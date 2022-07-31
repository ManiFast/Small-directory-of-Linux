# List_of_commands                       
List of my frequent Linux terminal commands (updating every two days)</br>
I think in near future I write a small book for Linux like "A little about Linux in many ways !"</br>

# Table of Contents:
- [<b>Main</b>](#main)
  - [Commands](#commands)
  - [Logs](#logs)
  - [Input text in file](#input_text_in_file)
  - [Users and groups](#users)
  - [Archiving](#archiving)
  - [Compression](#compression)
  - [Compiling](#compiling)
- [<b>BASH scripting</b>](#bash_scripting)
- [<b>Hot keys</b>](#keys)
- [<b>Software</b>](#software)
  - [VIM](#vim)
    - [Macros](#macros)
    - [Config VIM](#config)
  - [||| Metasploit |||](#metasploit)
    - [Search Email Collector](#search_email_collector)
    - [Inbuilt nmap](#inbuilt_nmap)
    - [Find auxiliary for certain ports (table)](#find_auxiliary_for_ports)
  - [NMAP](#nmap)
    - [ZENMAP](#zenmap)
  - [DIRB](#dirb)
  - [SCRCPY](#scrcpy)
  - [GHOST](#ghost)
  - [MacChanger](#macchanger)
  - [Proxychain](#proxychain)
  - [AutoTor](#auto_tor)
  - [Extracting information from metadata](#extract_info)
    - [ExifTool](#exiftool)
    - [MetaGooFil](#metagoofil)
  - [Find information about emails](#info_of_emails)
    - [theHarvester](#theharvester)
    - [Search Email Collector](#search_email_collector)
    - [Maltego](#maltego)

- [<b>Root</b>](#root)
- [<b>Permission</b>](#permisson)

- [<b>Shared folder</b>](#shared_folder)
- [<b>Update Linux (Kali)](#update)
- [<b>SSH</b>](#ssh)
  
- [<b>Features</b>](#features)
  - [<b>APT remove</b>](#apt-remove)
  
  - [<b>Tricks</b>](#tricks)
---
## Main
### Commands
`!$`    last argument (напр mkdir ss/sdf)</br>
`!!`    previous comand</br>
`Super+Space`     change language keyboard</br>
`ls`     show files and folders</br>
  `ls -l -a`        -l beauti   -a  all files</br>
`touch`     create file</br>
`cd`       previous path</br>
`cat`    output file</br>
`vim`    change file</br>
`htop`     about system</br>
`ps`    what running</br>

`mkdir (-p)`      create dir, p-if that dir isnt found, create !</br>
`rmdir`    remove dir</br>
`rm -R`     remove not empty dir</br>

`mv`    rename or move</br>
`wc`    word count</br>
  `wc file.txt -l/w`     show lines or words in file </br>
  `grep "[A-Za-z]*stas" -E ./*`  example, find ...s/Stas in this folder
`sort`   sort to symbols without change</br>
  `sort -n`    sort by names</br>

`cut -d ">" -f 3 file.txt`   divorse each column on end ">" and output only third lines in file.txt</br>
  `cut -d ">" -f 3 countries.txt | sort -n`   example of sorting</br>


`find`     find file</br>
  `find /home -name "file*.txt"`</br>

`grep <-i> <word> <file/path>`   find in folders or files, 'i' = ignore case count Aa</br>
  `grep -E  "@[A-Za-z]*.com" file.txt`       find certain fraze in file</br>
  `grep "[A-Za-z0-9]*@gmail.com" email.txt`  example, find all email in end @gmail.com</br>
   [A-Z] [a-z] [0-9] @ _ - . </br>

`ln`       links (like shortcut)</br>
  `ln -s /home/Desktop/Dir`      link to folder</br>
  `ln /home/Desktop/file.txt`   create duplicate of file</br>


`date`    show date (with args)</br>
  `date +"%H:%M"`  11:32</br>
  
`> >>` clear and rewrite/just write in end</br>
`2>` catch errors</br>
  `grep cats animals/* 2> errors.txt` find strings with word 'cats' in all files in folder 'animals' and errors write in 'errors.txt' file</br>
  `grep aqua colors/* > good.txt 2> nogood.txt` write noerrors msg in 'good.txt' and errors msg in nogood.txt</br>
  `/dev/null` always empty folder, like 'black hole')</br>
  `2>>` add errors in file, like '>>'</br>
`&>` catch errors and noerrors messages (because if you write '>' saving only noerrors messages)</br>
 
 `bg` show background process</br>
 `fg` return to background</br>
 
 `top` task manager</br>
 `ps` list of procces</br>
    `ps -aux` show all in all</br>
    ps -aux | grep manifast    find strings with this word</br>
 
  `whoami` what user</br>
 `id` which groups u consist</br>
    `id root` show id root</br>
    
  `last` who enter in pc</br>
  `who` who now use pc</br>
  `w` what all users do</br>
  
  `su` <user> change user</br>
  
  `locate <app>` where is program locate</br>
  
  
  
  
  -------------------------------------------------------------------------------------------------------------
  
  
  
  
 
 ### Logs
 
 `/var/log` logs</br>
 `sudo dmesg` log of Linux core</br>
 `/etc/passwd` system accaunts</br>
 `/etc/shadow` all shifered passwords</br>
 `/etc/group`  all users groups (f.e how can use sudo)</br>
 
  
### Input_text_in_file
  1) `cat > file.txt << ENDL`</br>    '>' its write in end ENDL its special word witch means end of line (random word)</br>
  2) `printf "text" > file.txt`</br>
  

### Users
`useradd -m` <name> add user (with home directory)</br>
`userdel -r` <name> delete user (with home)</br>

`/etc/skel` templete of home directory</br>
`passwd` <user> change password for user</br>

`groupadd` <name> create group in /etc/group</br>
`groupdel` <name> delete group</br>
 
 `usermod -aG` <group> <user> add user to group</br>
 `deluser` <user> <group> delete user from group</br>

### Archiving
tar using without "-"
`tar cvf <name.tar> <folder>` create archive (c - create, v - view, f - must be in end)</br>
  tar cvf data.tar dataBig/</br>
`tar xvf <name.tar>` extract archive (x - unzip)</br>
  tar xvf data.tar</br>
  `tar -C <path> -xvf <file>` extract to considered folder (C - path)</br>
      tar -C home/ -xvf data.tar</br>
`tar tf <name.tar>` view what in tar (t - test)</br>

### Compression
Compressing one file, (for example compress one big tar)</br>
1) gzip <b>.gz</b></br>
`gzip <tar file/or 1 big file>` zip</br>
  gzip myData.tar</br>
`gunzip` unzip</br>

2) bzip2 <b>.bz2</b> - best</br>
`bzip2 <file>` zip</br>
  bzip2 myData.tar</br>
`bunzip2 <file>` unzip</br>

3) xz <b>.xz<b></br>
`xz <file>` zip</br>
  xz myData.tar</br>
`unxz <file>` unzip</br>

4) zip
`zip -r <file.zip> <folder>` zip folder (r - recorsvely) with beauti adding
    zip -r data.zip bigData/
 `unzip <file.zip>` unzip
    unzip data.zip

All in 1 command:</br>
tar - can make compression too</br>

Archiving and compression:</br>
`tar cvzf <file.gz> <folder>` to .gz (z - create gzip)</br>
`tar cvjf <file.bz2> <folder>` to .bz2 (j - create bzip2)</br>
`tar cvJf <file.xz> <folder>` to .xz (J - create xz)</br>

Uncompression archving tar:</br>
`tar xvf <file.bz/.bz2/xz>` Uncompression archving .bz</br>
  tar xvf myData.bz2

### Compiling
`gcc file.c -o file`        compiling output for C file</br>
`g++ file.c -o file`        compiling uutput for C++ file</br>

`make file`          gcc file.c -o file</br>
`./file`    run file</br>


</br>

## Bash_scripting
`var="string"`       create valuable</br>
`read` <var>         like "cin»var", write in value</br>
`var=$1/2`                 AKA Argument,      ./file $1</br>
`daytoday=$(date +"%D")`        example of pasting output command</br>


</br>

## Keys
`^`    Its Ctrl</br>
`^A ^E`   go to start or end </br>
`^R`         finding commands</br>
`^U`        clear what written on left</br>
`^M`       new line</br>

`^Shift+V`              paste text</br>
`^Shift+Insert`      paste text too :D</br>

`^h` show hidden files

</br>










---------------------------------------------------------------------------------------------


## Software

### Vim
`^:`    open vim command line</br>
`!`   extra ...  !q extra quit</br>
`w`   save</br>
`q`   quit</br>
`:%s/WORD/REPLEACEWORD/g`   find and replace (g - all)</br>

`ESC` NORMAL mode</br>
`i` INSERT mode</br>
`v` VISUAL mode</br>

`h j k l` left down up right</br>
`a` INSERT after 1 letter</br>
`A` INSERT in end of line</br>
`o` new line in down and INSERT</br>
`O` new line in up and INSERT</br>

`gg` go to start of file</br>
`G` go to end of file</br>

`w` ahead word</br>
`b` back word</br>

<number>`w` go to 10 word ahead</br>

`/` find word (<b>down</b> from cursor)</br>
  /555</br>
`?` find word (<b>up</b> from cursor)</br>
 
`m`<name> set marker (;'\ жэ\)</br>
  mfirst</br>
`'`<name> go to marker</br>
  'first</br>

in VISUAL mode:</br>
`x` cut text</br>
`p` paste text</br></br></br>
`d` delete</br>
 

`dd` delete line</br>
  5dd - delete 5 lines</br>
`dw` delete word</br>

`u` like ^Z (back)</br>

`cw` delete all to right in word (change word)</br>
`C` delete all to right

 ### Macros
 `q`<name> start to listen what you do</br>
 `q` stop listen</br>
 `@`<name> do macros</br>
  `10@mac` - do ten times</br>
 
 ### config
 [My cfg here](https://github.com/ManiFast/Linux_Config_Backup/blob/main/.vimrc)</br>
 
 `sudo vim ~/.vimrc`
 
</br>
  
  
### metasploit
<b>Exploit<b> - код для уязвимости</br>
<b>Payload</b> - устанавливает соединение, выполняет скрипты)</br>
  Sigles - Самостоятельный файл (объединяет два модуля)</br>
  Stagers - Устанавливает связь с атакующим и загружает Stager</br>
  Stages - Выполняет основное действие: похищение паролей, загрузка backdoor'а и тд</br>
<b>Post</b> -  запускается после успешного проникновения (кейлоггер, скачивает файлы)</br>
<b>Encoder</b> - маскировка от антивирусов</br>

<b>NOP</b> - заполняет пустоту в исполняемых файлах</br>
<b>Auxiliary</b> - модули для сканирование сети анализа трафика</br>

—-
Open in command:</br>
`sudo msfdb init && msfconsole`</br>
`msfconsole`</br>

Update:</br>
`msfupdate`</br>
  
Конфиг (там где пароли)</br>
<b>/usr/share/metasploit-framework/config</b></br>

`db_status` show what <b>DB (DataBase)</b> is turn on</br>
`db_disconect` disconnect DB</br>
`db_connect -y` </usr/share/metasploit-framework/config/database.yml> connect DB with path</br>
  
`help`
`workspace` show list of tabeles (projects)</br>
  `workspace -a <name>` add new table</br>
  `workspace -d <name>` delete table</br>
  `workspace -D` delete all</br>
`workspace <name>` switch to table</br>
 
 `db_import <path>` import tables .xml (from nmap scans)</br>
 `db_export <path>`
 
 `hosts` show all hosts: ip, MAC and type OC</br>
  `hosts -S <word>` find in hosts</br>
 `services` show all services (from .xls files, show all open ports)</br>
  `services -S` find in services</br>
 `notes` more info from scaning ports (results)</br>
 
 `vulns` list of vulnerability (уязвимость)</br>
 `loot` save dump hash memory (I dnt know)</br>
 `analyze` analyze DB for all ip</br>
 
 `search type:<exploit> <find>` search exploits</br>
   `search type:auxiliary ms17`</br>
 `use auxiliary/<exploit-path>` use</br>
   `use auxiliary/scanner/smb/smb_ms17_010`</br>
   
 `show options`</br>
 `info`</br>
 
**RPORT** - port wich exploit will attack</br>
**RHOSTS** - target ip (must be set)</br>
    `set rhosts <ip>` - set target ip</br>
 U can set rhosts in start, without every time set into exploit</br>
    
 [+] - vulnerable</br>
 [\*] - No</br>
 
  
#### search_email_collector
Start Metasploit</br>
`use auxiliary/gather/search_email_collector` open</br>
`show options` help</br>
  
  
#### inbuilt nmap
`help db_nmap` help</br>

`db_nmap -A <ip> -v` (-v see result)</br>
  `db_nmap -A 192.168.0.106 -v`</br>
  
#### find_auxiliary_for_ports  

<table>
  <tr>
    <td>Ports</td>
    <td>path</td>
    <td>name</td>
    <td>sense</td>
  </tr>
  <tr>
    <td>80</td>
    <td>auxiliary/dos/https/wordpress_xmlrpc_dos</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>135</td>
    <td></td>
    <td></td>
    <td>Read and do commaands</td>
  </tr>
  <tr>
    <td>137</td>
    <td></td>
    <td></td>
    <td>Searching info in other PC's</td>
  </tr>
  <tr>
    <td>139</td>
    <td></td>
    <td></td>
    <td>Remote control</td>
  </tr>
  <tr>
    <td>445</td>
    <td>auxiliary/scanner/msb/msb_ms17_010</td>
    <td>MS17</td>
    <td>Shared files</td>
  </tr>
  <tr>
    <td>3389</td>
    <td>auxiliary/scanner/rdp/ms12_020_check</td>
    <td>oRDP</td>
    <td></td>
  </tr>
  <tr>
    <td>2001</td>
    <td>auxiliary/dos/http/monkey_headers</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>3128</td>
    <td>auxiliary/dos/http/squid_range_dos</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>8080</td>
    <td>auxiliary/dos/http/cable_haunt_websocket_dos</td>
    <td></td>
    <td></td>
  </tr>
  
  
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</table>

**Features of auxiliary:**</br>
auxiliary/scanner/portscan/tcp - a tcp port scan (set THREADS 50)</br>


  
  
  
  
  
  
  
  
### nmap
NMAP - scananig all ports and do pings</br>
nmap - опции адрес</br>

Options:</br>
<img width="550px" height="300px" src="https://user-images.githubusercontent.com/62830326/178114474-727049dd-e106-4dbe-bb8c-4b1b7203286d.png"></br>
  
`--reason` what recive nmap from remote system</br>
`-p 0-65535` scanning all ports</br>
`-oX <path>` save to file</br> 
`-A` for find OC</br>
`-iL` scan ports in txt file</br>
`-oN` write output in txt file</br>
`-v` show more info</br>
  
if open port:</br>
`_http-generator: ` find port with access in web site</br>
5000/tcp open     tcpwrapped    syn-ack ttl 64</br>
 
example:</br>
`sudo nmap -A --reason <ip> -oX <path>.xml`</br>

`sudo nmap -A --reason -v 192.168.0.106 -p 0-54535 -oX /home/manifast/Desktop/scan.xml`</br>
  
#### zenmap
I dont know how you can be such a pervert to use this piece ...</br>


### dirb
Scanner web-content</br>
Show hidden paths, files and adresses in url</br>

`n` go to next directory</br>
`a` stop scanning (save stage)</br>
`r` save statistics of scanning</br>
  
Options:</br>
<img width="600px" height="250px" src="https://user-images.githubusercontent.com/62830326/181817742-1c232161-10c0-465b-b07a-e7372898aefa.png"></br>
 
Examples of starting DIRB:</br>
`dirb http://nwcom.info/ -o ~/Desktop/DIRB_scan.txt`</br>
`dirb <url>/directory` simple test</br>
`dirb <url> -X .html` testing files with suffics '.html'</br>
`dirb <url> /usr/share/dirb/wordlists/vulns/apache.txt` testing with list of words from file 'apache.txt'</br>
`dirb <url>/secure_url` simple test with SSL</br>

  
  
  
### scrcpy
SCRCPY Framework using for remote controle and emilate touches with output live divese</br>
dont forget turn on usb connection in VBox if u use -d, (USB/Wireless)</br>

site for help find ip https://www.shodan.io/ in search "android debug bridge"</br>

`adb devices` show all devices</br>

`adb connect <ip>:<port>` connecting</br>
`scrcpy -St` cocntroll (Screen hide, touches)</br>
  `scrcpy -d` (use usb)</br>
  `scrcpy -e` (use TCP/IP device)</br>

`adb kill-server` kill port, if failed to connect</br>
`adb tcpip <port 9999>` create port</br>


`adb forward --list serial "" local "" remote ""` ?</br>
`adb logcat` ? View device log</br>

adb get-state</br>
 Prints: offline | bootloader | device</br>
  
  
  
### ghost
GHOST Framework using for fast remote connecting to divece and share files and do screenshots</br>
after ghost if connction successeful better use SCRCPY Framework :D</br>

`connect <ip>`</br>
`help`</br>
  
### macchanger
MacChanger using for generate fake MAC adress.</br>

`sudo macchanger -A <eth0>` set random MAC</br>

`sudo macchanger -a <eth0>` set fake MAC</br>
`sudo macchanger -r <eth0>` set fully random MAC</br>
  
### proxychains
path `locate proxychains`</br>
    `sudo vim etc/proxychains.conf`</br>

### auto_tor
Change IP</br>

`git clone https://github.com/FDX100/Auto_Tor_IP_changer.git`</br></br>
`python3 install.py`</br>
`python3 autoTOR.py`</br>
 60</br>
 100</br>
  
  
### extract_info
#### exiftool
Using for showing all info of file (meta). For ex. find name of creator.<br>

`sudo apt-get install exiftool` - install</br>

`exiftool <file path>` start</br>

#### metagoofil
Using for download all file from site.</br>

`sudo apt-get install metagoofil` - install</br>

`metagoofil -d <site> -l 10 -n 10 -t <.type> -o <save path>` start, -l limit, download files limit, -t type of file, -s where save.</br>

example:</br>
`metagoofil -d it-black.ru -l 10 -n 10 -t pdf,dox,xml,xls,docx -o /home/manifast/Desktop/`</br>
  
### info_of_emails
#### theharvester
Find emails in domen.</br>

`theHarvester -d <domain> -l <count> -f <save path>` </br>
  `theHarvester -d mail.ru -l 500 -f google -f /home/manifast/Desktop/file` example</br>
  
#### search_email_collector
Start Metasploit</br>
`use auxiliary/gather/search_email_collector` open</br>
`show options` help</br>
  
#### Google Hacking
Use for find login page or enother info</br>

[Pentest-tools site](https://pentest-tools.com/information-gathering/google-hacking)</br>
  
#### Maltego

  
  
  
  
  
  
  
  ------------------------------------------------------------------------------------------
  
## Root
`sudo su`</br>
`sudo -i`</br>

## Permisson
1</br>
`sudo chown` <user> <file/folder></br>
  
2 (for all users)</br>
`sudo su`</br>
`chown -v` <user> <file/folder></br>
  
3 (most use). from -rwxrwxrwx to -rw-rw-r—, make your script executable</br>
`sudo chmod +x` <file></br>

</br>

## Shared_folder</br>
поставить двойное соединение</br>
создать папку (auto amount, permanent)</br>

<b>подключить CD Tools:</b>
если само не открылось перейти в</br>
`cd /media/user/VBox_GAs_6.1.34/VBox_GAs_6.1.34/`</br>
`./autorun.sh`</br>
`sudo apt update`</br>
`sudo apt install update`</br>

в консоли:</br>
`sudo usermod -a -G vboxsf <user name>`   создание прав</br>
`sudo apt-get install gcc make perl`    не знаю но надо</br>

</br>

## Update
Обновить Kali:</br>
`sudo apt update && sudo apt full-upgrade -y && sudo reboot -f`</br>

</br>

## ssh
`ssh-keygen -t ed25519 -C "your_email@.com"`</br>

</br>

## Features
### apt-remove</br>
<b>Удаление ненужных зависимостей:</b></br>
`sudo apt autoremove`</br>

---

### Tricks</br>
если нажать tab в имени которое было оно само допишет</br>
`ls -l && echo "Stas"`    если одно не выполнетеся остальное тоже</br>
`ls -l; echo "Stas"`   добавить много команд</br>
`truncate -s 0 file`     clear file</br>
`| column -t`    удобно вывести по колонкам</br>
`sudo rm -R /`    Kill Linux</br>
