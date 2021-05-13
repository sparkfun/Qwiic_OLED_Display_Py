Qwiic_OLED_Display_Py
===================

<p align="center">
   <img src="https://cdn.sparkfun.com/assets/custom_pages/2/7/2/qwiic-logo-registered.jpg"  width=200>  
   <img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM.png"  width=240>   
</p>
<p align="center">
	<a href="https://pypi.org/project/sparkfun-qwiic-oled-display/" alt="Package">
		<img src="https://img.shields.io/pypi/pyversions/sparkfun_qwiic_oled_display.svg" /></a>
	<a href="https://github.com/sparkfun/Qwiic_OLED_Display_Py/issues" alt="Issues">
		<img src="https://img.shields.io/github/issues/sparkfun/Qwiic_OLED_Display_Py.svg" /></a>
	<a href="https://qwiic-oled-display-py.readthedocs.io/en/latest/index.html" alt="Documentation">
		<img src="https://readthedocs.org/projects/qwiic-oled-display-py/badge/?version=latest&style=flat" /></a>
	<a href="https://github.com/sparkfun/Qwiic_OLED_Display_Py/blob/master/LICENSE" alt="License">
		<img src="https://img.shields.io/badge/license-MIT-blue.svg" /></a>
	<a href="https://twitter.com/intent/follow?screen_name=sparkfun">
        	<img src="https://img.shields.io/twitter/follow/sparkfun.svg?style=social&logo=twitter"
           	 alt="follow on Twitter"></a>
	
</p>

<img src="https://cdn.sparkfun.com//assets/parts/1/6/1/3/5/17153-SparkFun_Qwiic_OLED_Display__0.91_in__128x32_-01.jpg" align="right" width=200 alt="SparkFun Qwiic OLED Display">

The Python package for the [Qwiic OLED Display](https://www.sparkfun.com/products/17153) board.

This package is a port of the [SparkFun Micro OLED Breakout Arduino Library](https://github.com/sparkfun/SparkFun_Micro_OLED_Arduino_Library)

This package can be used in conjunction with the overall [SparkFun qwiic Python Package](https://github.com/sparkfun/Qwiic_Py)

New to qwiic? Take a look at the entire [SparkFun qwiic ecosystem](https://www.sparkfun.com/qwiic).


## Contents

* [Supported Platforms](#supported-platforms)
* [Dependencies](#dependencies)
* [Installation](#installation)
* [Documentation](#documentation)
* [Example Use](#example-use)

Supported Platforms
--------------------
The qwiic Python package current supports the following platforms:
* [Raspberry Pi](https://www.sparkfun.com/search/results?term=raspberry+pi)
* [NVidia Jetson Nano](https://www.sparkfun.com/products/15297)
* [Google Coral Development Board](https://www.sparkfun.com/products/15318)

Dependencies
================
This driver package depends on the qwiic I2C driver: 
[Qwiic_I2C_Py](https://github.com/sparkfun/Qwiic_I2C_Py)

Documentation
-------------
The SparkFun Qwiic OLED Display module documentation is hosted at [ReadTheDocs](https://qwiic-oled-display-py.readthedocs.io/en/latest/index.html)

Installation
--------------

### PyPi Installation
This repository is hosted on PyPi as the [sparkfun-qwiic-oled-display](https://pypi.org/project/sparkfun-qwiic-oled-display/) package. On systems that support PyPi installation via pip, this library is installed using the following commands

For all users (note: the user must have sudo privileges):
```sh
sudo pip install sparkfun-qwiic-oled-display
```
For the current user:

```sh
pip install sparkfun_qwiic_oled_display
```

### Local Installation
To install, make sure the setuptools package is installed on the system.

Direct installation at the command line:
```sh
python setup.py install
```

To build a package for use with pip:
```sh
python setup.py sdist
 ```
A package file is built and placed in a subdirectory called dist. This package file can be installed using pip.
```sh
cd dist
pip install sparkfun_oled_display-<version>.tar.gz
```
  
Example Use
------------
This example is intended to be used with the [Qwiic OLED Display](https://www.sparkfun.com/products/17153) board. (See the <a href="https://github.com/sparkfun/Qwiic_OLED_Display_Py/tree/main/examples">examples directory</a> for more detailed use cases.)

```python
import qwiic_oled_display
import sys


def runExample():

    #  These lines of code are all you need to initialize the OLED display and print text on the screen.
  
    print("\nSparkFun Qwiic OLED Display - Hello Example\n")
    myOLED = qwiic_oled_display.QwiicOledDisplay()

    if myOLED.is_connected() == False:
        print("The Qwiic OLED Display isn't connected to the system. Please check your connection", \
            file=sys.stderr)
        return
    
    #  Before you can start using the OLED, call begin() to init all of the pins and configure the OLED.
    myOLED.begin()

    myOLED.clear(myOLED.PAGE)  #  Clear the display's buffer

    myOLED.print("Hello World")  #  Add "Hello World" to buffer

    #  To actually draw anything on the display, you must call the display() function. 
    myOLED.display()

runExample()
```

<p align="center">
<img src="https://cdn.sparkfun.com/assets/custom_pages/3/3/4/dark-logo-red-flame.png" alt="SparkFun - Start Something">
</p>
