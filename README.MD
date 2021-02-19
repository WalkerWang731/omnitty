# Omnitty Integration Version

## What is the Omnitty？
Omnitty is a simplified terminal ssh tool. It can provide your management multiple servers with more convenient!

Although it was created in 2004, it is still one of the best options when you want to manage multiple servers!


## The Difference with Ansible or SaltStack(or other automatic tools)
It is a terminal ssh tool that real-time interactive, you can use any interactive 'command', such as `vim`, `top`, `screen`, etc. 

This is not possible with other automatic tools.

## How to install

#### First install `rote`
- `cd rote-0.2.8` 
- `chmod +x configure`
- `./configure`
- `make && make install`

#### Then install `omnitty`
- `cd omnitty-0.3.0` or `cd omnitty-g112wdh`
- `./configure`
- `make && make install`

#### If you want to install on Mac OS
Please `copy` and `replace` files that same name from the `osx_patch` directory


## Q&A
#### When occurred that `Need ncurses to compile librote`
- CentOS: `yum install ncurses-devel`
- ubuntu: `apt-get install libncurses5-dev`

#### When occurred that `DSO missing from command line`

The error example
```
# make  
gcc -g -O2 -I/usr/local/include -Wall -DOMNITTY_VERSION=\"0.3.0\" -o omnitty minibuf.o machine.o main.o machmgr.o help.o menu.o curutil.o  -L/usr/local/lib -lrote   
/usr/bin/ld: help.o: undefined reference to symbol 'delwin@@NCURSES_5.0.19991023'  
//lib/x86_64-linux-gnu/libncurses.so.5: error adding symbols: DSO missing from command line  
collect2: error: ld returned 1 exit status  
Makefile:18: recipe for target 'omnitty' failed  
make: *** [omnitty] Error 1  
```

You can edit `omnitty-{VERSION}/Makefile.in` and replace that lines:
```
omnitty: $(objects)  
$(CC) $(CFLAGS)  -o omnitty $(objects) $(LDFLAGS) $(LIBS) -lncurses  -ltinfo
```

## Thanks for them
- rote-0.2.8 from http://rote.sourceforge.net/
- omnitty-0.3.0 from http://omnitty.sourceforge.net/
- omnitty-g112wdh from [@g112wdh](https://github.com/g112wdh/omnitty)
- osx_patch from [@mastre](https://github.com/mastre/omnitty_osx)
