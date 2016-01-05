# Bug tracker #

If you face what appears to be a bug in BridJ, [we](CreditsAndLicense.md)'d be very grateful if you could try and report it on the bug tracker :
> [NativeLibs4Java's BridJ Bug Tracker](https://github.com/ochafik/nativelibs4java/issues?labels=BridJ)

Of course, [we](CreditsAndLicense.md)'d recommend that you first look at the open bugs (and if you're not using the latest snapshot version of BridJ, that you also look at the bugs recently closed) to see if an issue similar to yours has already been reported.

# What should go in an ideal report #

To maximise the chances [we](CreditsAndLicense.md) can fix the issue and/or help you quickly, please make sure to provide all of the following items in the report :
  * Minimum-sized working code that exhibits the issue : **any of the following** :
    * a class with a static main method that compiles directly against BridJ's JAR (you might want to [build BridJ from sources](Build.md) and just drop your `.java` file to `src/main/java`, to have it compiled an run with `mvn compile exec:java -Dexec.mainClass=yourClass`)
    * a JUnit test class that can just be dropped into [BridJ's test sources](https://github.com/ochafik/nativelibs4java/tree/master/libraries/Runtime/BridJ/src/test/java/org/bridj)
    * an archive of a project that compiles **easily** with Maven or Ant
> _In particular, please make sure to include the source code of your BridJ bindings._ If you've used [JNAerator](http://code.google.com/p/jnaerator/) without the [-noComp and -noJar options](http://code.google.com/p/jnaerator/wiki/CommandLineOptionsAndEnvironmentVariables), the sources of the generated bindings are located in the generated JAR, alongside the .class files.
  * Instructions on how to run your code :
    * full command-line
    * prequisites :
      * native library to install manually ?
      * specific hardware ?
      * other dependencies (direct links and/or exact version numbers, please !)
  * The full error log of BridJ :
    * Set the `BRIDJ_VERY_VERBOSE=1` environment variable prior to running your program / test class
    * Any `hs_err_pidXXX.log` files
    * In case the program never ends (hangs with no normal reason), run `jconsole` and include a dump of the execution trace of the main thread (or of all of them)
  * A direct link to the native library targeted by your bindings, if possible and if needed to reproduce the issue
  * The full C/C++/Objective-C headers of the native library
  * The exact [JNAerator](http://code.google.com/p/jnaerator/) arguments you've used to generate your bindings, if you've used that tool (which is highly advised !)

Also, please do not use fancy archive formats (stick to plain old `.zip`), and if you have only a handful of files without particular directory hierarchy, you can even attach these files separately (this way they'll be readable separately from an iPhone).

Anyway if you're in doubt, please come and ask on [the mailing-list](http://groups.google.com/group/nativelibs4java) :-)