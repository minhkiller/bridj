<table cellpadding='15' width='90%' border='1'>
<tr>
<td align='center'>
BridJ aims to be the <b>ultimate Java / native interoperability library</b> (<a href='CreditsAndLicense.md'>BSD-licensed</a>).<br>
<br />
<i>⇒ Call C, C++, ObjectiveC libraries without compiling native code</i>
<br />
<i>Moving to <a href='http://github.com/nativelibs4java/BridJ'>github.com/nativelibs4java/BridJ</a></i>
</td>
</tr><tr>
<td align='center'>
<a href='FAQ.md'>FAQ</a> |<br>
<a href='Download.md'>Download</a> | <a href='https://github.com/nativelibs4java/BridJ/blob/master/CHANGELOG.md'>Change Log</a> |<br>
<a href='http://nativelibs4java.sourceforge.net/bridj/api/stable/'>0.7.0 API</a> |<br>
<a href='http://nativelibs4java.sourceforge.net/bridj/api/development/'>0.7.1-SNAPSHOT API</a> |<br>
<a href='http://groups.google.com/group/nativelibs4java/'>Forum / Support</a>
</td>
</tr></table>

BridJ is **a [young project with limitations](CurrentState.md)** (in particular with respect to passing structs-by-value, C++ templates and ObjectiveC support...).

It was inspired by [JNA](http://jna.dev.java.net/) but it has :
  * uncompromised speed (thanks to [dyncall](http://dyncall.org/) and [assembler optimizations](Design.md))
  * more features : (limited) support for C++, COM, Objective-C...
  * better usability : Java 1.5+ generics, annotations...
  * a liberal [BSD license](CreditsAndLicense.md) (GPL-compatible)

# Key features #
  * Dynamic C / C++ / COM interop : call C++ methods, create C++ objects (and **[subclass C++ classes](CPlusPlus.md) from Java** !)
  * You **never need to compile any extra native code**: we deal with the cross-compilation hassle for you once and for all in BridJ ! (works on Windows, Linux, MacOS X, Solaris, Android...)
  * Full [JNAerator support](http://jnaerator.googlecode.com) : stay away from C / C++ headers !
  * Small library size (~ 600 kB all included)
  * Straightforward type mappings with good use of generics
> [Learn more](FAQ.md)

# Quickstart #

  1. See if one of the [Examples](https://github.com/ochafik/nativelibs4java/tree/master/libraries/BridJ/Examples/BasicExample) can work for you
  1. [Download](Download.md) Bridj's binaries or add the following repository and dependency to your [Maven pom.xml](http://maven.apache.org/guides/introduction/introduction-to-the-pom.html) (see the [Download](Download.md) page for more options, including specialized trimmed-down versions) :
```
<dependencies>
  <dependency>
    <groupId>com.nativelibs4java</groupId>
    <artifactId>bridj</artifactId>
    <version>0.7.0</version>
  </dependency>
  ...
</dependencies>
<repositories>
  <!-- Needed only for snapshot versions -->
  <repository>
    <id>sonatype</id>
    <name>Sonatype OSS Snapshots Repository</name>
    <url>http://oss.sonatype.org/content/groups/public</url>
  </repository>
  <!-- Needed only for releases older than 0.6.1 -->
  <repository>
    <id>nativelibs4java</id>
    <name>nativelibs4java Maven2 Repository</name>
    <url>http://nativelibs4java.sourceforge.net/maven</url>
  </repository>
  ...
</repositories>
```
  1. [Generate BridJ wrappers](http://jnaerator.sourceforge.net/webstart/JNAerator/JNAeratorStudio.jnlp) for your library using [JNAerator](http://jnaerator.googlecode.com) (just select "BridJ" in the "Runtime" combobox).
  1. Read some documentation :
    * The [FAQ](FAQ.md) might save your life
    * Javadoc :
      * [BridJ Development API (0.7.1-SNAPSHOT)](http://nativelibs4java.sourceforge.net/bridj/api/development) (direct link : [Pointer class](http://nativelibs4java.sourceforge.net/bridj/api/development/org/bridj/Pointer.html)) ; see [changelog](https://github.com/nativelibs4java/BridJ/blob/master/CHANGELOG.md)
      * [BridJ Stable API (0.7.0)](http://nativelibs4java.sourceforge.net/bridj/api/stable) (direct link : [Pointer class](http://nativelibs4java.sourceforge.net/bridj/api/stable/org/bridj/Pointer.html))
> > FYI Pointer is probably the most important class to look at, the only other classes you need to know about are the ones created by [JNAerator](http://jnaerator.googlecode.com).
  1. Join the [NativeLibs4Java Google Group](http://groups.google.com/group/nativelibs4java/) to share your questions and remarks with the community !

# Example #

Original C++ code :
```
/// exported in test.dll / libtest.so / libtest.dylib
class MyClass {
public:
    MyClass();
    ~MyClass();
    virtual void virtualMethod(int i, float f);
    void normalMethod(int i);
};
void getSomeCount(int* countOut);
...
void test() {
    int count;
    getSomeCount(&count);
    MyClass t;
    t.virtualMethod(count, 0.5f);
}
```

Translation + binding with BridJ :
```
import org.bridj.*;     // C interop and core classes
import org.bridj.ann.*; // annotations
import org.bridj.cpp.*; // C++ runtime
import static org.bridj.Pointer.*; // pointer factories such as allocateInt(), pointerTo(java.nio.Buffer), etc...

@Library("test")
public class TestLibrary {
    static {
        BridJ.register(); // binds all native methods in this class and its subclasses
    }
    public static class MyClass extends CPPObject {
        @Virtual(0) // says virtualMethod is the first virtual method
        public native void virtualMethod(int i);
        public native void normalMethod(int i);
    };
    public static native void getSomeCount(Pointer<Integer> countOut);

    public static void test() {
        Pointer<Integer> pCount = allocateInt();
        getSomeCount(pCount);
        MyClass t = new MyClass();
        t.virtualMethod(pCount.get(), 0.5f);
    }
}
```