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
#### Version: 0.15.11
```bash
wget ftp://gcc.gnu.org/pub/gcc/infrastructure/cloog-ppl-0.15.11.tar.gz
tar xvf cloog-ppl-0.15.11.tar.gz
mkdir build_cloog-ppl-0.15.11
cd build_cloog-ppl-0.15.11
../cloog-ppl-0.15.11/configure --prefix=/home/steven/install/libcloog/0.15.11 --with-ppl=/home/steven/install/libppl/0.11 --with-gmp=/home/steven/install/libgmp/with_cxx_support/for_gcc_4.4.7/4.3.2
make -j10
make check -j10 | tee QualityVerification.txt
make install
```


#### Version: 0.18.0
**(based on isl-0.11.1 and gmp-4.3.2)**
```bash
wget ftp://gcc.gnu.org/pub/gcc/infrastructure/cloog-0.18.0.tar.gz
tar xvf cloog-0.18.0.tar.gz
mkdir build_cloog-0.18.0
cd build_cloog-0.18.0
../cloog-0.18.0/configure --prefix=/home/steven/install/libcloog/0.18.0 --with-gmp=system --with-gmp-prefix=/home/steven/install/libgmp/4.3.2 --with-gmp-exec-prefix=/home/steven/install/libgmp/4.3.2 --with-isl=system --with-isl-prefix=/home/steven/install/libisl/0.11.1 --with-isl-exec-prefix=/home/steven/install/libisl/0.11.1 --enable-portable-binary=yes --enable-shared=yes --enable-static=yes
make -j10
make check -j10 | tee QualityVerification.txt
make install
```
note: GCC 4.8.4 requires isl-based CLooG and **must** be built against isl-0.11.1 (not the bundled isl). "--with-bits=gmp" ensures CLooG is configured to use GMP internally (required by GCC 4.8.4).

#### Version: 0.18.1
**(based on isl-0.12.2 and gmp-4.3.2)**
```bash
wget ftp://gcc.gnu.org/pub/gcc/infrastructure/cloog-0.18.1.tar.gz
tar xvf cloog-ppl-0.18.1.tar.gz
mkdir build_cloog-0.18.1
cd build_cloog-0.18.1
../cloog-0.18.1/configure --prefix=/home/steven/install/libcloog/0.18.1 --with-gmp=system --with-gmp-prefix=/home/steven/install/libgmp/4.3.2 --with-gmp-exec-prefix=/home/steven/install/libgmp/4.3.2 --with-isl=system --with-isl-prefix=/home/steven/install/libisl/0.12.2 --with-isl-exec-prefix=/home/steven/install/libisl/0.12.2 --enable-portable-binary=yes --enable-shared=yes --enable-static=yes
make -j10
make check -j10 | tee QualityVerification.txt
make install
```
note: GCC 4.9.2 requires isl-based CLooG and **must** be built against isl-0.12.2 (not the bundled isl).

### Quality verification
See the "QualityVerification.txt" for the output of "make check".