# C program execution process

![alt text](Pictures\c_compile.png "c_program_execution_process")

1. Preprocessor converts the source file (app.c) into pre-processed file (app.i)

    ```markdown
    gcc -E app.c -o app.i
    ```

2. Compiler converts the pre-processed file (app.i) into assembly (app.s)

    ```markdown
    gcc -S app.i -o app.s
    ```

3. Assembler takes the assembly file (app.s) as input and generates relocatable object file (app.o)

    ```markdown
    gcc -c app.s -o app.o
    ```

4. Linker converts the relocatable object file (app.o) into executable file (app.out)

    ```markdown
    gcc app.o -o app.out
    ```


The steps 1 and 2 are usually referred as compilation and the steps 3 and 4 are referred as build.

#testing




## Sample program execution output in Jenkins

```
Started by user Kalesha Shaik
Running as SYSTEM
Building on master in workspace /var/lib/jenkins/workspace/c-program-execution
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --is-inside-work-tree # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/ping2kalesh/c-program-execution.git # timeout=10
Fetching upstream changes from https://github.com/ping2kalesh/c-program-execution.git
 > git --version # timeout=10
 > git --version # 'git version 2.17.1'
 > git fetch --tags --progress -- https://github.com/ping2kalesh/c-program-execution.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 8163ac6e66644e969cfaf51fc37221b3b96fff4a (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 8163ac6e66644e969cfaf51fc37221b3b96fff4a # timeout=10
Commit message: "Update README.md"
 > git rev-list --no-walk 8163ac6e66644e969cfaf51fc37221b3b96fff4a # timeout=10
[c-program-execution] $ /bin/sh -xe /tmp/jenkins4922339912569305347.sh
+ gcc -E -v app.c -o app.i
Using built-in specs.
COLLECT_GCC=gcc
OFFLOAD_TARGET_NAMES=nvptx-none
OFFLOAD_TARGET_DEFAULT=1
Target: x86_64-linux-gnu
Configured with: ../src/configure -v --with-pkgversion='Ubuntu 7.5.0-3ubuntu1~18.04' --with-bugurl=file:///usr/share/doc/gcc-7/README.Bugs --enable-languages=c,ada,c++,go,brig,d,fortran,objc,obj-c++ --prefix=/usr --with-gcc-major-version-only --program-suffix=-7 --program-prefix=x86_64-linux-gnu- --enable-shared --enable-linker-build-id --libexecdir=/usr/lib --without-included-gettext --enable-threads=posix --libdir=/usr/lib --enable-nls --enable-bootstrap --enable-clocale=gnu --enable-libstdcxx-debug --enable-libstdcxx-time=yes --with-default-libstdcxx-abi=new --enable-gnu-unique-object --disable-vtable-verify --enable-libmpx --enable-plugin --enable-default-pie --with-system-zlib --with-target-system-zlib --enable-objc-gc=auto --enable-multiarch --disable-werror --with-arch-32=i686 --with-abi=m64 --with-multilib-list=m32,m64,mx32 --enable-multilib --with-tune=generic --enable-offload-targets=nvptx-none --without-cuda-driver --enable-checking=release --build=x86_64-linux-gnu --host=x86_64-linux-gnu --target=x86_64-linux-gnu
Thread model: posix
gcc version 7.5.0 (Ubuntu 7.5.0-3ubuntu1~18.04) 
COLLECT_GCC_OPTIONS='-E' '-v' '-o' 'app.i' '-mtune=generic' '-march=x86-64'
 /usr/lib/gcc/x86_64-linux-gnu/7/cc1 -E -quiet -v -imultiarch x86_64-linux-gnu app.c -o app.i -mtune=generic -march=x86-64 -fstack-protector-strong -Wformat -Wformat-security
ignoring nonexistent directory "/usr/local/include/x86_64-linux-gnu"
ignoring nonexistent directory "/usr/lib/gcc/x86_64-linux-gnu/7/../../../../x86_64-linux-gnu/include"
#include "..." search starts here:
#include <...> search starts here:
 /usr/lib/gcc/x86_64-linux-gnu/7/include
 /usr/local/include
 /usr/lib/gcc/x86_64-linux-gnu/7/include-fixed
 /usr/include/x86_64-linux-gnu
 /usr/include
End of search list.
COMPILER_PATH=/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/:/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/
LIBRARY_PATH=/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../x86_64-linux-gnu/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../../lib/:/lib/x86_64-linux-gnu/:/lib/../lib/:/usr/lib/x86_64-linux-gnu/:/usr/lib/../lib/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../:/lib/:/usr/lib/
COLLECT_GCC_OPTIONS='-E' '-v' '-o' 'app.i' '-mtune=generic' '-march=x86-64'
+ sleep 5
+ gcc -S -v app.i -o app.s
Using built-in specs.
COLLECT_GCC=gcc
OFFLOAD_TARGET_NAMES=nvptx-none
OFFLOAD_TARGET_DEFAULT=1
Target: x86_64-linux-gnu
Configured with: ../src/configure -v --with-pkgversion='Ubuntu 7.5.0-3ubuntu1~18.04' --with-bugurl=file:///usr/share/doc/gcc-7/README.Bugs --enable-languages=c,ada,c++,go,brig,d,fortran,objc,obj-c++ --prefix=/usr --with-gcc-major-version-only --program-suffix=-7 --program-prefix=x86_64-linux-gnu- --enable-shared --enable-linker-build-id --libexecdir=/usr/lib --without-included-gettext --enable-threads=posix --libdir=/usr/lib --enable-nls --enable-bootstrap --enable-clocale=gnu --enable-libstdcxx-debug --enable-libstdcxx-time=yes --with-default-libstdcxx-abi=new --enable-gnu-unique-object --disable-vtable-verify --enable-libmpx --enable-plugin --enable-default-pie --with-system-zlib --with-target-system-zlib --enable-objc-gc=auto --enable-multiarch --disable-werror --with-arch-32=i686 --with-abi=m64 --with-multilib-list=m32,m64,mx32 --enable-multilib --with-tune=generic --enable-offload-targets=nvptx-none --without-cuda-driver --enable-checking=release --build=x86_64-linux-gnu --host=x86_64-linux-gnu --target=x86_64-linux-gnu
Thread model: posix
gcc version 7.5.0 (Ubuntu 7.5.0-3ubuntu1~18.04) 
COLLECT_GCC_OPTIONS='-S' '-v' '-o' 'app.s' '-mtune=generic' '-march=x86-64'
 /usr/lib/gcc/x86_64-linux-gnu/7/cc1 -fpreprocessed app.i -quiet -dumpbase app.i -mtune=generic -march=x86-64 -auxbase-strip app.s -version -o app.s -fstack-protector-strong -Wformat -Wformat-security
GNU C11 (Ubuntu 7.5.0-3ubuntu1~18.04) version 7.5.0 (x86_64-linux-gnu)
	compiled by GNU C version 7.5.0, GMP version 6.1.2, MPFR version 4.0.1, MPC version 1.1.0, isl version isl-0.19-GMP

GGC heuristics: --param ggc-min-expand=100 --param ggc-min-heapsize=131072
GNU C11 (Ubuntu 7.5.0-3ubuntu1~18.04) version 7.5.0 (x86_64-linux-gnu)
	compiled by GNU C version 7.5.0, GMP version 6.1.2, MPFR version 4.0.1, MPC version 1.1.0, isl version isl-0.19-GMP

GGC heuristics: --param ggc-min-expand=100 --param ggc-min-heapsize=131072
Compiler executable checksum: b62ed4a2880cd4159476ea8293b72fa8
COMPILER_PATH=/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/:/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/
LIBRARY_PATH=/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../x86_64-linux-gnu/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../../lib/:/lib/x86_64-linux-gnu/:/lib/../lib/:/usr/lib/x86_64-linux-gnu/:/usr/lib/../lib/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../:/lib/:/usr/lib/
COLLECT_GCC_OPTIONS='-S' '-v' '-o' 'app.s' '-mtune=generic' '-march=x86-64'
+ sleep 5
+ gcc -c -v app.s -o app.o
Using built-in specs.
COLLECT_GCC=gcc
OFFLOAD_TARGET_NAMES=nvptx-none
OFFLOAD_TARGET_DEFAULT=1
Target: x86_64-linux-gnu
Configured with: ../src/configure -v --with-pkgversion='Ubuntu 7.5.0-3ubuntu1~18.04' --with-bugurl=file:///usr/share/doc/gcc-7/README.Bugs --enable-languages=c,ada,c++,go,brig,d,fortran,objc,obj-c++ --prefix=/usr --with-gcc-major-version-only --program-suffix=-7 --program-prefix=x86_64-linux-gnu- --enable-shared --enable-linker-build-id --libexecdir=/usr/lib --without-included-gettext --enable-threads=posix --libdir=/usr/lib --enable-nls --enable-bootstrap --enable-clocale=gnu --enable-libstdcxx-debug --enable-libstdcxx-time=yes --with-default-libstdcxx-abi=new --enable-gnu-unique-object --disable-vtable-verify --enable-libmpx --enable-plugin --enable-default-pie --with-system-zlib --with-target-system-zlib --enable-objc-gc=auto --enable-multiarch --disable-werror --with-arch-32=i686 --with-abi=m64 --with-multilib-list=m32,m64,mx32 --enable-multilib --with-tune=generic --enable-offload-targets=nvptx-none --without-cuda-driver --enable-checking=release --build=x86_64-linux-gnu --host=x86_64-linux-gnu --target=x86_64-linux-gnu
Thread model: posix
gcc version 7.5.0 (Ubuntu 7.5.0-3ubuntu1~18.04) 
COLLECT_GCC_OPTIONS='-c' '-v' '-o' 'app.o' '-mtune=generic' '-march=x86-64'
 as -v --64 -o app.o app.s
GNU assembler version 2.30 (x86_64-linux-gnu) using BFD version (GNU Binutils for Ubuntu) 2.30
COMPILER_PATH=/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/:/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/
LIBRARY_PATH=/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../x86_64-linux-gnu/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../../lib/:/lib/x86_64-linux-gnu/:/lib/../lib/:/usr/lib/x86_64-linux-gnu/:/usr/lib/../lib/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../:/lib/:/usr/lib/
COLLECT_GCC_OPTIONS='-c' '-v' '-o' 'app.o' '-mtune=generic' '-march=x86-64'
+ gcc app.c -o -v app.out
+ ./app.out
main: Welcome to linux world
Finished: SUCCESS
```


