# crossbridge-zlib

http://crossbridge.io/

STATICLIB=libz.a
```
CFLAGS="-emit-llvm" ./configure
CFLAGS="-emit-llvm" make
"/cygdrive/c/crossbridge/sdk/usr/bin/g++" -O4 zlibmain.c -L. libz.a -emit-swc=zlib -o zlib.swc
"/cygdrive/c/crossbridge/sdk/usr/bin/swig" -as3 -module zlib -outdir . -includeall -ignoremissing -o zlib_wrapper.c zlibswig.h
"/cygdrive/c/crossbridge/sdk/usr/bin/g++" -Werror -Wno-write-strings -Wno-trigraphs -O4 adler32.o compress.o crc32.o deflate.o gzclose.o gzlib.o gzread.o gzwrite.o infback.o inffast.o inflate.o inftrees.o trees.o uncompr.o zutil.o zlibmain.c zlib_wrapper.c -emit-swc=zlib -o zlib.swc
```