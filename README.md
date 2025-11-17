# PHP 7.2.34 - Session Upload Progress RCE Exploit

> Critical Remote Code Execution via PHP Session Upload Progress + LFI  
> Discovered & coded by @spyizxa_0day  
> Telegram: @siberdirenis

## Vulnerability
Combines:
- `session.upload_progress.enabled = On` (default)
- Predictable session file path (`/var/lib/php/sessions/sess_[PHPSESSID]`)
- Local File Inclusion (LFI) vulnerability in the target app

Allows attacker to write arbitrary PHP code into own session file and execute it via LFI.

Works on PHP 7.0 - 7.2.34 (and sometimes 7.3/7.4 with default config).

## Usage
```bash
python3 exploit.py
[+] please enter URL: http://vulnerable-site.com/upload.php
