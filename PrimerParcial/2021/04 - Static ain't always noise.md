# Static ain't always noise

## Descripcion Reto
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static)? This [BASH script](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh) might help!

## Pistas
1. 

## Solución
```bash
ajhagaal-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh
--2023-03-05 00:28:06--  https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                    100%[========================================>]     785  --.-KB/s    in 0s      

2023-03-05 00:28:06 (481 MB/s) - 'ltdis.sh' saved [785/785]

ajhagaal-picoctf@webshell:~$ ls
README.txt  decode  file  flag  ltdis.sh  netcat  warm
ajhagaal-picoctf@webshell:~$ cat ltdis.sh 
#!/bin/bash



echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by 
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
        echo "Disassembly failed!"
        echo "Usage: ltdis.sh <program-file>"
        echo "Bye!"
fi
ajhagaal-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static
--2023-03-05 00:30:35--  https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                      100%[========================================>]   8.18K  --.-KB/s    in 0s      

2023-03-05 00:30:35 (153 MB/s) - 'static' saved [8376/8376]

ajhagaal-picoctf@webshell:~$ ls
README.txt  decode  file  flag  ltdis.sh  netcat  static  warm
ajhagaal-picoctf@webshell:~$ cat static 
 HH/lib64/ld-linux-x86-64.so.2GNUGNUFŋ|@>1FbY] 
                                               Y h "libc.so.6puts__cxa_finalize__libc_start_mainGLIBC_2.2.5_I       HisterTMCloneTable__gmon_start___ITM_registerTMCloneTableui      1
 Ht5
 %
 @%
 h%
8#TT 1tt$DN
 @@ 0@)pp V``^okyajhagaal-picoctf@webshell:~$ 
 UH
 H9HtHZ
]f.]@f.H=
 H5
 UH)HHHH?HHtH!
 Ht
   ]f]@f.=I
 u/H=    UHt
H!          H=   
 ]fDUH]fUHH=]f.DAWAVIAUATL%F UH-F SAIL)HWHt 1LLDAHH9u[]A\A]A^A_Ðf.Oh hai! Wait what? A flag? Yes, it's around here somewhere!8
                 T<,zRx
                      Rx
                        FJ
R                         ?;*3$"D\JAC
D|PeBBE B(H0H8M@r8A0A(B BBx0
o`

 picoCTF{d15a5m_t34s3r_ccb2b43e}GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.08Tt`


   @ 
 $  k  1C@ Ji v `eH o0+@ :@     "
                                 crtstuff.cderegister_tm_clones__do_global_dtors_auxcomp
ajhagaal-picoctf@websh
ajhagaal-picoctf@webshell:~$ ntryframe_dummy__frame_dummy_init_array_entrystatic.c__FRAME_END____init_array_end_DYNAM
ajhagaal-picoctf@webshell:~$ strings static 
/lib64/ld-linux-x86-64.so.2
>1FbY]
libc.so.6
puts
__cxa_finalize
__libc_start_main
GLIBC_2.2.5
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
AWAVI
AUATL
[]A\A]A^A_
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
;*3$"
picoCTF{d15a5m_t34s3r_ccb2b43e}
GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0
crtstuff.c
deregister_tm_clones
__do_global_dtors_aux
completed.7698
__do_global_dtors_aux_fini_array_entry
frame_dummy
__frame_dummy_init_array_entry
static.c
__FRAME_END__
__init_array_end
_DYNAMIC
__init_array_start
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
puts@@GLIBC_2.2.5
_edata
__libc_start_main@@GLIBC_2.2.5
__data_start
__gmon_start__
__dso_handle
_IO_stdin_used
__libc_csu_init
__bss_start
main
__TMC_END__
_ITM_registerTMCloneTable
flag
__cxa_finalize@@GLIBC_2.2.5
.symtab
.strtab
.shstrtab
.interp
.note.ABI-tag
.note.gnu.build-id
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rela.dyn
.rela.plt
.init
.plt.got
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.dynamic
.data
.bss
.comment
ajhagaal-picoctf@webshell:~$ strings static | grep picoCTF
picoCTF{d15a5m_t34s3r_ccb2b43e}
ajhagaal-picoctf@webshell:~$ 
```

## Bandera
* picoCTF{d15a5m_t34s3r_ccb2b43e}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| strings | Escribe los caracteres legibles en un archivo |

## Referencias
- []()