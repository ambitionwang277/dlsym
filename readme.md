gcc -shared  -fPIC prog2.c -o libprog2.so -ldl  # the option is put last

LD_PRELOAD=$PWD/unrandom.so ldd random_nums

The dlfcn.h is needed for dlsym function we use later. That strange #define directive instructs the compiler to enable some non-standard stuff, we need it to enable RTLD_NEXT in dlfcn.h. 
