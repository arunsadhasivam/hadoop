----------------------------------------------------------------------------------
Building on Windows
----------------------------------------------------------------------------------
Requirements:

* Windows System
* JDK 1.6+
* Maven 3.0 or later
* Findbugs 1.3.9 (if running findbugs)
* ProtocolBuffer 2.5.0
* CMake 2.6 or newer
* Windows SDK or Visual Studio 2010 Professional
* Unix command-line tools from GnuWin32 or Cygwin: sh, mkdir, rm, cp, tar, gzip
* zlib headers (if building native code bindings for zlib)
* Internet connection for first build (to fetch all Maven and Hadoop dependencies)

If using Visual Studio, it must be Visual Studio 2010 Professional (not 2012).
Do not use Visual Studio Express. It does not support compiling for 64-bit,
which is problematic if running a 64-bit system. The Windows SDK is free to
download here:

http://www.microsoft.com/en-us/download/details.aspx?id=8279

----------------------------------------------------------------------------------
Building:

Keep the source code tree in a short path to avoid running into problems related
to Windows maximum path length limitation. (For example, C:\hdc).

Run builds from a Windows SDK Command Prompt. (Start, All Programs,
Microsoft Windows SDK v7.1, Windows SDK 7.1 Command Prompt.)

JAVA_HOME must be set, and the path must not contain spaces. If the full path
would contain spaces, then use the Windows short path instead.

You must set the Platform environment variable to either x64 or Win32 depending
on whether you're running a 64-bit or 32-bit system. Note that this is
case-sensitive. It must be "Platform", not "PLATFORM" or "platform".
Environment variables on Windows are usually case-insensitive, but Maven treats
them as case-sensitive. Failure to set this environment variable correctly will
cause msbuild to fail while building the native code in hadoop-common.

set Platform=x64 (when building on a 64-bit system)
set Platform=Win32 (when building on a 32-bit system)

Several tests require that the user must have the Create Symbolic Links
privilege.

All Maven goals are the same as described above with the exception that
native code is built by enabling the 'native-win' Maven profile. -Pnative-win
is enabled by default when building on Windows since the native components
are required (not optional) on Windows.

If native code bindings for zlib are required, then the zlib headers must be      
deployed on the build machine. Set the ZLIB_HOME environment variable to the
directory containing the headers.

set ZLIB_HOME=C:\zlib-1.2.7

At runtime, zlib1.dll must be accessible on the PATH. Hadoop has been tested
with zlib 1.2.7, built using Visual Studio 2010 out of contrib\vstudio\vc10 in

the zlib 1.2.7 source tree.

http://www.zlib.net/

----------------------------------------------------------------------------------
Building distributions:

* Build distribution with native code : mvn package [-Pdist][-Pdocs][-Psrc][-Dtar]
