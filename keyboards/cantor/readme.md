# Cantor by AtomBoards

![Cantor](https://i.imgur.com/lvG6ztl.png)

Клавиатура Cantor от AtomBoards — это разделенная клавиатура с 42 клавишами без диодов, разработанная с упором на простоту. Она вдохновлена популярными клавиатурами [corne](https://github.com/foostan/crkbd), [ferris](https://github.com/pierrechevalier83/ferris) и [sweep](https://github.com/davidphilipbarr/Sweep), целью которой является предоставление более эргономичной раскладки в стиле corne с простой, легкой в сборке и недорогой конструкцией.

Спасибо за уточнение. Вот обновленная инструкция, учитывающая ваше замечание:

## Компиляция и прошивка с использованием QMK MSYS

### Установка QMK MSYS
1. Скачайте и установите [QMK MSYS](https://msys.qmk.fm/).
2. После установки запустите QMK MSYS.

### Компиляция и прошивка клавиатуры
1. В QMK MSYS, клонируйте репозиторий AtomBoards/vial-qmk, если вы этого еще не сделали:
   ```
   git clone https://github.com/AtomBoards/vial-qmk
   ```
2. Перейдите в папку с репозиторием QMK:
   ```
   cd vial-qmk
   ```
3. Сначала скомпилируйте прошивку для левой стороны клавиатуры командой:
   ```
   qmk flash -kb cantor -km vial -bl dfu-util-split-left
   ```
   Когда в консоли появится запрос на перевод платы в режим bootloader, сначала зажмите кнопку BOOT0 на клавиатуре, затем нажмите и отпустите кнопку NRST, и после этого отпустите кнопку BOOT0.
4. Повторите процесс для правой стороны клавиатуры, используя команду:
   ```
   qmk flash -kb cantor -km vial -bl dfu-util-split-right
   ```
   Используйте те же шаги для перевода платы в режим bootloader.
