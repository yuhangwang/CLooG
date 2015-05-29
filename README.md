# CLooG
**Clunky Loop Generator**

This is an unofficial verbatim redistribution of the binary&source form of the CLooG library (a prerequisite for compiling programs like GCC 4.7), under the terms of GPL 2.0 license.

This redistribution is under the the same GPL 2.0.

Please visit the official website for more details: http://www.cloog.org

## Usage
The binary/ folder contains both a tar.gz file and a folder, which are equivalent. You can use either one.

## Compilation notes
### Compilation environment
* CentOS 6.6
* x86_64 architecture
* Compiler: gcc version 4.4.7 20120313 (Red Hat 4.4.7-11)

### Compilation steps
```bash
wget ftp://gcc.gnu.org/pub/gcc/infrastructure/cloog-ppl-0.15.11.tar.gz
tar xvf cloog-ppl-0.15.11.tar.gz
mkdir build_cloog-ppl-0.15
cd build_cloog-ppl-0.15
../cloog-ppl-0.15/configure --prefix=/home/steven/install/libcloog/0.15.11 --with-ppl=/home/steven/install/libppl/0.11 --with-gmp=/home/steven/install/libgmp/with_cxx_support/for_gcc_4.4.7/4.3.2
make -j10
make check -j10 | tee QualityVerification.txt
make install
```

### Quality verification
See the "QualityVerification.txt" for the output of "make check".