# Настройка инструментов на Windows

1. Установите набор инструментов [MSYS2](https://www.msys2.org/).

2. Из меню "Пуск" запустите оболочку "MSYS2 MinGW 64-bit" (синяя иконка)

3. Установите GCC, GNU Make и [QEMU](https://www.qemu.org/):
   ```
   $ pacman -S make mingw-w64-x86_64-gcc mingw-w64-x86_64-qemu
   ```

4. _Опционально:_ установите [Git VCS](https://git-scm.com/) (думаю, что в одном терминале работать удобнее):
   ```
   $ pacman -S git
   ```

5. Распакуйте папку opt из [архива с тулчейном RISC-V GCC](ссылку я не дам) в корневую директорию MSYS2 (по умолчанию это C:\\msys64\\)

6. Проверьте, что всё работает:
   ```
   $ gcc --version
   gcc.exe (Rev1, Built by MSYS2 project) 10.2.0
   $ /opt/riscv/bin/riscv64-unknown-elf-gcc --version
   riscv64-unknown-elf-gcc.exe (GCC) 10.1.0
   $ qemu-system-riscv64 --version
   QEMU emulator version 5.1.0
   ```
   
   > Версии могут быть более новыми, это нормально.
