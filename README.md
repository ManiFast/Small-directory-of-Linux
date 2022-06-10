# List_of_commands     
List of my frequent Linux terminal commands (updating every week)

# Table of Contents:
- [<b>Main</b>]()
  - [Commands](#commands)
  - [Input text in file](#input_text_in_file)
  - [Compiling](#compiling)
- [<b>Hot keys</b>](#keys)
- [<b>Software</b>](#software)
  - [VIM](#vim)
- [<b>Root</b>](#root)
- [<b>Shared folder</b>](#shared_folder)
- [<b>Update Linux (Kali)](#update)
- [<b>Features</b>](#features)
---
## Main
### commands
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

### input_text_in_file
  1) `cat > file.txt << ENDL`</br>    '>' its write in end ENDL its special word witch means end of line (random word)</br>
  2) `printf "text" > file.txt`</br>
  
`sudo update-manager -c -d`   upgrade Linux</br>

### compiling
`gcc file.c -o file`        compiling output file</br>
`make file`          gcc file.c -o file</br>
`./file`    run file</br>

`ls -l && echo "Stas"`    если одно не выполнетеся остальное тоже</br>
`ls -l; echo "Stas"`   добавить много команд</br>
`truncate -s 0 file`     clear file</br>
`| column -t`    удобно вывести по колонкам</br>
`sudo rm -R /`    kill Linux</br>
</br>
## keys
`^`    Its Ctrl</br>
`^A ^E`   go to start or end </br>
`^R`         finding commands</br>
`^U`        clear what written on left</br>
`^M`       new line</br>
`^Shift+V`              paste text</br>
`^Shift+Insert`      paste text too :D</br>
</br>
## software

### vim
`^:`    open vim command line</br>
`!`   extra ...  !q extra quit</br>
`w`   save</br>
`q`   quit</br>
`:%s/WORD/REPLEACEWORD/g`   find and replace (g - all)</br>
</br>
## root
`sudo -i`


</br>

## shared_folder</br>
поставить двойное соединение</br>
создать папку (auto amount, permanent)</br>

<b>подключить CD Tools:</b>
если само не открылось перейти в</br>
`cd /media/user/VBox_GAs_6.1.34/VBox_GAs_6.1.34/`</br>
`./autorun.sh`</br>
`sudo apt update`</br>
`sudo apt install update`</br>

в консоли:
`sudo usermod -a -G vboxsf <user name>`   создание прав</br>
`sudo apt-get install gcc make perl`    не знаю но надо</br>

</br>

## update
Обновить Kali:</br>
`sudo apt update && sudo apt full-upgrade -y && sudo reboot -f`

## features
если нажать tab в имени которое было оно само допишет</br>

<b>Удаление ненужных зависимостей:</b>
`sudo apt autoremove`
