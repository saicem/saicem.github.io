# PowerShell

```powershell
Import-Module posh-git
Import-Module oh-my-posh
Set-PoshPrompt -Theme wopian

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
    $env:https_proxy = "localhost:7980"
    $env:http_proxy = "localhost:7980"
}

function proxyoff {
    $env:https_proxy = ""
    $env:http_proxy = ""
}

# Set-Alias -Name workspace -Value "Set-Location ~/workspace"
```