Reflow Oven Controller
====================
Big Thanks to Ed Simmons <ed@estechnical.co.uk> , Karl Pitrich <karl@pitrich.com>
For all there hard work on the original code that this is based on.


**News**
New method for better performance!

 NEW HARDWARE COMING SOON AND FIRMWARE REVISIONS FOR TUNNLE OVENS!
 
 ******** How To Upgrade Arduino For Faster Speeds! *********
 
 To boost your Arduino Uno's performance up to 25% faster, all you have to do is replace the 16 MHz crystal with 20 MHz crystal, and update the bootloader with one that designed for this upgraded speed (see instruction below).
 
 Please note that this is NOT overclocking, we'll just tuning it to maximum speed allowed by manufacturer as stated in ATmega328 datasheet. So it's 100% safe and guaranteed to run as reliable as before, it's just 25% faster :) up to nearly 20 MIPS!
Step 1: Add following content to your boards.txt (located in hardware/arduino sub-directory of the Arduino application directory, i.e. \Program Files (x86)\Arduino\hardware\arduino in default installation path on 64-bit Windows (or \Program Files\Arduino\hardware\arduino if you're still using the immortal WinXP ;)...

##############################################################

atmega328_20.name=Arduino Uno++ 20MHz

atmega328_20.upload.protocol=stk500
atmega328_20.upload.maximum_size=30720
atmega328_20.upload.speed=57600

atmega328_20.bootloader.low_fuses=0xFF
atmega328_20.bootloader.high_fuses=0xDA
atmega328_20.bootloader.extended_fuses=0x05
atmega328_20.bootloader.path=atmega
atmega328_20.bootloader.file=ATmega328_20MHz.hex
atmega328_20.bootloader.unlock_bits=0x3F
atmega328_20.bootloader.lock_bits=0x0F

atmega328_20.build.mcu=atmega328p
atmega328_20.build.f_cpu=20000000L
atmega328_20.build.core=arduino

----------------- End Of Code ----------------

Step 2: Create new file with name ATmega328_20MHz.hex under hardware/arduino/bootloaders/atmega sub-directory with following content:

------------- Start Of Code --------------

:107800000C94343C0C94513C0C94513C0C94513CE1
:107810000C94513C0C94513C0C94513C0C94513CB4
:107820000C94513C0C94513C0C94513C0C94513CA4
:107830000C94513C0C94513C0C94513C0C94513C94
:107840000C94513C0C94513C0C94513C0C94513C84
:107850000C94513C0C94513C0C94513C0C94513C74
:107860000C94513C0C94513C11241FBECFEFD8E036
:10787000DEBFCDBF11E0A0E0B1E0ECE8FFE702C061
:1078800005900D92A230B107D9F712E0A2E0B1E065
:1078900001C01D92AD30B107E1F70E94313D0C945B
:1078A000C43F0C94003C982F92959F709A30B8F08A
:1078B000292F295A8F708A3078F0982F995A809101
:1078C000C00085FFFCCF2093C6008091C00085FFDB
:1078D000FCCF9093C6000895982F905DF0CF292F8C
:1078E000205DE8CF982F8091C00085FFFCCF90935A
:1078F000C6000895EF92FF920F931F93EE24FF248A
:1079000087018091C00087FD17C00894E11CF11C1D
:10791000011D111D81EDE81682E1F80683E10807DB
:1079200080E0180770F3E0910401F09105010995DA
:107930008091C00087FFE9CF8091C6001F910F9111
:10794000FF90EF9008950E947A3C982F8091C0009C
:1079500085FFFCCF9093C600913628F4903308F051
:107960009053892F08959755892F08951F930E944A
:10797000A33C182F0E94A33C1295107F810F1F91EA
:1079800008951F93182F882321F00E947A3C1150EC
:10799000E1F71F9108951F93182F0E947A3C8032BF
:1079A00049F0809103018F5F809303018530C1F01E
:1079B0001F9108958091C00085FFFCCF84E18093E2
:1079C000C6008091C00085FFFCCF1093C600809157
:1079D000C00085FFFCCF80E18093C6001F91089511
:1079E000E0910401F091050109951F9108950E940D
:1079F0007A3C803241F0809103018F5F80930301D4
:107A0000853081F008958091C00085FFFCCF84E12E
:107A10008093C6008091C00085FFFCCF80E18093F9
:107A2000C6000895E0910401F091050109950895BB
:107A300044EF51E08823A1F02D9A28EE33E0FA01BB
:107A40003197F1F721503040D1F72D9828EE33E0EF
:107A5000FA013197F1F721503040D1F7815061F7A9
:107A600008953F924F925F926F927F928F929F9272
:107A7000AF92BF92CF92DF92EF92FF920F931F933C
:107A8000CF93DF93000084E18093C4001092C5007F
:107A900088E18093C10086E08093C2005098589A94
:107AA000259A81E00E94183D24E1F22E9EE1E92E04
:107AB00085E9D82E0FE0C02E10E1B12EAA24A394A0
:107AC000B1E49B2EA6E58A2EF2E57F2EE0E26E2E33
:107AD00079E4572E63E5462E50E5352E0E947A3C18
:107AE0008033B1F18133B9F1803409F46FC081344E
:107AF00009F476C0823409F485C0853409F488C05D
:107B0000803531F1823521F1813511F1853509F466
:107B100085C0863509F48DC0843609F496C0843753
:107B200009F403C1853709F472C1863709F466C0C8
:107B3000809103018F5F80930301853079F6E09196
:107B40000401F091050109950E947A3C803351F6B9
:107B50000E94F73CC3CF0E947A3C803249F7809163
:107B6000C00085FFFCCFF092C6008091C00085FF69
:107B7000FCCF9092C6008091C00085FFFCCF809220
:107B8000C6008091C00085FFFCCF7092C600809136
:107B9000C00085FFFCCF6092C6008091C00085FFC9
:107BA000FCCF5092C6008091C00085FFFCCF409270
:107BB000C6008091C00085FFFCCF3092C600809146
:107BC000C00085FFFCCFB092C60088CF0E947A3CEF
:107BD000863808F4BDCF0E947A3C0E94F73C7ECFE5
:107BE0000E947A3C803809F49CC0813809F40BC1AA
:107BF000823809F430C1883909F48FC080E00E94CE
:107C0000CB3C6CCF84E10E94C13C0E94F73C66CF24
:107C100085E00E94C13C0E94F73C60CF0E947A3C04
:107C2000809306010E947A3C809307010E94F73CF2
:107C300055CF0E947A3C803309F411C183E00E9441
:107C4000C13C80E00E94CB3C49CF0E947A3C8093AB
:107C500009020E947A3C8093080280910C028E7F78
:107C600080930C020E947A3C853409F409C180910A
:107C7000080290910902892B89F000E010E00E942F
:107C80007A3CF801E85FFE4F80830F5F1F4F8091C1
:107C90000802909109020817190788F30E947A3C9C
:107CA000803209F045CF80910C0280FFF5C06091D1
:107CB000060170910701660F771F709307016093AB
:107CC0000601A0910802B09109021097C9F0E8E0FE
:107CD000F1E09B01AD014E0F5F1FF999FECF32BD60
:107CE00021BD819180BDFA9AF99A2F5F3F4FE41729
:107CF000F50799F76A0F7B1F7093070160930601E0
:107D00008091C00085FFFCCFF092C6008091C0003A
:107D100085FFFCCFB092C600E1CE83E00E94CB3C51
:107D2000DDCE82E00E94CB3CD9CE0E947A3C80938B
:107D300009020E947A3C809308028091060190918A
:107D40000701880F991F90930701809306010E94F5
:107D50007A3C853409F49AC080910C028E7F80931E
:107D60000C020E947A3C803209F0B8CE8091C000AB
:107D700085FFFCCFF092C600A0910802B0910902E5
:107D80001097C1F180910C02082F0170182F1695E1
:107D90001170E0910601F0910701AF014F5F5F4F55
:107DA000BA0120E030E00023B1F4112339F49491BA
:107DB0008091C00085FFFCCF9093C6002F5F3F4F9E
:107DC000CB010196FA012A173B0780F4BC014F5FF3
:107DD0005F4F002351F3F999FECFF2BDE1BDF89A50
:107DE00090B58091C00085FFFCCFE6CF709307016E
:107DF000609306018091C00085FDE5CE8091C000B2
:107E000085FFF8CFE0CE81E00E94CB3C67CE0E9498
:107E10007A3C803209F08CCE8091C00085FFFCCF87
:107E2000F092C6008091C00085FFFCCFE092C600B2
:107E30008091C00085FFFCCFD092C6008091C00029
:107E400085FFFCCFC092C6008091C00085FFFCCFAB
:107E5000B092C60043CE80E10E94CB3C3FCE0E9450
:107E60007A3C0E947A3C182F0E947A3C112309F434
:107E700083C0113009F484C08FE00E94CB3C2ECE29
:107E800080910C02816080930C02F1CE80910C02F3
:107E9000816080930C0265CF809107018823880F51
:107EA000880B8A2180930B02809106019091070133
:107EB000880F991F90930701809306018091080213
:107EC00080FF09C080910802909109020196909369
:107ED000090280930802F894F999FECF1127E091E6
:107EE0000601F0910701C8E0D1E08091080290916D
:107EF0000902103091F40091570001700130D9F35C
:107F000003E000935700E89500915700017001309D
:107F1000D9F301E100935700E89509901990009179
:107F2000570001700130D9F301E000935700E89544
:107F30001395103498F0112700915700017001300B
:107F4000D9F305E000935700E895009157000170C0
:107F50000130D9F301E100935700E895329602977A
:107F600009F0C7CF103011F00296E5CF11248091AF
:107F7000C00085FFC5CEC8CE8EE10E94CB3CAECD01
:0C7F800085E90E94CB3CAACDF894FFCF0D
:027F8C00800073
:040000030000780081
:00000001FF

--------- End of Code ---------

Step 3: desolder the old 16 Mhz crystal from Arduino Uno board. Please note that this action may void your warranty, please proceed on your own risk! If you're unsure with this, perhaps it's better to build a brand new Arduino compatible board by your own from scratch. For example, you can buy Playduino-One kit from Play-Zone — they ship worldwide — for Fr. 19.9 (about USD 21). If you live in Indonesia, you can also purchase Playduino-One Kit from azTech for only Rp150.000,- (less than USD 14).
Step 4: Install a 20 MHz crystal. Soldering should be easy since space on bottom surface is sparse.
Step 5: Burn the bootloader: open Arduino IDE, if you've done step #1 correctly then a new board should be appear under Tools > Board menu with name Arduino Uno++ 20MHz. Select the new board, attach USB cable to Arduino (or ISP programmer if you build Playduino One), and execute Tools > Burn Bootloader command. That's all, now you have a much faster Arduino!

**Arduino-based reflow oven controller with:**
* [PID] loop control
* [Wave Packet] and [Phase Fired] control for AC outputs
* graphic TFT LC-Display, drawing the temperature curves
  * using an [Adafruit 1.8" TFT] or derivate display
* solely controlled using a cheap rotary encoder and its single button
* stores up to 30 temperature profiles in EEPROM
* configurable PID-parameters
* simple, small hardware to drive loads up to 600V and up to 8A
* hardware can
  * measure two temperatures independently
  * drive two AC loads, such as heater and fan
* could also be used for slow coockers
* *Please Note*: Requires Arduino IDE 1.5.x or newer

(c) 2016 John Reichard <john@hobbywizards.com>
in part based on a project (c) 2013 Ed Simmons <ed@estechnical.co.uk> , (c) 2014 Karl Pitrich <karl@pitrich.com>


**Post action shot**

![CycleWithOverflow] | ![Warning]
------------ | -------------


## Warning: This project operates with possibly lethal mains voltage. If you are unsure what to do, don't do it and get help from an experienced tinkerer with professional training.


**Completed build**

![Completed1] | ![Completed2]
------------ | -------------


Introduction
====================

This Reflow Oven Controller relies on an [Arduino Pro Micro], which is similar to the Leonardo and easily obtainable on eb*y for less than $10, plus my custom shield, which is actually more like a motherboard.

As I believe it is not wise to have a mess of wiring and tiny breakout-boards for operating mains powered equipment, I've decided to design custom board with easily obtainable components.

The hardware can be found in the [folder hardware], including the Eagle schematics and PCB layout files. It should fit the freemium version of Eagle. Here are preview images:

![PCB][ImgPCB]
![Schematic][ImgSCH]

From my manufacturing run, I have some spare PCBs and parts. They are available at my [tindie store].

The board contains the [Arduino Pro Micro], very simple [Zero crossing] detection circuit, used to align control logic to mains frequency, two [MAX31855] thermocouple-to-digital converters and two [Sharp S202S01] PCB-mount solid state relays, mounted on cheap [Fischer SK409 50,8] heat sinks. The current software uses only one of the thermocouples, so you need to populate one IC only. If you're lucky, you can get free samples of the MAX31855 from Maxim.

The software uses [PID] control of the heater and fan output for improved temperature stability. The heater AC load is controlled using [Wave Packet] control in order to minimize RF interference and load on the relay. For the fan motor, [Phase Fired] control has been implemented.

Please note that all important timings are *based on the mains frequency*, so the circuit will **not work** properly without mains connection.

But for testing, I've added an additional timer to simulate the zero-crossings, in order to run the software without being connected to mains. The software should work in 50 and 60Hz mains, the 60Hz version is not tested, though.

Errata and construction infos
========

Issue | Notes
------------ | -------------

Code can only be uploded with the Arduino 1.0.6 IDE or the LCD won't dysplay anything in my case.


Screenshots and usage information
========

Image | Information
------------ | -------------
![CycleWithOverflow] | *Display after a cylcle has been completed. The blue line is the setpoint, the red line the actual temperature measured by the thermocouple. Note that the graph wraps around automatically. 'Sp' is the current setpoint calculated by the PID loop. In the lower line there are: Current heater and fan outputs, both in percent, and the current temperature rise or drop rate in °C per second. The graph will draw orientation lines every 50°C up to the peak temperature set in the selected profile.*
![MenuDefault] | *The main menu can be navigated by rotating the encoder (sic!). Clicking enters the menu item, or navigates to the submenu. Doubleclick moves up or back or exits the menu item.*
![FanSpeedEdit] | *To edit a setting, click once to enter edit mode (red cursor), then rotate to change the value, click again to save. Doubleclick will exit without saving.*
![MenuEditProfile] | -
![ProfileSettings] | *Typical solder profile settings...*
![ProfileSettingsEdit] | *These parameters can be easily edited using the encoder as described above.*
![MenuLoadProfile] | *Up to 30 Profiles can be loaded and saved. You have to do this manually, so that you can have 'save-as' functionality without overwriting existing profiles.*
![PIDValues] | *Current pid values for my 1300W 20$ toaster oven.*
![PIDValuesEdit] | *Editing is simple, like above. Note that, unlike with the profile settings, the PID values will be automatically stored to EEPROM when you exit the submenu by doubleclicking.*


Obtaining the source code
====================

Get the code using `git`.

	git clone https://github.com/OricalWorksINC/reflowOvenController

or [download a Snapshot].

I've added some libraries I've used as submodules to the git repositroy, so it is important that, after cloning this repository, you do 

    git submodule update --init

to fetch all involved libraries. (See: [Submodule Cheat Sheet])


Installation
====================

Of course, you need to have the Arduino IDE installed. I've worked with version 1.5.x only and I will not support older versions. Get it from the [Arduino Download] page or upgrade you current Arduino setup.

There as several dependencies you need to install. 

If you are unfamiliar with Arduino Libraries, please read [the library guide].
Basically, each library needs to be liked or copied into your Arduino library folder.

On a Mac, this is how you link the submodule libraries to your Arduino libraries folder:

    cd ~/Documents/Arduino/Libraries
    ln -s ~/Development/<reflow source code>/libraries
    
My code uses [TimerOne] for basic timing, for the 1.8" TFT I've used [Adafruit_ST7735], which requires [Adafruit_GFX]. I **strongly suggest** to use my **modified version** of [Adafruit_ST7735-pit], as it **performs much better**, but requires you to use SPI, which my board does anyway.

For the user interface you require my own [Menu] and [ClickEncoder] libraries, which are included as submodules.

All other libraries need to be downloaded and installed.

After you've installed all libraries, open the Arduino IDE, open the ReflowController.pde sketch (using File->Open).

Select the right hardware from the Tools->Board menu. (Use Leonardo for the Pro Micro)

Compile the firmware (Sketch->Verify) to test everything is installed correctly. If something's wrong, feel free to post an issue here on github, I will look into it.

Now, choose the correct serial port from Tools->Serial Port and then upload the code.
*Remember* that a standard compile will get stuck at "Calibrating..." without proper mains connection, so that zero crossing interrupts can occur.

I could not fit PID Autotuning into the limited space of the Arduino in addition the normal code. So if you want to try to autotune you PID Loop, install the [PID_AutoTune] Library, `#define PIDTUNE 1` in the .ino file, then recompile and download do the Arduino.

As all timing relies on Zero Crossing detection, you need to `#define FAKE_HW 1` and install [TimerThree] when you want to run without actual hardware *and/or* without mains connection.


Things to note
====================

* The [MAX31855] does not like the thermocouple being grounded; It must be isolated from ground or earth.
* The PID Loop must be tuned individually for each oven. It will *not* work out of the box. 
* [PID Autotune] is not very useful, as it seems to be able to tune only to keep a specific temperature value, which is not what we do in a reflow oven. Also, at least my oven seems to be very non-linear when heating up.
* When rewiring inside your oven, use only wiring that can withstand high temperatures. I use silicone coated lace.
* Do not solder wiring inside you oven, the temperature might desolder you joints. **Crimp everything.**
* Use proper earth ground connection for your ovens chassis.



Licensing
====================
```
The MIT License (MIT)

Copyright (c) 2016 JohnReichard
All rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```


[PID Autotune]:https://github.com/br3ttb/Arduino-PID-AutoTune-Library
[Submodule Cheat Sheet]:http://blog.jacius.info/git-submodule-cheat-sheet/
[ESTechnical]:http://www.estechnical.co.uk
[Arduino Download]:http://arduino.cc/en/Main/Software
[folder hardware]:https://github.com/0xPIT/reflowOvenController/tree/master/hardware
[download a Snapshot]:https://github.com/0xPIT/reflowOvenController/archive/master.zip
[the library guide]:http://arduino.cc/en/Guide/Libraries
[PID]:http://en.wikipedia.org/wiki/PID_controller
[Wave Packet]:http://de.wikipedia.org/wiki/Schwingungspaketsteuerung
[Phase Fired]:http://en.wikipedia.org/wiki/Phase-fired_controllers 
[Adafruit 1.8" TFT]:http://www.adafruit.com/products/358
[MAX31855]:http://www.maximintegrated.com/en/products/analog/sensors-and-sensor-interface/MAX31855.html
[Fischer SK409 50,8]:http://www.pollin.de/shop/dt/NzE5OTY1OTk-
[Sharp S202S01]:http://sharp-world.com/products/device/lineup/data/pdf/datasheet/s102s01_e.pdf
[Zero crossing]:http://en.wikipedia.org/wiki/Zero_crossing
[TimerOne]:http://playground.arduino.cc/Code/Timer1
[TimerThree]:http://playground.arduino.cc/Code/Timer1
[Adafruit_ST7735]:https://github.com/adafruit/Adafruit-ST7735-Library
[Adafruit_GFX]:https://github.com/adafruit/Adafruit-GFX-Library
[Adafruit_ST7735-pit]:https://github.com/0xPIT/Adafruit-ST7735-Library
[Menu]:https://github.com/0xPIT/menu
[ClickEncoder]:https://github.com/0xPIT/encoder
[Arduino Pro Micro]:https://www.sparkfun.com/products/12640
[tindie store]:https://www.tindie.com/products/0xPIT/reflow-oven-controller-motherboard-for-arduino-pro-micro/

[CycleWithOverflow]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/CycleWithOverflow.jpg
[FanSpeedEdit]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/FanSpeedEdit.jpg
[MenuDefault]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/Menu.jpg
[MenuLoadProfile]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/MenuLoadProfile.jpg
[MenuEditProfile]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/MenuEditProfile.jpg
[PIDValuesEdit]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/PIDValuesEdit.jpg
[ProfileSettings]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/ProfileSettings.jpg
[PIDValues]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/PIDValues.jpg
[ProfileSettingsEdit]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/ProfileSettingsEdit.jpg

[Warning]:http://www.proshieldsafetysigns.co.uk/signs/59793_signs.jpg
[ImgPCB]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/hardware/v0.2.brd.preview.png
[ImgSCH]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/hardware/v0.2.sch.preview.png

[ImgMissingTrace]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/MissingTrace.jpg
[Completed1]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/Completed1.jpg
[Completed2]:https://raw.githubusercontent.com/0xPIT/reflowOvenController/master/images/Completed2.jpg
