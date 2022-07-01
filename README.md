# List_of_commands                                        
List of my frequent Linux terminal commands (updating every week)

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
  - [Metasploit](#metasploit)

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
    
  `last` who enter in pc
  `who` who now use pc
  `w` what all users do
  
  `su` <user> change user
  
  
  
  
  
  
  
  
  
  
  
 
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
 
</br>
  
  
### metasploit
<b>Exploit<b> - код для уязвимости</br>
<b>Payload</b> - устанавливает соединение, выполняет скрипты)</br>
<b>Post</b> -  запускается после успешного проникновения (кейлоггер, скачивает файлы)</br>
<b>Encoder</b> - маскировка от антивирусов</br>

<b>NOP</b> - заполняет пустоту в исполняемых файлах</br>
<b>Auxiliary</b> - модули для сканирование сети анализа трафика</br>

—-
  
Конфиг (там где пароли)</br>
<b>/usr/share/metasploit-framework/config</b></br>

`db_status` show what <b>DB (DataBase)</b> is turn on</br>
`db_disconect` disconnect DB</br>
`db_connect -y` </usr/share/metasploit-framework/config/database.yml> connect DB with path</br>
  
`help`
`workspace` show list of tabeles (projects)</br>
  `workspace -a <name>` add new table</br>
  `workspace -d <name>` delete table</br>
`workspace <name>` switch to table</br>
 
 `db_import <path>` import tables .xml</br>
 `db_export <path>`
 
 `hosts` show all hosts: ip, MAC and type OC</br>
   `hosts -S <word>` find in hosts</br>
 `sevices` show all services (from .xls files)</br>
    `services -S` find in services</br>
 `vulns` list of vulnerability (уязвимость)</br>
 
 `notes` results from scaning</br>
 `loot` save dump hash memory (I dnt know)</br>
 `analyze` analyze DB</br>
 `search type:exploit ftp` search exploits for ftp (ot enth)</br>
  
  
  
  
  
  
  
  
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
