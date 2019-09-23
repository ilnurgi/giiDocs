Linux
=====

Contents:


.. toctree::
   :maxdepth: 2

   cd
   chgrp
   chmod
   chown
   cp
   cat
   dd
   df
   dirs
   dmwsg
   find
   grep
   head
   ls
   mkdir
   pwd
   touch
   ps


Горячие клавиши
----------------------------

* Ctrl+C - завершить текущую команду
* Ctrl+Z - остановить текущую команду, продолжить с fg на переднем плане или bg в фоне
* Ctrl+D - разлогиниться, тоже самое, что и exit
* Ctrl+W - удалить одно слово в текущей строке
* Ctrl+U - удалить строку
* !! - повторить последнюю команду

Файловые команды
-----------------------------

    * ln [args] file link
      Создать ссылку к файлу

        * args
          -s - символическая ссылка
        * file - путь к файлу
        * link - имя ссылки

    * ls [args]
      Список файлов и каталогов

        * args
          -a – со скрытыми каталогами и файлами
          -l – форматированный список
          -F - отобразить содержимое текущей директории с добавлением к именам символов, характеризующих тип
          -h - с правами
          -S - сортировка по возрастанию размеров

      .. code-block:: sh
        
        # показать файлы и директории содержащие в имени цифры
        ls \*[0-9]\*</pre>


    * more file
      Содержимое файла

        * file - путь к файлу

    * mv file1 file2
      Переименовать или переместить файл

        * file1 - путь к файлу/папке откуда копируем
        * file2 - путь к файлу/папке куда копируем

    * rm [args] file
      Удалить файл или папку

        * args
          -r - папку и все содержимое
          -f - форсированно
        * file - путь к файлу или каталогу

    * rmdir dir
      Удалить папку

        * dir - путь к каталогу

    * tail [args] file
      Последние 10 строк file

        * args
          -f - вывести содержимое file по мере роста, начинает с последних 10 строк
        * file - путь к файлу или каталогу

    * tree
      Показать дерево файлов и директорий, начиная от корня (/)

    Монтирование файловых систем
    ---

    * fuser -km /mnt/hda2
      Принудительное размонтирование раздела. Применяется в случае, когда раздел занят каким-либо пользователем

    * mount /dev/hda2 /mnt/hda2
      Монтирует раздел 'hda2' в точку монтирования '/mnt/hda2'. Убедитесь в наличии директории-точки монтирования '/mnt/hda2'

      mount /dev/sda1 /mnt/win8
      mount -t smbfs //server/folder /mnt/winshare
      mount -o loop disk.iso /mnt/disk
      mount -bind / /mnt/root

    * umount [args] /dev/hda2
      Размонтирует раздел 'hda2'. Перед выполнением, покиньте '/mnt/hda2'

        * args
          -n - без занесения информации в /etc/mtab. Полезно когда файл имеет атрибуты "только чтение" или недостаточно места на диске
    
      .. code-block:: sh

        *# монтировать флоппи-диск*
        mount /dev/fd0 /mnt/floppy
        *# монтировать CD или DVD*
        mount /dev/cdrom /mnt/cdrom
        *# монтировать CD-R/CD-RW или DVD-R/DVD-RW(+-)*
        mount /dev/hdc /mnt/cdrecorder
        *# смонтировать ISO-образ*
        mount -o loop file.iso /mnt/cdrom
        *# монтировать файловую систему Windows FAT32*
        mount -t vfat /dev/hda5 /mnt/hda5
        *# монтировать сетевую файловую систему Windows (SMB/CIFS)*
        mount -t smbfs -o username=user,password=pass //winclient/share /mnt/share
        *# "монтирует" директорию в директорию (binding). Доступна с версии ядра 2.4.0. Полезна, например, для предоставления содержимого пользовательской директории через ftp при работе ftp-сервера в "песочнице" (chroot), когда симлинки сделать невозможно. Выполнение данной команды сделает копию содержимого /home/user/prg в /var/ftp/user*
        mount -o bind /home/user/prg /var/ftp/user</code>

    Поиск
    ---

    * find dir_name [kwargs]
      Найти файлы и директории

        * kwargs
          -name - название файла/папки
          -user - файлы/папки принадлежащие пользователю
          -atime - время последнего обращения
          -mtime - время создания
        * dir_name - путь, откуда начинаем поиск
    
      .. code-block:: sh

        *# найти файл и директорию принадлежащие пользователю user1. Поиск начать с корня (/)*
        find / -user user1
        *# Найти все файлы и директории, имена которых оканчиваются на '. bin'. Поиск начать с '/ home/user1'*
        find /home/user1 -name "\*.bin"
        *# найти все файлы в '/usr/bin', время последнего обращения к которым  более 100 дней*
        find /usr/bin -type f -atime +100
        *# найти все файлы в '/usr/bin', созданные или изменённые в течении последних 10 дней*
        find /usr/bin -type f -mtime -10
        *# найти все фалы и директории, имена которых оканчиваются на '.rpm', и изменить права доступа к ним*
        find / -name \*.rpm -exec chmod 755 '{}' \;
        *# найти все фалы и директории, имена которых оканчиваются на '.rpm', игнорируя съёмные носители, такие как cdrom, floppy и т.п.*
        find / -xdev -name "*.rpm"</code>

    * grep [args] pattern files
      Искать строку в файлах

        * args
          -r - рекурсивно в папке
        * files - список файлов/папок
        * pattern - искомая строка
    
      .. code-block:: sh
    
        # искать pattern в выводе command
        $ command | grep pattern</code>

    * locate file
      Найти все файлы с именем file

    * whereis app
      Возможное расположение программы app

    * which app
      Путь к приложению app

    Архивация
    ---

    * bunzip2 file
      Сжать/разжать file bz2

    * gzip [args] file

        * args
          -d - разжать Сжать/разжать file и переименовать в file.gz

    * tar [args] file.tar files
      Создать/распаковать tar-архив
        * args
          x - распаковать
          c - создать
          z - сжатие Gzip
          j - сжатие Bzip

    Управление процессами
    ---

    * bg
      Список остановленных и фоновых задач; продолжить выполнение остановленной задачи в фоне

    * fg
      Выносит на передний план последние задачи или указанную

    * kill pid
      Убить процесс с id pid

    * killall proc
      Убить все процессы с указанным именем

    * ps
      Текущие активные процессы

    * top
      Все запущенные процессы

    Системная информация
    ---

    * arch
      Архитектура компьютера

    * date [new_date]
      Текущая дата и время

        * new_date - установить системные дату и время ММДДЧЧммГГГГ.СС (МесяцДеньЧасМинутыГод.Секунды)

    * cal [year]
      Календарь на текущий месяц или указанный год

        * year - год

    * clock -w
      Сохранить системное время в BIOS

    * df
      Инф. о использовании дисков

    * dmidecode -q
      Аппаратные системные компоненты - (SMBIOS / DMI)

    * du [args] dir
      Файлы/папки в текущем каталоге
        * args
          -s - подсчет и вывод размера
          -h - размер в Gb
        * dir - папка

    * free
      Использование памяти и swap

    * hdparm -i /dev/hda
      Характеристики жесткого диска

    * hdparm -tT /dev/sda
      Протестировать производительность чтения данных с жесткого диска

    * lspci -tv
      Показать в виде дерева PCI устройства

    * lsusb -tv
      Показать в виде дерева USB устройства

    * man command
      Мануал для command

    * shutdown [args] [time]
      Остановить систему
        * args
          -h - выключить ПК
          -r - перезагрузка
          -c - отменить запланированное выключение
        * time - время выключения (now, hours:minutes)

    * reboot
      Перезагрузить систему

    * uname [args]
      Информация о ядре
    
      .. code-block:: sh

        $ uname
        Linux
        $ uname -a
        Linux ilnurgiPC 3.8.0-27-generic #40-Ubuntu SMP Tue Jul 9 00:17:05 UTC 2013 x86_64 x86_64 x86_64 GNU/Linux
        $ uname -m
        x86_64
        $ uname -r
        3.8.0-27-generic</code>

    * uptime
      Текущий аптайм

    Установка пакетов
    ---

    <code>
    *#Из исходников*
    ./configure, make, make install
    dpkg -i pkg.deb
    Debian
    rpm -Uvh pkg.rpm
    RPM</code>

    Пользователи и группы
    ---

    * chage -E 2005-12-31 user1
      Установить дату окончания действия учётной записи пользователя user1

    * exit
      Разлогиниться

    * groupadd group_name
      Создать новую группу

    * groupdel group_name
      Удалить группу

    * groupmod -n new_group_name old_group_name
      Переименовать группу old_group_name в new_group_name

    * grpck
      Проверяет корректность системных файлов учётных записей. Проверяется файл/etc/group

    * finger user
      Информация о user

    * logout
      Выйти из системы

    * passwd
      Cменить пароль

    * passwd user1
      Сменить пароль пользователя user1

    * pwck
      Проверить корректность системных файлов учётных записей. Проверяются файлы /etc/passwd и /etc/shadow

    * useradd [args] user_name
      Создать пользователя
        * args
          -c comment- коментарии
          -d dir - путь к домашней директорий
          -g group_name - добавить в группу
          -s dir - путь к shell'y

    * userdel [args] user_name
      Удалить пользователя
        * args
          -r - удалить домашнюю директорию

    * usermod [kwargs] user_name
      Изменить атрибуты пользователя
        * args
          -c comment- коментарии
          -d dir - путь к домашней директорий
          -g group_name - добавить в группу
          -s dir - путь к shell'y

    * whoami
      Имя, под которым вы залогинены

    Сеть
    ---

    * dig domain
      DNS информация domain

    * dig -x host
      Реверсивно искать host

    * ping host
      Пропинговать host и вывести результат

    * whois domain
      Информацию для domain

    * wget [args] file
      Скачать file

        * args
          -c - продолжить остановленную закачку

    SSH
    ---

    * scp [kwargs] src dst
      Копирует папки между машинами

        * src - путь, откуда копируем
        * dst - путь, куда копируем
        * kwargs
          -P port - порт подключения
    
    .. code-block:: sh

        scp /home/user/  user@XXX.XXX.XXX.XXX:/home/user</code>

    * ssh [kwargs] user@host

        * user - пользователь
        * host - сервер
        * args
          -p port - порт Подключение

    * ssh-copy-id user@host
      Добавить ваш ключ на host для user чтобы включить логин без пароля и по ключам

    Другое
    ---

    * more
      Постраничный вывод


/proc/cpuinfo – информация ЦПУ
/proc/interrupts - показать прерывания
/proc/meminfo – информация о памяти
/proc/mounts - отобразить смонтированные файловые системы
/proc/net/dev - показать сетевые интерфейсы и статистику по ним
/proc/swaps - показать файл(ы) подкачки
/proc/version - вывести версию ядра