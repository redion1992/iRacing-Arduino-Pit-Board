## iRacing-Arduino-Pit-Board

The iRacing Arduino Pit Board is designed to work on a 2.8 inch (320 x 240) TFT or LCD screen that is supported by the Adafruit graphics library.  Screens smaller than 2.8 inches will not work correctly and will crop significant amounts of Pit Board information.

Video of v0.4 in action.

<a href="http://www.youtube.com/watch?feature=player_embedded&v=LYWg47O0CII
" target="_blank"><img src="http://img.youtube.com/vi/LYWg47O0CII/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>


### Changelog: ([Full Changelog](https://github.com/Grimzentide/iRacing-Arduino-Pit-Board/blob/master/Changelog))
### Version 0.4 - 2015-08-22
#### Front End (Arduino)
* Added - Session Laps title changes to Session Time when in a timed session
* Added - Session Time displayed for timed sessions (previously blank)
* Added - Remaining Time displayed in timed sessions (previously blank)
* Added - "Unlimited" shown as session time in offline testing mode
* Fixed - Various bug fixes
* Changed - GUI alignment
#### Back End (Python)
* Changed - Fuel required now shows the maximum tank size when the required fuel exceeds amount you can fit in
* Fixed - Various bug fixes


### Hardware
* [Arduino Uno or Uno Clone](https://www.arduino.cc/en/Main/arduinoBoardUno)
* [2.8" TFT Shield via eBay](http://www.ebay.com.au/itm/381238351575?_trksid=p2060353.m2749.l2648&ssPageName=STRK%3AMEBIDX%3AIT) <-- This is the actual TFT I purchased on eBay Australia.
  * [The underside of the TFT screen looks like this](http://i.imgur.com/zYKCSf8.jpg)


### Software Install Procedure

#### Python Side
1. Install [Python 3.4.x](https://www.python.org/)
2. Install [PyYaml 3.11](http://pyyaml.org/wiki/PyYAML)
3. add python directory to your PATH environment variable
4. Install [Python iRacing SDK](https://github.com/kutu/pyirsdk) by [Mihail Latyshov](https://github.com/kutu)
  * pip3 install pyirsk
5. Download the iRacing Arduino Pit Board Back End python file to your computer

#### Arduino Side
1. Install [Arduino IDE](https://www.arduino.cc)
2. Install [Adafruit GFX graphics core library](https://github.com/adafruit/Adafruit-GFX-Library)
3. Install [Adafruit 2.8" TFT display library](https://github.com/adafruit/TFTLCD-Library)
  * Not all TFT's are supported and it may take some work on your behalf to identify and get the above libraries working
4. Download the iRacing Arduino Pit Board TFT Front End.ino sketch to your computer and open it in the Arduino IDE
5. Ensure line 58 in the Arduino front end uses the correct identifier for your TFT Screen.  The test sketches in the Adafruit core library will assist with this identification.
  * eg: uint16_t identifier = 0x9325;
5. Upload the iRacing Arduino Pit Board TFT sketch onto your Arduino Uno

### How to use the iRacing Arduino Pit Board
**Note:** If you can not get the test scripts in the Adafruit libraries to display the test graphics screens, the iRacing Arduino Pit Board will not work at all.

1. Plug in your Arduino with TFT screen into an available USB port
2. Determine which COM port your Arduino Uno is connected to
3. Edit the first section of the iRacing Arduino Pit Board Back End python file to ensure the COM port and operating system is correct
4. Run the python file from a command prompt or set it to auto load from a launcher (eg [iAppStarter](http://www.fulhack.org/iappstarter/))
  1. python "iRacing Arduino Pit Board TFT Back End.py"
5. Load iRacing Simulator
