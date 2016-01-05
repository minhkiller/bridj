

Display [the CHANGELOG](https://github.com/ochafik/nativelibs4java/tree/master/libraries/BridJ/CHANGELOG)

# Supported Platforms #

See the [FAQ](FAQ.md) and the [Download](Download.md) pages.

# Working Features #

  * thread-safe design (including reentrant calls)
  * [JNAerator](http://jnaerator.googlecode.com/) support on par with JNA's
  * C functions calls with cdecl and stdcall conventions (including varargs support)
  * C++ constructors, method calls and destructors (including virtual methods, thiscall and stdcall conventions)
  * C++ classes subclassing from Java (override virtual C++ methods from Java !)
  * lazy signatures annotation support (exact symbols are optional)
  * Call C callbacks from Java and call Java-implemented callbacks from C
  * Complete [Pointers](Pointers.md) API (with typed opaque pointers, array accessible + iterable reified generic Pointer base class...)
  * Type-safe enums (ValuedEnum + [FlagSet](http://nativelibs4java.sourceforge.net/bridj/api/stable/org/bridj/FlagSet.html) classes) : unifies singleton and multi-flags patterns
  * [COM](COM.md) object creation and calls, with some support for the VARIANT type
  * lightweight and fast structs (no memory duplication nor update issues between Java and the native side), with unions and sub-structs
  * [Getting the native handler to an AWT Component's peer](http://nativelibs4java.sourceforge.net/bridj/api/stable/org/bridj/jawt/JAWTUtils.html)
  * Dynamic function pointers casting (see Pointer.asDynamicFunction)
  * Enumeration of shared libraries symbols (w/ demangling) and resolution of libraries paths (including support for GNU LD scripts)

# Known limitations #

  * structs by value not supported yet (neither as function arguments nor as function return values)
  * requires Java 1.5 or more recent (if you need 1.4 compatibility, you shoud JNA instead)

# Features in progress #

  * assembly-optimized raw calls (for Win32, Win64, Mac64, Linux32, Linux64) : win64 is buggy, lin32 is TODO, mac is buggy with floats and doubles (of course, buggy implies disabled)
  * C++ templates for functions and classes (combination of generics and extra args/fields for types reification and last-minute lookup of actual symbols). Begins to work with GCC.
  * ObjectiveC methods calls (objc\_msgSend) : hope to draw interest from Rococoa developers

# Planned features #

(also see [GoogleSummerOfCode](GoogleSummerOfCode.md) for projects on which we'd love to receive help, from students or passionate individuals)

  * pass and return structs by value
  * C++ templates typedefs : `typedef WImageC<uchar, 1>        WImage1_b;` (JNAerator should create WImage1\_b with the correct constructor).
  * COM JNAeration : need to parse declspec(uuid("xxx"))
  * **some** amount of built-in support for STL types (strings and vector at least, in debug/release mode, for GNU's STL, STLPort and MS VC++9's STL)
  * Full MFC Runtime (with annotations-based message map creation)
  * Mono/CLR interop (see [my previous hack](http://ochafik.free.fr/blog/?p=165))
  * MS/.NET interop
  * reverse-engineering helper (struct sizes guesses can be eased up a bit, and there's already a good demangler)

# Dynamic Library dependencies #

On Windows :
  * C runtime + DbgHelp

On MacOS X :
  * C runtime + libobjc + pthreads

On other Unix platforms :
  * C runtime + pthreads

# Features Not Planned / Ruled Out #

Why limiting the scope of this project so early ?