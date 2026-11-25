codeagent 一键安装
```powershell
$s = "$env:USERPROFILE\.cac\skills"
Rename-Item "$s\prompt-optimizer" ("prompt-optimizer.bak-" + (Get-Date -Format 'yyyyMMdd-HHmm'))
git clone https://github.com/shiho-qiao/prompt-optimizer.git "$s\prompt-optimizer"
```
