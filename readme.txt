                        ______
                       (_____ \
                  _   _ _____) )___ ___   ____ 
                 | | | |  ____/ ___) _ \ / _  |
                 | |_| | |   | |  | |_| ( ( | |
                 | ____|_|   |_|   \___/ \_|| |
                 | |                    (_____|
                 |/


µProg - the AVR µControllers programmer

Hardware and software: Pawe³ Kisielewski "Manekinen"
manekinen@gmail.com

Used/based on third-party software:
AVR-DOS by Vögel Franz Josef
LPH7779 driver by Grzegorz Bujanowski RGB

Compiler: bascom-avr v.2.0.7.0   

PCB: Eagle light v.5.10.0    

Code quality: 2 WTFs/min

**************************************************************************    

Project website:  http://diy.elektroda.eu/uprog-maly-szybki-przenosny-programator-avr-z-sd/
English language: http://diy.elektroda.eu/uprog-maly-szybki-przenosny-programator-avr-z-sd/?lang=en

Any modifications allowed, do not remove this README.txt from archive.
Do not remove author info from pcb and code.

Any usage of this project in commercial/profit purposes, entirely or partly, is prohibited.
READ AND ACCEPT LICENSE FILE TO USE THIS PROJECT.

Project-related questions - post in comments on project site.
Other questions - contact me at manekinen@gmail.com

For software updates notifications, follow me at http://www.twitter.com/manekinen

**************************************************************************

Special thanks to:
Maciej Lassota "mlassota" mlassota76@gmail.com - beta tester
Piotr Rzeszut "piotrva" "piotr94" piotrva@wp.pl - beta tester

**************************************************************************
**************************************************************************

CHANGELOG:

_________________________
First release 05.06.2011:

PCB ver.1.0
-target programming tested from 3.0 to 5.5 volts

Firmware ver.1.0 BETA
-programmer fully tested with: tiny13, tiny2313, mega8, mega88, mega16, mega32, mega328, mega644
-write/read above 128kB (extended memory chips) has not been tested but it is implemented
Known issues (will be fixed within next update):
-write/read HEX files are probably limited to 64kB
-errors when writing eeporom from/to HEX files

Chip database ver.1.0
-109 chip records (47 fully supported, for rest only fuses/locks operations)


____________________
#1 Update 22.06.2011:

PCB ver.1.1
-added current limiting resistors for MOSI and SCK lines
This is necessary if your target works at 5V and have strong high state at MOSi and SCK lines
5V at ports supplied from 3V3 could damage these ports, resistors will take current overflow.

Firmware ver.1.1
-fixed issue when programmer got freeze after waking up from sleep mode
-fixed issue when LCD get too low voltage (contrast problems)
-fixed errors when writing/reading eeprom from/to HEX files
-fixed communication issues (SPI settings)
-fixed issue when non existing submenu options was visible
-fixed issue when broken verification progress bar appear if autoverify was disabled
-fixed freezing animations
-eliminated inconsistency between program and "chip.db" file in "programming method" byte
-added support for 48*102 organization LCDs (see "config.ini")
-added lcd contrast and bias settings to "config.ini" file
-added battery voltage measurement - device will not turn on if voltage exceeds 3,7V
-code improvements

____________________
#2 Update 30.06.2011:

Firwmare ver.1.2
-fixed addresing issue when addressing last word in 128kB chips with "0000" instead of "FFFF"
-fixed broken progress bar when writing files larger than 64kB
-fixed broken progress bar when writing small file into a big chip
-fixed time delays when navigating in menu
-added support for extended intelHEX files addressing - read and write. (no 64kB limit)
-added 1 second delay at startup if battery voltage is below 3V (helps to init SD card)
-speed test (read signature) is now performed 100 times
-added "success" animation, displayed if write/verify was successful and if animations are enabled

Chip database ver.1.02
-filled up almost all entries, only old AT90S and few attiny chips are left

____________________
#3 Update 20.07.2011:

Firmware ver.1.3
-fixed write and verify HEX files which starts not at 0 address (f.e. bootloaders)
-added OSCCAL setting to "config.ini"
-added max SCK speed setting to "config.ini"
-added function to delete files (select file, hold LE, press RI to delete)
-imrpoved buttons debouncing
-fixed extended memory chips addressing (mega2560, mega2561)
-added "manual" function which allows to manually set fusebits, select values from 0 to F for each fuse
-added smallest SCK speed - 8kHz - so its possible to program chips driven by watch crystal
-changed naming method of created files, now names will be "m2560-12.hex", "t2313-2.bin" etc
-added license file, it must be present in root dir in unmodified form.

Chip database ver.1.03
-changed all "/" slash chars to "-" dash chars because of new file naming method. "/" are not allowed chars in windows os.