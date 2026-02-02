# crto-notes

# RTO Infrastructure 

- ### Redirectors
	- ### HTTP Redirectors

[High-reputation Redirectors & Domain Fronting](https://www.cobaltstrike.com/blog/high-reputation-redirectors-and-domain-fronting)

![http_proxy](https://www.cobaltstrike.com/app/uploads/2023/01/df_http_noproxy2.png)

![proxy_http_redirect](https://www.cobaltstrike.com/app/uploads/2023/01/df_https_withproxy.png)



[Empire Domain Fronting with Microsoft Azure](https://truneski.github.io/blog/2019/02/27/empire-domain-fronting-with-microsoft-azure/)

![redirector2empire](https://truneski.github.io/post/images/domain-fronting/wireshark.png)

- ### Redirectors
	- ### DNS Redirectors


[Socat UDP Redirector](https://www.cobaltstrike.com/blog/simple-dns-redirectors-for-cobalt-strike)

`socat -T 5 udp4-listen:53,fork udp4:teamserver.example.net:53`


## Beacons

### HTTP & HTTPS Beacons

[HTTP & HTTPS Beacons - Cobalt Strike Manual](https://hstechdocs.helpsystems.com/manuals/cobaltstrike/current/userguide/content/topics/listener-infrastructue_beacon-http-https.htm)
## Listeners

[Redops.at - Cobalt Strike CDN/Reverse Proxy Listener Setup](https://redops.at/en/blog/cobalt-strike-cdn-reverse-proxy-setup)

 ### DNS Listeners
[Redops.at - Cobalt Strike DNS Listeners](https://redops.at/en/blog/cobalt-strike-dns-listener)
# Weaponization
## Miscellaneous
[Microsoft Learn - PowerShell - Running Remote Commands](https://learn.microsoft.com/en-us/powershell/scripting/security/remoting/running-remote-commands?view=powershell-7.5&viewFallbackFrom=powershell-7.1)

[Session-contained PowerShell One-Liner - Cobalt Strike 4.0](https://m.youtube.com/watch?v=dNC5HKwmbyI&time_continue=22&source_ve_path=NzY3NTg&embeds_referring_euri=https%3A%2F%2Fwww.cobaltstrike.com%2F)

[Cobalt Strike 4.0 - Bring Your Own Weaponization](https://www.cobaltstrike.com/blog/cobalt-strike-4-0-bring-your-own-weaponization)

[Offensive PowerShell - Fighting the Toolset - Cobalt Strike (2018)](https://www.cobaltstrike.com/blog/fighting-the-toolset)

## Process Injection

[Direct vs Indirect Syscalls](https://redops.at/en/blog/direct-syscalls-vs-indirect-syscalls)

[Cobalt Strike Beacon - Windows System Calls](https://hstechdocs.helpsystems.com/manuals/cobaltstrike/current/userguide/content/topics/post-exploitation_system-calls.htm)

[Core Security - Creating Processes Using System Calls](https://www.coresecurity.com/core-labs/articles/creating-processes-using-system-calls)

[DLL Injection](https://www.ired.team/offensive-security/code-injection-process-injection/dll-injection)

[CreateProcessW](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) - create a process that will have the same access token as the caller 

[CreateProcessAsUserW](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) - create a process using an alternate access token

[CreateProcessWithLogonW](https://learn.microsoft.com/en-us/windows/win32/api/winbase/nf-winbase-createprocesswithlogonw) - create a process using a user's plaintext credentials

Ultimately, each API calls into the NtCreateUserProcess kernel function.

# Post-Exploitation

## Command Obfuscation 

### base64 encoding

```
$command = 'cmd /C cmdkey /list' ; $bytes = [System.Text.Encoding]::Unicode.GetBytes($command) ; $encodedCommand = [Convert]::ToBase64String($bytes) ; Write-Output $command ; Write-Output $encodedCommand
```

## Useful Windows Shell Commands

[Windows: List Services – CMD & PowerShell](https://www.shellhacks.com/windows-list-services-cmd-powershell/)
[Manual Enumeration - Windows Privilege Escalation](https://juggernaut-sec.com/manual-enumeration/)
### Stored Credentials

```
cmd /C cmdkey /list
```

### User Groups

```
whoami /groups
```

### User Privileges

```
whoami /priv
```
# Pivoting

## DNS & HTTP Pivoting

[DNS & HTTP Pivoting with Cobalt Strike’s Beacon](https://m.youtube.com/watch?v=yt7xC1-h9ec)



