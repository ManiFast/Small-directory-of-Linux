            
# Tools and settings           
<h3>List of my frequent Lin ux terminl commands (updating every two days)</br></br>                                              
       
<i>Its like a bible lmao)</br>
I think in near future I write a small book for Linux like "A bit about Linux in many ways !"</i></h3></br>   

> **Hint** </br> 
> ![-=> More about pentesting and tools <=-](https://github.com/ManiFast/Pentest-RedTeam-Tools/)
>
>
> *Click 🔙 to get back.*

# Table of Contents:
- [<b>Main</b>](#main)
  - [Commands](#commands)
  - [LAN](#lan)
    - [Wi-Fi](#wifi)
    - [nmtui](#nmtui)
    - [config of interfaces](#config_of_interfaces)
    - [Others](#others)
  - [KeyBinds](#keybinds)
  - [Logs](#logs)
  - [Input text in file](#input_text_in_file)
  - [Users and groups](#users)
  - [Archiving](#archiving)
  - [Compression](#compression)
  - [Compiling](#compiling)
  - [gcc compile c/c++ program](#gcc)
- [<b>BASH scripting</b>](#bash_scripting)
- [<b>Hot keys</b>](#keys)


- [<b>Software</b>](#software)
  - [VIM](#vim)
    - [Macros](#macros)
    - [Config VIM](#config)
  - [neo VIM](#neo_vim)
  - [tldr](#tldr)

- [<b>Linux</b>](#linux)
  - [Distributions](#distributions)
    - [Debian](#debian)
    - [Arch](#arch)
  - [Root](#root)
  - [Permission](#permisson)
  - [Shared folder](#shared_folder)
  - [Update Linux (Kali)](#update)
  - [SSH](#ssh)
  - [Linux Desktop Environments](#linux_desktop_environments)
    - [KDE](#kde)
    - [xfce](#xfce)
  - [Config bash](#config_bash)
    - [.bashrc](#bashrc)
    - [.zshrc](#zshrc)
  - [GRUB](#grub)
  
- [<b>Features</b>](#features_of_linux)
  - [APT remove](#apt-remove)
  - [Set emoji](#emoji)
  - [Terminal](#terminal)

- [<b>Tricks</b>](#tricks)

---


## Main
### Commands
| **Command** | **Description** |
| --------------|-------------------|

`!$`    last argument (напр mkdir ss/sdf)</br>
`!!`    previous comand</br>
`Super+Space`     change language keyboard</br>
`ls`     show files and folders</br>
  `ls -l -a`    -l beauty   -a  all files</br>
  `ls -F`    -F show folders and files with "/"<br>
`touch`    create file</br>
`cd`    previous path</br>
`cat`    output file</br>
`vim`    change file</br>
`htop`    about system</br>
`ps`    what running</br>

`mkdir (-p)`    create dir, p-if that dir isnt found, create !</br>
`rmdir`    remove dir</br>
`rm -R`    remove not empty dir</br>

`mv`    rename or move</br>
`wc`    word count</br>
  `wc file.txt -l/w`    show lines or words in file </br>
  `grep "[A-Za-z]*stas" -E ./*`    example, find ...s/Stas in this folder
`sort`    sort to symbols without change</br>
  `sort -n`    sort by names</br>

`cut -d ">" -f 3 file.txt`    divorse each column on end ">" and output only third lines in file.txt</br>
  `cut -d ">" -f 3 countries.txt | sort -n`    example of sorting</br>


`find`    find file</br>
  `find /home -name "file*.txt"`</br>

`grep <-i> <word> <file/path>`    find in folders or files, 'i' = ignore case count Aa</br>
  `grep -E  "@[A-Za-z]*.com" file.txt`    find certain fraze in file</br>
  `grep "[A-Za-z0-9]*@gmail.com" emails.txt`    example, find all email in end @gmail.com</br>
   [A-Z] [a-z] [0-9] @ _ - . </br>

`curl <URL>`      parsing for sites, give text from URL</br>
      `curl https://www.kali.org/`      showing html code</br>
      `curl -s https://hackware.ru/`      show code without statistic</br>
      `curl -A <URL>`      site didnt know that u use console app with curl</br>
      `curl --compressed https://www.kali.org/`      without binary trash</br>
      `curl -s https://hackware.ru/ | grep "extra"`      good sample</br>

If you also have trash, try change charset:</br>
For ex. when u put this:
`curl http://z-oleg.com/`</br>
You see this:
![84](https://github.com/ManiFast/Small-directory-of-Linux/assets/62830326/aec69bb2-63b6-4afc-b867-637dffa3be0a)</br>
And u should look what charset set in HTML in tag <meta></br>
<meta http-equiv="Content-Type" content="text/html; charset=windows-1251"></br>
Use <b>iconv</b>:
`curl http://z-oleg.com/ | iconv -f windows-1251 -t UTF-8`      right charset translate</br>

`ln`    links (like shortcut)</br>
  `ln -s /home/Desktop/Dir`    link to folder</br>
  `ln /home/Desktop/file.txt`    create duplicate of file</br>


`date`    show date (with args)</br>
  `date +"%H:%M"`    11:32, certain cut date</br>
  
`whoami` what user</br>
`id` which groups u consist</br>
  `id root` show id root</br>
    
`last` who enter in pc</br>
`who` who now use pc</br>
`w` what all users do</br>
  
`su` <user> change user</br>

`fiind` find but not use, search for files in a directory hierarchy</br>
`whereis` locate main place, locate the binary, source, and manual page files for a command</br>
`which` locate a command</br>
`locate <app>`/`plocate <app>` where is program locate, find files by name, quickly</br>
  
`fakeroot` fake root in kali</br>
  
`sudo apt search` search packages for install</br>
  
`> >>`    clear and rewrite/just write at the end</br>
`2>`    catch errors</br>
  `grep cats animals/* 2> errors.txt`    find strings with word 'cats' in all files in folder 'animals' and errors write in 'errors.txt' file</br>
  `grep aqua colors/* > good.txt 2> nogood.txt`    write noerrors msg in 'good.txt' and errors msg in nogood.txt</br>
  `/dev/null`    always empty folder, like 'black hole')</br>
  `2>>`    add errors in file, like '>>'</br>
`&>`    catch errors and noerrors messages (because if you write '>' saving only noerrors messages)</br>
 
`bg`    show background process</br>
`fg`    return to background</br>
 
`top` task manager</br>
`htop`  new task manager</br>

`ps` list of procces</br>
  `ps -aux`    show all in all</br>
  `ps -ax`
  `ps -aux | grep manifast`    find strings with this word</br>
 
`kill <signal>`  kill process, find signal from 'ps -aux'</br>
  `kill -9 2763`</br>
  `kill -KILL 2763`</br>
  `kill -9/KILL %`  kill last process</br>
  `kill %2`  point to second task</br>
 
`<command> &`  & - needed for start task into background</br>
   `updatedb &`</br>
   
`jobs`  show tasks list in background</br>
 
`hostname` ur nick</br>
`hostnamectl` show vresion (check the Kernel version and CPU architecture)</br>
`lsb_release -a` check the release version, description, and operating system codename</br>
`uname -a` shows the current kernel and OS information</br>
`sudo adduser `id -un` libvirt` add user for qemu</br>
 
 `ping` using for test connection and avalible of server</br>
  `ping -c yandex.ru` test only 3 times and get right info</br>

`sudo date -s "$(wget --method=HEAD -qSO- --max-redirect=0 google.com 2>&1 | sed -n 's/^ *Date: *//p')"` set date</br>

 
install packages in Debian:</br>
`sudo dpkg -i <path>`</br>
     sudo dpkg -i quickhash_3.3.1-1_amd64.deb</br>

Check for supporting vm:</br>
`LC_ALL=C lscpu | grep Virtualization` </br>

Time:</br>
`sudo ln -sf /usr/share/zoneinfo/Asia/Tashkent /etc/localtime`</br>
 
 
### LAN

#### wifi

`nmcli d wifi connect <name> password <password> ifname wlan0` connect wifi</br> 

#### nmtui
`nmtui` Network Manager TUI</br>

![image](https://user-images.githubusercontent.com/62830326/209325587-beab3bb9-fab4-4e38-a1ac-57d64db7f610.png)</br>

#### Config_of_interfaces

`/etc/network/interfaces`</br>

![image](https://user-images.githubusercontent.com/62830326/209325802-8ada84ca-c6b0-47c5-850f-651bdbd5fb37.png)</br>

text:</br>
auto eth0</br>
iface eth0 inet static</br>
address 192.168.0.226/24</br>
gateway 192.168.0.1</br>

Set to default if u have problems with connetion like (ping, browser etc.)</br>

In /etc/network/interfaces u must make like this:</br></br>
```
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

auto eth0
#iface eth0 inet static
#address 193.168.0.224/24
#gateway 192.168.0.1
iface eth0 inet dhcp
```

#### Others

`systemctl restart NetworkManager.service` restart connections</br>


 
 
 
 
 
 
### Keybinds

In the Terminal:</br></br>
Move:</br>
`стрелки`       moving cursor</br>
`Shift + стрелки`     list terminal</br>
`Shift + PageUp/PageDown`         list with spacees</br>
`Ctrl + PageUp/PageDown`     switch bookmarks</br>
`Ctrl + Shift + PageUp/PageDown`    moving bookmarks</br></br>

Close:</br>
`Ctrl + D` end of file input</br></br>
`Ctrl + C` close (kill), OC send signal 'SIGINT'</br>
`Ctrl + /` close too, OC send signal 'SIGQUIT'</br>
`Ctrl + Z` sleep</br>
`Ctrl + S` pause output</br>
`Ctrl + Q` resume output</br>

  
###  Logs
 
`/var/log` logs</br>
`sudo dmesg` log of Linux core</br>
`/etc/passwd` system accaunts</br>
`/etc/shadow` all shifered passwords</br>
`/etc/group`  all users groups (f.e how can use sudo)</br>
 
  
###  Input_text_in_file
  1) `cat > file.txt << ENDL`</br>    '>' its write in end ENDL its special word witch means end of line (random word)</br>
  2) `printf "text" > file.txt`</br>
  

###  Users
`useradd -m` <name> add user (with home directory)</br>
`userdel -r` <name> delete user (with home)</br>

`/etc/skel` templete of home directory</br>
`passwd` <user> change password for user</br>

`groupadd` <name> create group in /etc/group</br>
`groupdel` <name> delete group</br>
 
 `usermod -aG` <group> <user> add user to group</br>
 `deluser` <user> <group> delete user from group</br>

###  Archiving
tar using without "-"
`tar cvf <name.tar> <folder>` create archive (c - create, v - view, f - must be in end)</br>
  tar cvf data.tar dataBig/</br>
`tar xvf <name.tar>` extract archive (x - unzip)</br>
  tar xvf data.tar</br>
  `tar -C <path> -xvf <file>` extract to considered folder (C - path)</br>
      tar -C home/ -xvf data.tar</br>
`tar tf <name.tar>` view what in tar (t - test)</br>

###  Compression
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



## gcc
Hot to compile and run c/c++ file.
In default gcc can be installed on your system if not ->

`sudo apt-get install build-essential manpages-dev`</br>
``</br>

Create file, edit it and save like `.c` or `.cpp`</br>

For c:</br>
`cc program.c -o program`</br>

For c++</br>
`gcc program.c -o program`</br>

or universal:</br>
`make program.c` </br>

How to run:</br>
`./program` or `/home/Desktop/program`</br>

(not necessary)

Generate symbolic information for gdb and warning messages</br>
c:</br>
`cc -g -Wall input.c -o executable`</br>
c++:</br>
`g++ -g -Wall input.C -o executable `</br>

Compile a C program that uses math functions</br>
c:</br>
`cc myth1.c -o executable -lm `</br>

Compile a C++ program that uses Xlib graphics functions</br>
c++:</br>
`g++ fireworks.C -o executable -lX11`</br>

Compile a program with multiple source files</br>
c:</br>
`cc light.c sky.c fireworks.c -o executable`</br>
c++:</br>
`g++ ac.C bc.C file3.C -o my-program-name`</br>


#  Bash_scripting
`var="string"`       create valuable</br>
`read` <var>         like "cin»var", write in value</br>
`var=$1/2`                 AKA Argument,      ./file $1</br>
`daytoday=$(date +"%D")`        example of pasting output command</br>


</br>

# Keys
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


##  Software

###  VIM
`^:`  open vim command line</br>
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

<number>`w` go to 10 word ahead</br>

`/` find word (<b>down</b> from cursor)</br
`?` find word (<b>up</b> from cursor)</br>

in VISUAL mode:</br>
`y` copy text</br>
`x` cut text</br>
`p` paste text</br></br>
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
 
 ### Config
 [My cfg here](https://github.com/ManiFast/Linux_Config_Backup/blob/main/.vimrc)</br>
 
 `sudo vim ~/.vimrc`</br>
 `sudo vim .config/nvim/init.vim`</br>
 
 
 
 
 
 ## Neo_vim
 `sudo apt install neovim -y` install</br>
 `sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'` write this in directory ~/.config/nvim</br>
`nvim` start</br>

Create config folder:
`cd ~/.config/`</br>
`mkdir nvim`</br>
`nvim nvim/init.vim` config</br>
and paste config here</br>

`sudo apt install git`</br>
`:PlugInstall` write this in nvim command cmd</br>

https://vimawesome.com/ set plugins here</br></br>

![photo_2022-08-22_10-23-10](https://user-images.githubusercontent.com/62830326/185845216-3a2e8029-61ad-45c6-ba29-540838ee8c33.jpg)

![Screenshot 2022-08-22 102500](https://user-images.githubusercontent.com/62830326/185845363-3a761231-8813-42fd-8934-275b6b7f7065.png)

Setting nvim:</br>
in <b>options.txt</b> file</br>

`:h <what find>` find in all setting in nvim</br>
  `:h 'guicursor'>` or u can type `:h guic<tab>`</br>
`:set <parametr>=<value>`</br>
  `:set guicursor=`</br>
  

# tldr

<b>tldr</b> is a small tool that provides concise, easy-to-read summaries of information from man guides.</br>

The Debian man command does not have the same format as Archcraft Linux.</br>
On Debian, the man command displays man manuals in text format.</br>
In Archcraft Linux, the man command displays man pages in HTML format.</br>
To get the same look as in Archcraft Linux, you can use the tldr program.</br>
The tldr program provides concise, easy-to-read summaries of information</br>
from man manuals in HTML format. To install the tldr program, you can run the</br>
following command in a terminal:</br>

`sudo apt install tldr`</br>

It very useful for people like me because show many of examples with all arguments and options like this.</br>
For example you forget something in nmap or dirb programm and it easly show you all examples, </br>
ether you waste time of searching in browser.</br> 


![image](https://github.com/ManiFast/Small-directory-of-Linux/assets/62830326/dd5632b7-3cbd-4dfd-8a53-56599b239ffd)




# Linux  

## Distributions

### Debian
*apt* is a packet manager in Debian</br>

func:</br>
apt install <name of packet></br>
apt remove <name of packet></br>
apt search <name of packet></br>

`sudo apt update -y $$ sudo apt upgrade -y` full update Linux</br>
  `-y` without ask</br>

packeges:</br>
`sudo apt install ./deb_file` install .deb files</br>

Install & Execute BIN files:</br>

`chmod + x <filename> `</br>
`./<filename>`</br>

### Arch
*Pacman* is a packet manager in Arch</br>

Funcions:</br>
`sudo pacman -S <name of packet>`          install</br>
`sudo pacman -Ss <name of packet>`        search</br>
`sudo pacman -R <name of packet>`    remove</br>
`sudo pacman -R <name of packet>`    remove expact config (dependencies)</br>
`sudo pacman -Rns <name of packet>`         remove with all config dependencies</br>

`sudo pacman -Syu` update Linux</br>

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
make a double connection</br>
create directory(folder) (auto amount, permanent)</br>

<b>turn on CD Tools:</b>
if it didnt open automaticly, go to</br>
`cd /media/user/VBox_GAs_6.1.34/VBox_GAs_6.1.34/`</br>
`./autorun.sh`</br>
`sudo apt update`</br>
`sudo apt install update`</br>

in terminal:</br>
`sudo usermod -a -G vboxsf <user name>`   create rights</br>
`sudo apt-get install gcc make perl`    dnt know but must paste</br>

</br>

## Update
Linux version:</br>
`uname -r`</br>
6.1.0-kali9-amd64</br></br>

`cat /proc/version`</br>
Linux version 6.1.0-kali9-amd64 (devel@kali.org) (gcc-12 (Debian 12.2.0-14) 12.2.0,</br>GNU ld (GNU Binutils for Debian) 2.40) #1 SMP PREEMPT_DYNAMIC Debian 6.1.27-1kali1 (2023-05-12)</br></br>

`lsb_release -r`</br></br>

Update Debian/Kali:</br>
`sudo apt update && sudo apt full-upgrade -y && sudo reboot -f`</br></br>

/etc/apt/sources.list </br>

`deb http://http.kali.org/kali kali-rolling main non-free contrib
deb-src http://http.kali.org/kali kali-rolling main non-free contrib`

`apt-get update` address update, update software source data.</br>
`apt-get upgrade` software update, update all installed software.</br>
`apt-get dist-upgrade` system update, replace the system version.</br>
`apt-get clean` Clean up garbage, delete all downloaded packages.</br>


</br>

## ssh
`ssh-keygen -t ed25519 -C "your_email@.com"`</br></br>

## linux_desktop_environments
![Screenshot 2022-08-21 144330](https://user-images.githubusercontent.com/62830326/185785217-6e46fae4-c196-47d1-8847-75a7f47bda4c.png)</br></br>

`sudo tasksel` select startup enviroments</br>
![image-104-768x579](https://user-images.githubusercontent.com/62830326/185799739-4512aefe-d079-4c7c-a422-b90f3b2d1e1c.png)



### KDE
`sudo apt install kali-defaults kali-root-login desktop-base kde-plasma-desktop` </br>

![photo_2022-08-22_16-29-22](https://user-images.githubusercontent.com/62830326/185910850-61b5d180-adeb-4500-a600-be5aeee3a380.jpg)

### xfce

## config_bash

### bashrc
Paths:</br>
`/etc/bash.bashrc`</br>
`/root/.bashrc`</br>

### zshrc
Path:</br>
`/.zshrc`</br>

-> ![Config.txt](https://github.com/ManiFast/Small-directory-of-Linux/blob/main/Config_zshrc.txt) <-

## grub
GRUB (GNU GRUB -  GRand Unified Bootloader) is default OS bootloader wich have quite good configuration.</br>

`sudo nvim /etc/default/grub` config of GRUB</br>

If you write changes you must reload GRUB</br>

`sudo update-grub` </br>


# Features_of_linux
## apt-remove</br>
<b>Delete unuseful dependencies(зависимостей):</b></br>
`sudo apt autoremove`</br>

## Emoji
![image](https://user-images.githubusercontent.com/62830326/191039766-9b7ce2ba-e814-46e0-9c45-53cb131e9736.png)</br>
`sed -i 's/prompt_symbol=㉿/prompt_symbol=💻/' ~/.zshrc` for user</br>
`sed -i 's/prompt_symbol=㉿/prompt_symbol=💀/' ~/.zshrc` for root</br>

## Terminal
Kali Linux use the Qterminal like main terminal emulator and more like byouye and xfce4-terminal





# Tricks</br>
if you press tab in the name that was, it will add itself</br>
`ls -l && echo "Stas"`    if one fails, the next too</br>
`ls -l; echo "Stas"`   add many commands</br>
`truncate -s 0 file`     clear file</br>
`| column -t`    convenient to display in columns (удобно вывести по колонкам)</br>
`sudo rm -R /`    Kill Linux</br>
`fakeroot` fakeroot</br></br>
`Ctrl + Alt + стрелки`      switch desktop</br>
`Ctrl + h` replacement (замена) backspace</br>
`Alt + WhellUp/Down` loop</br>
U can install only needed programs from different system like:</br>
`sudo apt install gnome-calculator` or</br>
`sudo apt install xfce4-terminal`</br>

---
![](https://github.com/ManiFast/DeskTop/blob/main/Screenshot_2023-07-05_11_10_22.png)
Do u like it ? Star repo and share it with your friends!)
