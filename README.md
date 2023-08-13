# ConteinL1
Изоляция пространств имен баш.
1.Создаем директорию testfolder
mkdir testfolder
2.Входит в созданную директорию
cd testfolder
4. Копируем окружение bash
mkdir bin
cd..
cp /bin/bash testfolder/bin
5. Создаем необходимые директории "testfolder/lib" и "testfolder/lib64":
mkdir testfolder/lib
mkdir testfolder/lib64
Копируем необходимые библиотеки в папку "testfolder/lib" и "testfolder/lib64". 
cp /lib/x86_64-linux-gnu/libtinfo.so.6 testfolder/lib
cp /lib/x86_64-linux-gnu/libc.so.6 testfolder/lib
cp /lib64/ld-linux-x86-64.so.2 testfolder/lib64/
6. Запускаем команду chroot для изменения корневой папки:
chroot testfolder /bin/bash
Примечания:
Важно убедиться, что пути к исполняемым файлам и библиотекам соответствуют вашей системе.

Можно увидеть что приветствие системы изменилось.
Мы сменили в данном случае корневую папку , это означает что мы изолировали процесс, получив изолированную среду (безопасность, независимость от системы). По сути у Нас запустилась изолированная оболочка интерпретатора БАШ, с корнем отличным от файловой системы.
![1 chroot](https://github.com/PavelE13/ConteinL1/assets/94640966/def8df9c-38f8-4005-9daf-b97a13774f30)
