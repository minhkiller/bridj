

# Main author #

Olivier Chafik (author of [BridJ](http://code.google.com/p/bridj/), [JNAerator](http://code.google.com/p/jnaerator/), [JavaCL](http://code.google.com/p/javacl/) and [ScalaCL](http://code.google.com/p/scalacl/))
  * [Blog : Ché zOlive](http://ochafik.free.fr/blog/)
  * [Twitter : @ochafik](http://twitter.com/ochafik)

# Contributors #

  * [Rémi Emonet](http://twitter.com/remiemonet) : many enhancements in BridJ's GCC demangler
  * [Kazó Csaba](http://kazocsaba.blogspot.com/) : bug reports + patches for JavaCL (kernel binaries, reduction utilities...)
  * Andrei Sochirca : intense bug reporting and many suggestions that drove [release 0.4.1](https://github.com/ochafik/nativelibs4java/tree/master/libraries/BridJ/CHANGELOG#) of BridJ
  * [Atsushi Eno](https://github.com/atsushieno) : testing and many patch proposals that helped support BridJ on Android
  * [Bob Boothby](http://bbboblog.blogspot.com/) : Mandelbrot demo in JavaCL
  * Jeff Palmer : moderation of [the mailing list](http://groups.google.com/group/nativelibs4java) and support to JavaCL users
  * [Samuel Audet](http://www.ok.ctrl.titech.ac.jp/~saudet/) : support to JavaCL users
  * Countless [bug reporters](http://github.com/ochafik/nativelibs4java/issues), whose energy and patience are a great motivation !

[Wonder how to help ? Read this page !](HowToHelp.md)

# Generous donors #

  * Matthew S. (Paypal donation)
  * [Roger Pack](http://freeldssheetmusic.org/) (Paypal donation)
  * Tishampati Dhar (Paypal donation)
  * NeZetiC (donation of a Sun Ultra 5 computer so I can work on the BridJ+dyncall Sparc port)

While I'm working on these projects for the fun of it on my free time, I still don't own any sports car... Any donation will be greatly appreciated :
> <a href='http://sourceforge.net/donate/index.php?group_id=266856'><img src='http://images.sourceforge.net/images/project-support.jpg' alt='Become a sponsor' border='0' width='88' height='32' /></a>

# Projects Used #

BridJ uses the following libraries :
  * [dyncall](http://dyncall.org), an excellent lightweight FFI library distributed under [an ISC-style license](http://dyncall.org/license.shtml) (reproduced below).
> Daniel Adler and Tassilo Philipp (authors of [dyncall](http://dyncall.org/)) have been very supportive and kindly accepted and/or adapted most if not all of the patches I submitted to them, many thanks !
> To patch dyncall with BridJ's modifications, type :
```
wget http://nativelibs4java.googlecode.com/svn/trunk/libraries/BridJ/admin/patch_dyncall.sh
bash patch_dyncall.sh dyncall
```
  * [ASM](http://asm.ow2.org/), a Java code generation library distributed under [a 3-clauses BSD-style license](http://asm.ow2.org/license.html) (reproduced below).

Note that BridJ ships with these libraries, so you don't need to put them in the path or install them to your system : **BridJ's JAR file is self-contained.**

# Projects that use BridJ #

See [WhoUsesBridJ](WhoUsesBridJ.md)

# Licenses #

## BridJ, JavaCL & ScalaCL License (3-clauses BSD-like) ##

```
Copyright (c) 2010-2013, Olivier Chafik
All rights reserved.
Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

  * Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
  * Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
  * Neither the name of Olivier Chafik nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE REGENTS AND CONTRIBUTORS ``AS IS'' AND ANY
EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE REGENTS AND CONTRIBUTORS BE LIABLE FOR ANY
DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

## dyncall License (2-clauses BSD-like) ##

[dyncall](http://dyncall.org) is redistributed in binary form in BridJ's binary downloads an in its source tree, and in source form in its source tree.

It is originally distributed under an [an ISC-style license](http://dyncall.org/license.shtml) (see [Wikipedia's page about the ISC license](http://en.wikipedia.org/wiki/ISC_license)) :

```
Copyright (c) 2007-2010 
                        Daniel Adler <dadler AT uni-goettingen DOT de>, 
                        Tassilo Philipp <tphilipp AT potion-studios DOT com>

Permission to use, copy, modify, and distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```

## ASM License (3-clauses BSD-like) ##

[ASM](http://asm.ow2.org/) is redistributed in binary form in BridJ's binary downloads.

It is originally distributed under a [3-clauses BSD-style license](http://asm.ow2.org/license.html) (see [Wikipedia's page about the BSD license](http://en.wikipedia.org/wiki/BSD_Licence)) :

```
Copyright (c) 2000-2005 INRIA, France Telecom
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:

1. Redistributions of source code must retain the above copyright
   notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright
   notice, this list of conditions and the following disclaimer in the
   documentation and/or other materials provided with the distribution.

3. Neither the name of the copyright holders nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF
THE POSSIBILITY OF SUCH DAMAGE.
```