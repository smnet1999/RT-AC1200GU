## Padavan configurations for ASUS RT-AC1200GU

**Note**: The configration enables Chinese Simplified translation.You need to download [the dictionary file](https://github.com/gorden5566/padavan/raw/master/trunk/user/www/dict/CN.dict) and put them into ``/trunk/user/www/dict/`` ,then edit ``trunk/user/www/Makefile`` to enable it.  

***  
Just as Beijing No.3 Transportation Division said,"Routes are countless. Safety is foremost. Unregulated driving. Loved ones end up in tears."When we compiling,making toolchains happy is foremost. If you compile it on Ubuntu 18.04 (GCC7),you may face the following error:  
````
scripts/kconfig/zconf.tab.o: In function `zconflex':
zconf.tab.c:(.text+0xf05): undefined reference to `kconf_id_lookup'
zconf.tab.c:(.text+0xfb6): undefined reference to `kconf_id_lookup'
collect2: error: ld returned 1 exit status
scripts/Makefile.host:113: recipe for target 'scripts/kconfig/conf' failed
make[2]: *** [scripts/kconfig/conf] Error 1
/opt/rt-n56u/trunk/user/busybox/busybox-1.24.x/Makefile:443: recipe for target 'silentoldconfig' failed
make[1]: *** [silentoldconfig] Error 2
Makefile:519: recipe for target 'include/autoconf.h' failed
make: *** [include/autoconf.h] Error 2
make: Leaving directory '/opt/rt-n56u/trunk/user/busybox/busybox-1.24.x'
````  
Till now,Padavan didn't fix it,so try to use Docker or VM to run Ubuntu 16.04,and compile on it.
