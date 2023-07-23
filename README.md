## Trust GBO Systems Code Signing Certificate

```powershell
## Paste this into an Administrator PowerShell window
$dir = [System.IO.Path]::GetTempPath()
$url = "https://github.com/gbosystems/cert/raw/main/gbo-systems-code-signing.cer"
$file = Join-Path -Path $dir -ChildPath "gbo-systems-code-signing.cer"

Invoke-WebRequest -Uri $url -OutFile $file

Import-Certificate -FilePath $file -CertStoreLocation Cert:\LocalMachine\Root
Import-Certificate -FilePath $file -CertStoreLocation Cert:\LocalMachine\TrustedPublisher

Remove-Item -Path $file
```