## Observations

Preprocessor: The binary '/usr/lib/gcc/x86_64-linux-gnu/7/cc1' acts as a preprocessor. The preprocessor is responsible for including the preprocessor directives into the code. The preprocessed file is still ASCII text file

```
/usr/lib/gcc/x86_64-linux-gnu/7/cc1
root@jenkins:~# file app.i
app.i: C source, ASCII text
root@jenkins:~# head -5 app.i
# 1 "app.c"
# 1 "<built-in>"
# 1 "<command-line>"
# 31 "<command-line>"
# 1 "/usr/include/stdc-predef.h" 1 3 4
root@jenkins:~#
```

Compiler: The compiler converts the preprocessed code into the assembly file containing assembly instructions. The binary '/usr/lib/gcc/x86_64-linux-gnu/7/cc1' acts as compiler.

```
root@jenkins:~# file app.s
app.s: assembler source, ASCII text
root@jenkins:~# head -5 app.s
        .file   "app.c"
        .text
        .section        .rodata
.LC0:
        .string "%s, the funcation name is\n"
root@jenkins:~#
```

Assembler: The binary as acts as an assembler. The assembler converts the assembly language instructions into relocatable object file. The relocatalbe object file is an ELF binary file. We can't read the content of the ELF object file using cat/vim commands. We use the commands readelf/objdump to read the content of the ELF binary files.

