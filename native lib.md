https://hadoop.apache.org/docs/current/hadoop-project-dist/hadoop-common/NativeLibraries.html

The native hadoop library is written in ANSI C and is built using the GNU autotools-chain (autoconf, autoheader, automake, autoscan, libtool). This means it should be straight-forward to build the library on any platform with a standards-compliant C compiler and the GNU autotools-chain (see the supported platforms).

The packages you need to install on the target platform are:

C compiler (e.g. GNU C Compiler)
GNU Autools Chain: autoconf, automake, libtool
zlib-development package (stable version >= 1.2.0)
openssl-development package(e.g. libssl-dev)
Once you installed the prerequisite packages use the standard hadoop pom.xml file and pass along the native flag to build the native hadoop library:

   $ mvn package -Pdist,native -DskipTests -Dtar
You should see the newly-built library in:

   $ hadoop-dist/target/hadoop-2.7.1/lib/native
