# Setup and Troubleshooting Guide

This guide covers the exact stack you asked about:
- WSL
- Python + IDLE
- Rust apps
- ngrok (`ngrok http 8080`)
- Zipping and sharing local "IP custody platform" builds

## 1) WSL (run on Windows PowerShell as Administrator)
```powershell
wsl.exe --list --online
wsl.exe --install Ubuntu
wsl.exe --set-default-version 2
wsl.exe --status
```

If `wsl.exe` is not found:
```powershell
Get-Command wsl.exe
Test-Path C:\Windows\System32\wsl.exe
```

Enable required features (then reboot):
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

## 2) Python + IDLE
Install Python from python.org (or Microsoft Store), then verify:
```powershell
python --version
python -m idlelib
```

## 3) Rust toolchain
Install with rustup:
```powershell
winget install Rustlang.Rustup
rustc --version
cargo --version
```

## 4) ngrok
Install:
```powershell
winget install Ngrok.Ngrok
ngrok config add-authtoken <YOUR_AUTHTOKEN>
ngrok version
```

Expose local port 8080:
```powershell
ngrok http 8080
```

## 5) Run local app on 8080 then tunnel
If your app isn't already listening on `:8080`, quick test server:
```powershell
python -m http.server 8080
```
Then in another terminal:
```powershell
ngrok http 8080
```

## 6) Zip and share local platform snapshot
From repo root:
```powershell
Compress-Archive -Path * -DestinationPath ip-custody-platform-local.zip -Force
```

## 7) Linux equivalents (inside WSL)
```bash
python3 --version
python3 -m idlelib -h
rustc --version
cargo --version
ngrok version
python3 -m http.server 8080
```
