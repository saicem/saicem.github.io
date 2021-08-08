# shell

## win

- [oh my posh](https://ohmyposh.dev/)

> 配置文件在 `$Home \ [My] 文档 \ PowerShell \Profile.ps1`

### 临时设置终端代理

#### CMD

> 好像不可行

```zsh
临时设置
set http_proxy=socks5://127.0.0.1:10808
set https_proxy=socks5://127.0.0.1:10808

如果有用户名和密码
set http_proxy_user=jake
set http_proxy_pass=abcd

取消设置
set http_proxy=
set https_proxy=
```

#### POWER SHELL

> 亲测可行

```bash
$env:https_proxy = "localhost:7890"
$env:http_proxy = "localhost:7890"
```

### 获取帮助

command /?

### net 命令

1. `net start` 查看已启动的服务
2. `net share` 查看当前用户下的共享目录
3. `net user` 查看当前机器上的用户

## zsh

- mac
- linux

### 改变用户默认shell

`/etc/passwd`

### bash 切换到 zsh 环境变量丢失

1. 在bash下面执行
`echo $PATH`
查看系统路径，复制路径。

2. 切换到zsh `sudo vim ~/.zshrc`
在 If you come from bash you might have to change your $PATH.下面添加刚才的路径
`export PATH=" you path copy just now "`

3. `source ~/.zshrc` 加载配置

- [on my zsh安装脚本](https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)

> 配置文件在 .zshrc

```zshrc
# Antigen: https://github.com/zsh-users/antigen
ANTIGEN="$HOME/.local/bin/antigen.zsh"

# Install antigen.zsh if not exist
if [ ! -f "$ANTIGEN" ]; then
 ANTIGEN="$HOME/.local/bin/antigen.zsh"
 echo "Installing antigen ..."

 [ ! -d "$HOME/.local" ] && mkdir -p "$HOME/.local" 2> /dev/null
 [ ! -d "$HOME/.local/bin" ] && mkdir -p "$HOME/.local/bin" 2> /dev/null
 [ ! -f "$HOME/.z" ] && touch "$HOME/.z"
 URL="http://git.io/antigen"
 TMPFILE="/tmp/antigen.zsh"
 if [ -x "$(which curl)" ]; then
  curl -L "$URL" -o "$TMPFILE" 
 elif [ -x "$(which wget)" ]; then
  wget "$URL" -O "$TMPFILE" 
 else
  echo "ERROR: please install curl or wget before installation !!"
  exit
 fi
 if [ ! $? -eq 0 ]; then
  echo ""
  echo "ERROR: downloading antigen.zsh ($URL) failed !!"
  exit
 fi;
 echo "move $TMPFILE to $ANTIGEN"
 mv "$TMPFILE" "$ANTIGEN"
fi


# Initialize command prompt
export PS1="%n@%m:%~%# "

# Enable 256 color to make auto-suggestions look nice
export TERM="xterm-256color"


# Load local bash/zsh compatible settings
_INIT_SH_NOFUN=1
[ -f "$HOME/.local/etc/init.sh" ] && source "$HOME/.local/etc/init.sh"

# exit for non-interactive shell
[[ $- != *i* ]] && return

# WSL (aka Bash for Windows) doesn't work well with BG_NICE
[ -d "/mnt/c" ] && [[ "$(uname -a)" == *Microsoft* ]] && unsetopt BG_NICE


# Initialize antigen
source "$ANTIGEN"


# Initialize oh-my-zsh
antigen use oh-my-zsh

# default bundles
# visit https://github.com/unixorn/awesome-zsh-plugins
# antigen bundle git
# antigen bundle heroku
antigen bundle pip
#antigen bundle svn-fast-info
# antigen bundle command-not-find

antigen bundle colorize
antigen bundle github
antigen bundle python
antigen bundle rupa/z z.sh
# antigen bundle z

antigen bundle zsh-users/zsh-autosuggestions
antigen bundle zsh-users/zsh-completions
antigen bundle zsh-users/zsh-syntax-highlighting
# antigen bundle supercrabtree/k
antigen bundle Vifon/deer

antigen bundle willghatch/zsh-cdr
antigen bundle zsh-users/zaw

# uncomment the line below to enable theme
# antigen theme fishy


# check login shell
if [[ -o login ]]; then
 [ -f "$HOME/.local/etc/login.sh" ] && source "$HOME/.local/etc/login.sh"
 [ -f "$HOME/.local/etc/login.zsh" ] && source "$HOME/.local/etc/login.zsh"
fi

# syntax color definition
ZSH_HIGHLIGHT_HIGHLIGHTERS=(main brackets pattern)

typeset -A ZSH_HIGHLIGHT_STYLES

# ZSH_HIGHLIGHT_STYLES[command]=fg=white,bold
# ZSH_HIGHLIGHT_STYLES[alias]='fg=magenta,bold'

ZSH_HIGHLIGHT_STYLES[default]=none
ZSH_HIGHLIGHT_STYLES[unknown-token]=fg=009
ZSH_HIGHLIGHT_STYLES[reserved-word]=fg=009,standout
ZSH_HIGHLIGHT_STYLES[alias]=fg=cyan,bold
ZSH_HIGHLIGHT_STYLES[builtin]=fg=cyan,bold
ZSH_HIGHLIGHT_STYLES[function]=fg=cyan,bold
ZSH_HIGHLIGHT_STYLES[command]=fg=white,bold
ZSH_HIGHLIGHT_STYLES[precommand]=fg=white,underline
ZSH_HIGHLIGHT_STYLES[commandseparator]=none
ZSH_HIGHLIGHT_STYLES[hashed-command]=fg=009
ZSH_HIGHLIGHT_STYLES[path]=fg=214,underline
ZSH_HIGHLIGHT_STYLES[globbing]=fg=063
ZSH_HIGHLIGHT_STYLES[history-expansion]=fg=white,underline
ZSH_HIGHLIGHT_STYLES[single-hyphen-option]=none
ZSH_HIGHLIGHT_STYLES[double-hyphen-option]=none
ZSH_HIGHLIGHT_STYLES[back-quoted-argument]=none
ZSH_HIGHLIGHT_STYLES[single-quoted-argument]=fg=063
ZSH_HIGHLIGHT_STYLES[double-quoted-argument]=fg=063
ZSH_HIGHLIGHT_STYLES[dollar-double-quoted-argument]=fg=009
ZSH_HIGHLIGHT_STYLES[back-double-quoted-argument]=fg=009
ZSH_HIGHLIGHT_STYLES[assign]=none

# load local config
[ -f "$HOME/.local/etc/config.zsh" ] && source "$HOME/.local/etc/config.zsh" 
[ -f "$HOME/.local/etc/local.zsh" ] && source "$HOME/.local/etc/local.zsh"

# enable syntax highlighting
antigen bundle zsh-users/zsh-syntax-highlighting

antigen apply

# setup for deer
autoload -U deer
zle -N deer

# default keymap
bindkey -s '\ee' 'vim\n'
bindkey '\eh' backward-char
bindkey '\el' forward-char
bindkey '\ej' down-line-or-history
bindkey '\ek' up-line-or-history
# bindkey '\eu' undo
bindkey '\eH' backward-word
bindkey '\eL' forward-word
bindkey '\eJ' beginning-of-line
bindkey '\eK' end-of-line

bindkey -s '\eo' 'cd ..\n'
bindkey -s '\e;' 'll\n'

bindkey '\e[1;3D' backward-word
bindkey '\e[1;3C' forward-word
bindkey '\e[1;3A' beginning-of-line
bindkey '\e[1;3B' end-of-line

bindkey '\ev' deer

alias ll='ls -lh'
# open file
alias -s gz='tar -xzvf'
alias -s tgz='tar -xzvf'
alias -s zip='unzip -O cp936'
alias -s bz2='tar -xjvf'
alias -s zst='tar -xvf'

# proxy
proxy_addr="http://127.0.0.1:7890"
alias proxyon="export ALL_PROXY=$proxty_addr;export all_proxy=$proxy_addr;export https_proxy=$proxy_addr;git config --global http.proxy $proxy_addr;git config --global https.proxy $proxy_addr"
alias proxyoff='unset ALL_PROXY;unset all_proxy;unset https_proxy;git config --global --unset http.proxy;git config --global --unset https.proxy'
#debian
alias aupdate='sudo apt update && sudo apt upgrade -y'

# locale
export LC_ALL=en_US.UTF-8  
export LANG=en_US.UTF-8

# path
export PATH=$PATH:~/.local/bin

# golang
export PATH=$PATH:$HOME/go/bin

# options
unsetopt correct_all

setopt BANG_HIST                 # Treat the '!' character specially during expansion.
setopt INC_APPEND_HISTORY        # Write to the history file immediately, not when the shell exits.
setopt SHARE_HISTORY             # Share history between all sessions.
setopt HIST_EXPIRE_DUPS_FIRST    # Expire duplicate entries first when trimming history.
setopt HIST_IGNORE_DUPS          # Don't record an entry that was just recorded again.
setopt HIST_IGNORE_ALL_DUPS      # Delete old recorded entry if new entry is a duplicate.
setopt HIST_FIND_NO_DUPS         # Do not display a line previously found.
setopt HIST_IGNORE_SPACE         # Don't record an entry starting with a space.
setopt HIST_SAVE_NO_DUPS         # Don't write duplicate entries in the history file.
setopt HIST_REDUCE_BLANKS        # Remove superfluous blanks before recording entry.
setopt HIST_VERIFY # Don't execute immediately upon history expansion.


# source function.sh if it exists
[ -f "$HOME/.local/etc/function.sh" ] && . "$HOME/.local/etc/function.sh"


# ignore complition
zstyle ':completion:*:complete:-command-:*:*' ignored-patterns '*.pdf|*.exe|*.dll'
zstyle ':completion:*:*sh:*:' tag-order files
```
