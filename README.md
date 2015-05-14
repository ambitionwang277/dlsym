gcc -shared  -fPIC prog2.c -o libprog2.so -ldl  # the option is put last

LD_PRELOAD=$PWD/unrandom.so ldd random_nums

The dlfcn.h is needed for dlsym function we use later. That strange #define directive instructs the compiler to enable some non-standard stuff, we need it to enable RTLD_NEXT in dlfcn.h. 

example comes from the following websites:
http://www.opensourceforu.com/2011/08/lets-hook-a-library-function/
https://rafalcieslak.wordpress.com/2013/04/02/dynamic-linker-tricks-using-ld_preload-to-cheat-inject-features-and-investigate-programs/