```

 as -v --64 -o app.o app.s
root@jenkins:~# file app.o
app.o: ELF 64-bit LSB relocatable, x86-64, version 1 (SYSV), not stripped
root@jenkins:~#

root@jenkins:~# objdump -D app.o

app.o:     file format elf64-x86-64


Disassembly of section .text:

0000000000000000 <main>:
   0:   55                      push   %rbp
   1:   48 89 e5                mov    %rsp,%rbp
   4:   48 8d 35 00 00 00 00    lea    0x0(%rip),%rsi        # b <main+0xb>
   b:   48 8d 3d 00 00 00 00    lea    0x0(%rip),%rdi        # 12 <main+0x12>
  12:   b8 00 00 00 00          mov    $0x0,%eax
  17:   e8 00 00 00 00          callq  1c <main+0x1c>
  1c:   b8 00 00 00 00          mov    $0x0,%eax
  21:   5d                      pop    %rbp
  22:   c3                      retq

Disassembly of section .rodata:

0000000000000000 <__func__.2249-0x1b>:
   0:   25 73 2c 20 74          and    $0x74202c73,%eax
   5:   68 65 20 66 75          pushq  $0x75662065
   a:   6e                      outsb  %ds:(%rsi),(%dx)
   b:   63 61 74                movslq 0x74(%rcx),%esp
   e:   69 6f 6e 20 6e 61 6d    imul   $0x6d616e20,0x6e(%rdi),%ebp
  15:   65 20 69 73             and    %ch,%gs:0x73(%rcx)
  19:   0a 00                   or     (%rax),%al

000000000000001b <__func__.2249>:
  1b:   6d                      insl   (%dx),%es:(%rdi)
  1c:   61                      (bad)
  1d:   69                      .byte 0x69
  1e:   6e                      outsb  %ds:(%rsi),(%dx)
        ...

Disassembly of section .comment:

0000000000000000 <.comment>:
   0:   00 47 43                add    %al,0x43(%rdi)
   3:   43 3a 20                rex.XB cmp (%r8),%spl
   6:   28 55 62                sub    %dl,0x62(%rbp)
   9:   75 6e                   jne    79 <__func__.2249+0x5e>
   b:   74 75                   je     82 <__func__.2249+0x67>
   d:   20 37                   and    %dh,(%rdi)
   f:   2e 35 2e 30 2d 33       cs xor $0x332d302e,%eax
  15:   75 62                   jne    79 <__func__.2249+0x5e>
  17:   75 6e                   jne    87 <__func__.2249+0x6c>
  19:   74 75                   je     90 <__func__.2249+0x75>
  1b:   31 7e 31                xor    %edi,0x31(%rsi)
  1e:   38 2e                   cmp    %ch,(%rsi)
  20:   30 34 29                xor    %dh,(%rcx,%rbp,1)
  23:   20 37                   and    %dh,(%rdi)
  25:   2e                      cs
  26:   35                      .byte 0x35
  27:   2e 30 00                xor    %al,%cs:(%rax)

Disassembly of section .eh_frame:

0000000000000000 <.eh_frame>:
   0:   14 00                   adc    $0x0,%al
   2:   00 00                   add    %al,(%rax)
   4:   00 00                   add    %al,(%rax)
   6:   00 00                   add    %al,(%rax)
   8:   01 7a 52                add    %edi,0x52(%rdx)
   b:   00 01                   add    %al,(%rcx)
   d:   78 10                   js     1f <.eh_frame+0x1f>
   f:   01 1b                   add    %ebx,(%rbx)
  11:   0c 07                   or     $0x7,%al
  13:   08 90 01 00 00 1c       or     %dl,0x1c000001(%rax)
  19:   00 00                   add    %al,(%rax)
  1b:   00 1c 00                add    %bl,(%rax,%rax,1)
  1e:   00 00                   add    %al,(%rax)
  20:   00 00                   add    %al,(%rax)
  22:   00 00                   add    %al,(%rax)
  24:   23 00                   and    (%rax),%eax
  26:   00 00                   add    %al,(%rax)
  28:   00 41 0e                add    %al,0xe(%rcx)
  2b:   10 86 02 43 0d 06       adc    %al,0x60d4302(%rsi)
  31:   5e                      pop    %rsi
  32:   0c 07                   or     $0x7,%al
  34:   08 00                   or     %al,(%rax)
        ...
root@jenkins:~# readelf -a app.o
ELF Header:
  Magic:   7f 45 4c 46 02 01 01 00 00 00 00 00 00 00 00 00
  Class:                             ELF64
  Data:                              2's complement, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  ABI Version:                       0
  Type:                              REL (Relocatable file)
  Machine:                           Advanced Micro Devices X86-64
  Version:                           0x1
  Entry point address:               0x0
  Start of program headers:          0 (bytes into file)
  Start of section headers:          800 (bytes into file)
  Flags:                             0x0
  Size of this header:               64 (bytes)
  Size of program headers:           0 (bytes)
  Number of program headers:         0
  Size of section headers:           64 (bytes)
  Number of section headers:         13
  Section header string table index: 12

Section Headers:
  [Nr] Name              Type             Address           Offset
       Size              EntSize          Flags  Link  Info  Align
  [ 0]                   NULL             0000000000000000  00000000
       0000000000000000  0000000000000000           0     0     0
  [ 1] .text             PROGBITS         0000000000000000  00000040
       0000000000000023  0000000000000000  AX       0     0     1
  [ 2] .rela.text        RELA             0000000000000000  00000258
       0000000000000048  0000000000000018   I      10     1     8
  [ 3] .data             PROGBITS         0000000000000000  00000063
       0000000000000000  0000000000000000  WA       0     0     1
  [ 4] .bss              NOBITS           0000000000000000  00000063
       0000000000000000  0000000000000000  WA       0     0     1
  [ 5] .rodata           PROGBITS         0000000000000000  00000063
       0000000000000020  0000000000000000   A       0     0     1
  [ 6] .comment          PROGBITS         0000000000000000  00000083
       000000000000002a  0000000000000001  MS       0     0     1
  [ 7] .note.GNU-stack   PROGBITS         0000000000000000  000000ad
       0000000000000000  0000000000000000           0     0     1
  [ 8] .eh_frame         PROGBITS         0000000000000000  000000b0
       0000000000000038  0000000000000000   A       0     0     8
  [ 9] .rela.eh_frame    RELA             0000000000000000  000002a0
       0000000000000018  0000000000000018   I      10     8     8
  [10] .symtab           SYMTAB           0000000000000000  000000e8
       0000000000000138  0000000000000018          11    10     8
  [11] .strtab           STRTAB           0000000000000000  00000220
       0000000000000037  0000000000000000           0     0     1
  [12] .shstrtab         STRTAB           0000000000000000  000002b8
       0000000000000061  0000000000000000           0     0     1
Key to Flags:
  W (write), A (alloc), X (execute), M (merge), S (strings), I (info),
  L (link order), O (extra OS processing required), G (group), T (TLS),
  C (compressed), x (unknown), o (OS specific), E (exclude),
  l (large), p (processor specific)

There are no section groups in this file.

There are no program headers in this file.

There is no dynamic section in this file.

Relocation section '.rela.text' at offset 0x258 contains 3 entries:
  Offset          Info           Type           Sym. Value    Sym. Name + Addend
000000000007  000500000002 R_X86_64_PC32     0000000000000000 .rodata + 17
00000000000e  000500000002 R_X86_64_PC32     0000000000000000 .rodata - 4
000000000018  000c00000004 R_X86_64_PLT32    0000000000000000 printf - 4

Relocation section '.rela.eh_frame' at offset 0x2a0 contains 1 entry:
  Offset          Info           Type           Sym. Value    Sym. Name + Addend
000000000020  000200000002 R_X86_64_PC32     0000000000000000 .text + 0

The decoding of unwind sections for machine type Advanced Micro Devices X86-64 is not currently supported.

Symbol table '.symtab' contains 13 entries:
   Num:    Value          Size Type    Bind   Vis      Ndx Name
     0: 0000000000000000     0 NOTYPE  LOCAL  DEFAULT  UND
     1: 0000000000000000     0 FILE    LOCAL  DEFAULT  ABS app.c
     2: 0000000000000000     0 SECTION LOCAL  DEFAULT    1
     3: 0000000000000000     0 SECTION LOCAL  DEFAULT    3
     4: 0000000000000000     0 SECTION LOCAL  DEFAULT    4
     5: 0000000000000000     0 SECTION LOCAL  DEFAULT    5
     6: 000000000000001b     5 OBJECT  LOCAL  DEFAULT    5 __func__.2249
     7: 0000000000000000     0 SECTION LOCAL  DEFAULT    7
     8: 0000000000000000     0 SECTION LOCAL  DEFAULT    8
     9: 0000000000000000     0 SECTION LOCAL  DEFAULT    6
    10: 0000000000000000    35 FUNC    GLOBAL DEFAULT    1 main
    11: 0000000000000000     0 NOTYPE  GLOBAL DEFAULT  UND _GLOBAL_OFFSET_TABLE_
    12: 0000000000000000     0 NOTYPE  GLOBAL DEFAULT  UND printf

No version information found in this file.
root@jenkins:~# 

```

