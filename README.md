# Mighty 1284P: An Arduino core for the ATmega1284P #
  

## What is it? ##

Everything you need to run [Arduino](http://arduino.cc/) on an [ATmega1284P](http://www.atmel.com/devices/ATMEGA1284P.aspx) microcontroller.

This is a refreshed version of [maniacbug's mighty-1284p core](https://github.com/maniacbug/mighty-1284p) which was based on Arduino 1.0. With the invaluable help of many kind folks on the Arduino forum, I was able to produce this updated core. (If you're interested, and a bit masochistic, [here](http://forum.arduino.cc/index.php?topic=235521.0) is the rather lengthy discussion that took place during the process of updating the core.)

## Automatic installation using Arduino Board Manager <a name="autoinstallation"></a>

1. Open Arduino IDE.

2. Choose **File** -> **Preferences**

3. In **Additional Boards Manager URLs:** field add this URL:
https://raw.githubusercontent.com/jvitkauskas/mighty-1284p/ide-1.6.x-boards-manager/package_jvitkauskas_mighty-1284p_index.json

4. Press **OK**

5. Choose **Tools** -> **Board: <any>** -> **Boards Manager...**

6. Click on **mighty-1284p** and press **Install** button.

7. Now you should be able to select additional boards from **Tools** menu

## Manual installation <a name="installation"></a>

1. Go to https://github.com/jvitkauskas/mighty-1284p, click the **Download ZIP** button and save the ZIP file to a convenient location on your computer.

2. Ensure that the Arduino IDE is **not** running.

3. Go to your Arduino **hardware** folder.

4. Create folder named **mighty-1284p** and then inside it create **avr** folder.

5. Unzip the downloaded file contents into the **avr** folder.

6. The following folders and files should now exist:

	- hardware\mighty-1284p\avr\bootloaders
	- hardware\mighty-1284p\avr\libraries
	- hardware\mighty-1284p\avr\patched-3rd-party-libs
	- hardware\mighty-1284p\avr\variants
	- hardware\mighty-1284p\avr\boards.txt
	- hardware\mighty-1284p\avr\boards.txt.alt
	- hardware\mighty-1284p\avr\.gitignore
	- hardware\mighty-1284p\avr\README.md

7. The mighty-1284p compatible "official" patched libs are located to be used as default when a mighty-1284p board is selected in the **Board** menu by being in **hardware\mighty-1284p\avr\libraries**. **However**, be aware that a version of any of these libraries located in **[sketchfolder]\libraries** will take precedence over the corresponding mighty-1284p patched version:

    - Ethernet  
    - Firmata  
    - GSM  
    - SD  
    - Servo

    Unfortunately, in its present design (IDE 1.6.5) **Library Manager** installs and updates libraries to **[sketchfolder]\libraries**. This obviously presents a potential problem if you are using **Library Manager**. The following is the recommended work-around:

    If there are any of the above-named libraries installed in **[sketchfolder]\libraries**, then move those libraries from **[sketchfolder]\libraries** to **[Arduino install folder]\libraries**. This will then allow the mighty-1284p patched libraries to take precedence when (but only when) a mighty-1284p board is selected.

    Finally, note this manual move of the libraries from **[sketchfolder]\libraries** to **[Arduino install folder]\libraries** will need to be repeated after any updating any of the named libraries using **Library Manager**.

    Hopefully, as the design of **Library Manager** is improved, this issue and inconvenience will disappear in future revisions of the IDE.

8. Once all the libraries are verified to be in their appropriate locations, restart the Arduino IDE.  
9. Select the desired board from the Tools > Board menu and enjoy those extra pins and all that extra memory!  

Note: There is an alternative version of the boards.txt file supplied named boards.txt.alt. It provides more combinations of boards and clock speeds than the standard boards.txt selection menu. It uses a two-step selection of board type and then clock-speed via a submenu. As this differs from the standard boards.txt format, it is provided as an option for those users with more specialized needs, while the default boards.txt retains the more familiar style of interface, to minimise any potential for confusion.

To enable the alternate version, rename boards.txt to boards.txt.org, and then rename boards.txt.alt to boards.txt. Restart IDE, and the new selection options will appear. 

## Requirements <a name="requirements"></a>

* Works with Arduino 1.6.3. and later. It may work on other versions as early as 1.5.x but these have not been tested.
* The [USBtinyISP](http://www.adafruit.com/products/46) is advertised as not able to program chips with more than 64K of flash, however there are varying reports of success using it with the ATmega1284P. Sometimes error messages are given but the upload process seems to have worked OK. Be forewarned. YMMV.

## See also <a name="seealso"></a>

http://maniacbug.wordpress.com/2011/11/27/arduino-on-atmega1284p-4/

## Supported Boards <a name="boards"></a>

* **avr-developers.com pinouts 16MHz using Optiboot** - Some people prefer the pinouts from avr-developers.com.  The classic pinouts.
* **Bobuino** - [CrossRoads' board](http://crossroadsfencing.com/BobuinoRev17/index.html) built for maximum compatibility with Arduino Uno-class shields.
* **RFX 1284P Development/Deployment Board** (a.k.a. "Skinny Bob") from [Embedded Coolness](http://embeddedcoolness.com/shop/rfx-1284p-devdep-board-w-prototyping-area-nrf24l01-headers-kit/); also built for maximum compatibility with Arduino Uno-class shields, has prototyping area, configurable 5V/3v3 voltage selection, and nRF24L01+ support.
* **Mighty Mini 1284P** - A small breadboard-friendly version of the Mighty 1284p built with SMT components. Open-source design [available on GitHub](http://goo.gl/5fAHca).
* **"maniacbug" Mighty 1284p 16MHz using Optiboot** - This uses a straightforward pinout that is especially helpful on a breadboard-built unit.

