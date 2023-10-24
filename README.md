
```
$ make clean
$ make
nvc++ -std=c++17 -cuda -gpu=cc60 -gpu=rdc -c -o main.o main.cpp
nvc++ -std=c++17 -cuda -gpu=cc60 -gpu=rdc -c -o amrex_random.o amrex_random.cpp
nvc++ -std=c++17 -cuda -gpu=cc60 -gpu=rdc -cudalib=curand -o a.out main.o amrex_random.o
nvlink error   : Multiple definition of 'precalc_xorwow_matrix' in 'amrex_random.o', first defined in 'main.o'
nvlink error   : Multiple definition of 'precalc_xorwow_offset_matrix' in 'amrex_random.o', first defined in 'main.o'
nvlink error   : Multiple definition of 'mrg32k3aM1' in 'amrex_random.o', first defined in 'main.o'
nvlink error   : Multiple definition of 'mrg32k3aM2' in 'amrex_random.o', first defined in 'main.o'
nvlink error   : Multiple definition of 'mrg32k3aM1SubSeq' in 'amrex_random.o', first defined in 'main.o'
nvlink error   : Multiple definition of 'mrg32k3aM2SubSeq' in 'amrex_random.o', first defined in 'main.o'
nvlink error   : Multiple definition of 'mrg32k3aM1Seq' in 'amrex_random.o', first defined in 'main.o'
nvlink error   : Multiple definition of 'mrg32k3aM2Seq' in 'amrex_random.o', first defined in 'main.o'
nvlink error   : Multiple definition of '__cr_lgamma_table' in 'amrex_random.o', first defined in 'main.o'
nvlink fatal   : merge_elf failed
pgacclnk: child process exit status 2:
/opt/nvidia/hpc_sdk/Linux_x86_64/23.9/compilers/bin/tools/nvdd
make: *** [GNUmakefile:8: a.out] Error 2

$ make clean
$ make CXXSTD=c++14
nvc++ -std=c++14 -cuda -gpu=cc60 -gpu=rdc -c -o main.o main.cpp
nvc++ -std=c++14 -cuda -gpu=cc60 -gpu=rdc -c -o amrex_random.o amrex_random.cpp
nvc++ -std=c++14 -cuda -gpu=cc60 -gpu=rdc -cudalib=curand -o a.out main.o amrex_random.o
```
