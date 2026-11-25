One-click install for codeagent
```powershell
$s = "$env:USERPROFILE\.cac\skills"
Rename-Item "$s\prompt-optimizer" ("prompt-optimizer.bak-" + (Get-Date -Format 'yyyyMMdd-HHmm'))
git clone https://github.com/shiho-qiao/prompt-optimizer.git "$s\prompt-optimizer"
```
The optimized prompt body is written in English, and the output language is locked to the language used to invoke the skill.
