# Diagnostic command reference

These are optional examples for related support work, not a transcript of commands used in the published tickets. Use an authorised environment and the appropriate permissions. No command output is claimed here.

## Review a mailbox’s automatic-reply settings

In an authenticated Exchange Online PowerShell session with suitable permissions, replace the placeholder with the verified mailbox identity:

```powershell
Get-MailboxAutoReplyConfiguration -Identity 'user@example.com' |
    Select-Object AutoReplyState,StartTime,EndTime,ExternalAudience
```

This inspects configuration; it does not prove that a recipient received a reply. Follow with controlled internal and external tests as appropriate. Reference: [Microsoft command documentation](https://learn.microsoft.com/en-us/powershell/module/exchange/get-mailboxautoreplyconfiguration).

## Inspect current Windows processes and audio services

```powershell
Get-Process | Sort-Object CPU -Descending |
    Select-Object -First 10 ProcessName,Id,CPU,WorkingSet64
Get-Service -Name Audiosrv,AudioEndpointBuilder
```

CPU is cumulative process CPU time, not current CPU utilisation. These commands provide context; they do not identify a performance root cause or prove that sound reaches the selected output device.

## Inspect connectivity

```powershell
Get-NetIPConfiguration
Get-DnsClientServerAddress
# Replace with the approved service hostname.
Test-NetConnection 'service.example.com' -Port 443
```

A successful TCP connection does not prove that authentication, TLS negotiation or the application is working. Capture the actual error and use the service’s own diagnostics as well. Reference: [Microsoft Test-NetConnection documentation](https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection).
