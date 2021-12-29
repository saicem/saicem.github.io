# PowerShell

```powershell
Import-Module posh-git
Import-Module oh-my-posh
Import-Module ZLocation
Set-PoshPrompt -Theme wopian
# 设置命令预测
Set-PSReadLineOption -PredictionSource History # 设置预测文本来源为历史记录
Set-PSReadlineKeyHandler -Key Tab -Function Complete # 设置 Tab 键补全
Set-PSReadLineKeyHandler -Key "Ctrl+d" -Function MenuComplete # 设置 Ctrl+d 为菜单补全和 Intellisense
Set-PSReadLineKeyHandler -Key "Ctrl+z" -Function Undo # 设置 Ctrl+z 为撤销
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward # 设置向上键为后向搜索历史记录
Set-PSReadLineKeyHandler -Key DownArrow -Function HistorySearchForward # 设置向下键为前向搜索历史纪录

function cdwk ($target = "saicem") {
    if ($target -eq "saicem") {
        Set-Location ~/workspace/github.com/saicem
    }
    elseif ($target -eq "r") {
        Set-Location ~/workspace/project/R
    }
    else {
        Set-Location ~/workspace/$target
    }
}

function blog {
    cdwk && code ./saicem.github.io/
}

function cdsrc {
    Set-Location ~/go/src
}

function ssha ($name = "saicem") {
    "ssh $name@saicem.top"
    ssh $name@saicem.top
}

function proxyon {
    # "set http_proxy=http://127.0.0.1:1080"
    $env:https_proxy = "https://localhost:7980"
    $env:http_proxy = "http://localhost:7980"
}

function proxyoff {
    $env:https_proxy = ""
    $env:http_proxy = ""
}

# Set-Alias -Name workspace -Value "Set-Location ~/workspace"
```
