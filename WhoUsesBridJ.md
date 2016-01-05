

Please keep in mind that [BridJ is licensed under the BSD license](CreditsAndLicense.md), so anyone using it must state it appropriately in the documentation and/or other distributed materials (but there's no need to publish any modified sources, although it is good practice ;-)).

Here are some of the projects known to use BridJ internally (please post [on the mailing list](http://groups.google.com/group/nativelibs4java) if you'd like your project to be listed here) :

## StormMQ Myxi ##

" [StormMQ Myxi](http://stormmq.com/) is the world's first Message Queue as a Service using AMQP 1-0.

We decided to use BridJ as it is the only professionally-supported, efficient product available today to seamlessly integrate essential C functionality with Java. Olivier Chafik, the main developer, provides first-class support and deep technical understanding.

We've successfully mapped gnu libc and libpthread to allow us more fidelity and functionality on linux and work round Java's limitations with memory mapped files. "

## directx4java ##

[DirectX4Java](http://code.google.com/p/directx4java/) is a port of DirectX 10 and 11 for Java (MIT-licensed) written by [Evandro Millian](https://www.masterbranch.com/developer/evandro.millian).

It recently switched from JNA to BridJ to power its low-level COM interoperability.

## jlibav ##

[Java wrapper for Libav](http://code.google.com/p/jlibav/).

This library provides an access to a big part of the Libav functions via BridJ. It is compatible with all Libav binaries since version 0.7. The goal of this project is to cover complete functionality of the Libav. (Note: the Libav binaries are not a part of this library)

## OpenIMAJ ##

[Open Intelligent Multimedia Analysis toolkit for Java](http://www.openimaj.org/) (OpenIMAJ, BSD-licensed) is a collection of libraries for multimedia analysis, focusing on state of the art and highly scalable (multithreaded + distributed) image analysis and feature extraction. It was written by [Jon Hare](mailto:jsh2@ecs.soton.ac.uk), [Sina Samangooei](mailto:ss@ecs.soton.ac.uk) and [David Dupplaw](mailto:dpd@ecs.soton.ac.uk).

It uses BridJ in its 'openimaj-serial-driver' and 'core-video-capture' modules.

## webcam-capture ##

[sarxos/webcam-capture](http://webcam-capture.sarxos.pl/) is a generic Webcam capture utility (cross-platform, multi-drivers).

It uses BridJ for its built-in drivers.

## hunspell-bridj ##

[HunspellBridJ](https://github.com/thomas-joiner/HunspellBridJ): bindings for the Hunspell library for Java, using BridJ.

## BridJ PCap ##

[BridJ PCap](http://os.smaxe.com/bridj-pcap.html) (LGPL-licensed) is a library written by [Andrei Sochirca](http://andreisochirca.blogspot.com/) that provides network packet capture functionality.

It uses BridJ to leverage the native install of [libpcap](http://www.tcpdump.org/) or [WinPCap](http://www.winpcap.org/).

## `GeoTools` ##

[GeoTools](http://www.geotools.org/) is an open source Java library that provides tools for geospatial data.

It uses BridJ to bind the [OGR](http://www.gdal.org/ogr/) library.

## falplayer-android-j ##

[falplayer-android-j](https://github.com/atsushieno/falplayer-android-j) (MIT-licensed) is the Java version of [Atsushi Eno](https://github.com/atsushieno)'s Ogg Vorbis music player for Android (see original version : [falplayer](https://github.com/atsushieno/falplayer-android)).

It features BridJ-powered libvorbisidec / [Tremolo](http://wss.co.uk/pinknoise/tremolo/) bindings.

## JavaCL ##

[JavaCL](http://code.google.com/p/javacl/) (BSD-licensed) is an [OpenCL](http://www.khronos.org/opencl/) bindings library for Java.

It switched to BridJ for its low-level bindings (legacy JNA version is still available for download).

[JavaCL is also used by other projects](http://code.google.com/p/javacl/wiki/WhoUsesJavaCL), which hence make indirect use of BridJ.

## ScalaCL ##

[ScalaCL](http://code.google.com/p/scalacl/) (BSD-licensed) is an optimizing Scala compiler plugin + GPU-backed collections.

It uses the BridJ port of JavaCL.