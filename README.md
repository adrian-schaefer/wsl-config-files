### .bashrc
alias cat='/bin/batcat'  
alias catn='/bin/cat'  
alias catnl='/bin/batcat --paging=never'  
alias ll='lsd -lh --group-dirs=first'  
alias la='lsd -a --group-dirs=first'  
alias l='lsd --group-dirs=first'  
alias lla='lsd -lha --group-dirs=first'  
alias ls='lsd --group-dirs=first'  

alias firefoxd='firefox >/dev/null 2>&1 &'  
alias burpsuited='burpsuite >/dev/null 2>&1 &'  

function infoPorts()  
{  
&emsp;        ports="$(cat $1 | grep -oP '\d{1,5}/open' | awk '{print $1}' FS='/' | xargs | tr ' ' ',')"  
&emsp;        ip_address="$(cat $1 | grep -oP '\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}' | sort -u | head -n 1)"  
&emsp;        echo -e "\n[*] Extracting information...\n" > infoPorts.tmp  
&emsp;        echo -e "\t[*] IP Address: $ip_address"  >> infoPorts.tmp  
&emsp;        echo -e "\t[*] Open ports: $ports\n"  >> infoPorts.tmp  
&emsp;        cat infoPorts.tmp; rm infoPorts.tmp  
}  

function mkt()  
{  
&emsp;        mkdir {nmap,content,exploits}  
}  

### .tmux.conf
set -g mouse on  
set-option -g history-limit 9000  
set-option -g allow-rename off  
