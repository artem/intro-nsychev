# Настройка инструментов на Windows

1. Установите набор инструментов [MSYS2](https://www.msys2.org/).

2. Из меню "Пуск" запустите оболочку "MSYS2 MinGW 64-bit" (синяя иконка)

3. Установите GCC, GNU Make и [QEMU](https://www.qemu.org/):
   ```
   $ pacman -S make mingw-w64-x86_64-gcc mingw-w64-x86_64-qemu
   ```

4. _Опционально:_ Установите [Git VCS](https://git-scm.com/) (так можно будет взаимодействовать с git в том же окне):
   ```
   $ pacman -S git
   ```

5. С [сайта SiFive](https://www.sifive.com/software) скачайте сборку GNU Embedded Toolchain для Windows

6. Распакуйте содержимое архива (папки bin, include, lib...) в директорию C:\\msys64\\mingw64\\

7. Проверьте, что всё работает:
   ```
   $ gcc --version
   gcc.exe (Rev1, Built by MSYS2 project) 10.2.0
   $ /opt/riscv/bin/riscv64-unknown-elf-gcc --version
   riscv64-unknown-elf-gcc (SiFive GCC 8.3.0-2020.04.0) 8.3.0
   $ qemu-system-riscv64 --version
   QEMU emulator version 5.1.0
   ```
   
   > Версии могут быть более новыми, это нормально.

8. _Опционально:_ Можно добавить поддержку MSYS2 в Windows Terminal ([подробнее](https://www.msys2.org/docs/terminals/)) используя следующий конфиг:
   ```
   {
         "guid": "{17da3cac-b318-431e-8a3e-7fcdefe6d114}",
         "name": "MINGW64 / MSYS2",
         "commandline": "C:/msys64/msys2_shell.cmd -defterm -here -no-start -mingw64",
         "startingDirectory": "C:/msys64/home/%USERNAME%",
         "icon": "C:/msys64/mingw64.ico",
         "fontFace": "Lucida Console",
         "fontSize": 9
   },
   ```