Linker: The binary /usr/lib/gcc/x86_64-linux-gnu/7/collect2 acts as a linker. The linker takes the relocatable object file and creates an executable.


```
root@jenkins:~# gcc -o app.out app.o -v
Using built-in specs.
COLLECT_GCC=gcc
COLLECT_LTO_WRAPPER=/usr/lib/gcc/x86_64-linux-gnu/7/lto-wrapper
OFFLOAD_TARGET_NAMES=nvptx-none
OFFLOAD_TARGET_DEFAULT=1
Target: x86_64-linux-gnu
Configured with: ../src/configure -v --with-pkgversion='Ubuntu 7.5.0-3ubuntu1~18.04' --with-bugurl=file:///usr/share/doc/gcc-7/README.Bugs --enable-languages=c,ada,c++,go,brig,d,fortran,objc,obj-c++ --prefix=/usr --with-gcc-major-version-only --program-suffix=-7 --program-prefix=x86_64-linux-gnu- --enable-shared --enable-linker-build-id --libexecdir=/usr/lib --without-included-gettext --enable-threads=posix --libdir=/usr/lib --enable-nls --enable-bootstrap --enable-clocale=gnu --enable-libstdcxx-debug --enable-libstdcxx-time=yes --with-default-libstdcxx-abi=new --enable-gnu-unique-object --disable-vtable-verify --enable-libmpx --enable-plugin --enable-default-pie --with-system-zlib --with-target-system-zlib --enable-objc-gc=auto --enable-multiarch --disable-werror --with-arch-32=i686 --with-abi=m64 --with-multilib-list=m32,m64,mx32 --enable-multilib --with-tune=generic --enable-offload-targets=nvptx-none --without-cuda-driver --enable-checking=release --build=x86_64-linux-gnu --host=x86_64-linux-gnu --target=x86_64-linux-gnu
Thread model: posix
gcc version 7.5.0 (Ubuntu 7.5.0-3ubuntu1~18.04)
COMPILER_PATH=/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/:/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/
LIBRARY_PATH=/usr/lib/gcc/x86_64-linux-gnu/7/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../x86_64-linux-gnu/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../../lib/:/lib/x86_64-linux-gnu/:/lib/../lib/:/usr/lib/x86_64-linux-gnu/:/usr/lib/../lib/:/usr/lib/gcc/x86_64-linux-gnu/7/../../../:/lib/:/usr/lib/
COLLECT_GCC_OPTIONS='-o' 'app.out' '-v' '-mtune=generic' '-march=x86-64'
 /usr/lib/gcc/x86_64-linux-gnu/7/collect2 -plugin /usr/lib/gcc/x86_64-linux-gnu/7/liblto_plugin.so -plugin-opt=/usr/lib/gcc/x86_64-linux-gnu/7/lto-wrapper -plugin-opt=-fresolution=/tmp/ccuZ4OHn.res -plugin-opt=-pass-through=-lgcc -plugin-opt=-pass-through=-lgcc_s -plugin-opt=-pass-through=-lc -plugin-opt=-pass-through=-lgcc -plugin-opt=-pass-through=-lgcc_s --build-id --eh-frame-hdr -m elf_x86_64 --hash-style=gnu --as-needed -dynamic-linker /lib64/ld-linux-x86-64.so.2 -pie -z now -z relro -o app.out /usr/lib/gcc/x86_64-linux-gnu/7/../../../x86_64-linux-gnu/Scrt1.o /usr/lib/gcc/x86_64-linux-gnu/7/../../../x86_64-linux-gnu/crti.o /usr/lib/gcc/x86_64-linux-gnu/7/crtbeginS.o -L/usr/lib/gcc/x86_64-linux-gnu/7 -L/usr/lib/gcc/x86_64-linux-gnu/7/../../../x86_64-linux-gnu -L/usr/lib/gcc/x86_64-linux-gnu/7/../../../../lib -L/lib/x86_64-linux-gnu -L/lib/../lib -L/usr/lib/x86_64-linux-gnu -L/usr/lib/../lib -L/usr/lib/gcc/x86_64-linux-gnu/7/../../.. app.o -lgcc --push-state --as-needed -lgcc_s --pop-state -lc -lgcc --push-state --as-needed -lgcc_s --pop-state /usr/lib/gcc/x86_64-linux-gnu/7/crtendS.o /usr/lib/gcc/x86_64-linux-gnu/7/../../../x86_64-linux-gnu/crtn.o
COLLECT_GCC_OPTIONS='-o' 'app.out' '-v' '-mtune=generic' '-march=x86-64'
root@jenkins:~# 
```