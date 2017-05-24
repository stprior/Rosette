
biulds, fails from make with error

setting ESS_SYSDIR to "." in rosette
Rosette System, Version 3.0 (Jan 20, 1993 02:00:32 PM) - Copyright 1989, 1990, 1991, 1992 MCC
loading: ./configuration.rbl silent
loading: ./sbo-init.rbl silent
loading: ./system.rbl silent
*** runtime error:
        {StdOprn}
	        "bad method"
{Ctxt}
#niv
			



run standalone as boot_ess boot.rbl - somethimes fails with segfault

valgrind gives error about strlen

valrind:  A must-be-redirected function
valgrind:  whose name matches the pattern:      strlen
valgrind:  in an object with soname matching:   ld-linux.so.2
valgrind:  was not found whilst processing
valgrind:  symbols from the object with soname: ld-linux.so.2



installing libc6dbg makes no difference
sudo apt-get install libc6-dbg:i386



sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libc6-dbg:i386
make clean
make
valgrind --leak-check=yes bin/boot-ess -boot rbl/rosette/boot.rbl


As a bonus this lets rosette boot up correctly (or perhaps setting G++ optimisations off did that)
