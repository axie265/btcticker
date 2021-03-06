# Bitcoin (& other tokens) ePaper Ticker 

A Python3 ePaper Cryptocurrency price ticker that runs on a Raspberry Pi connected to a [Waveshare 2.7 inch monochrome ePaper display](https://www.waveshare.com/wiki/2.7inch_e-Paper_HAT). The script periodically takes data from CoinGecko and prints a summary to the ePaper.

A few minutes work gives you a desk ornament that will tastefully monitor Bitcoin's journey moonward.

![Action Shot](/images/actionshot/BasicLunar.jpg)


# Getting started

## Prerequisites

(These instructions assume that your Raspberry Pi is already connected to the Internet, happily running pip and has Python3 installed)

If you are running the Pi headless, connect to your Raspberry Pi using ssh.

Install the Waveshare Python module following the instructions on their [Wiki](https://www.waveshare.com/wiki/2.7inch_e-Paper_HAT).

(To install the waveshare_epd python module, you need to run the setup file in their repository)

```
cd e-Paper/RaspberryPi\&JetsonNano/python
sudo python3 setup.py install
```
## Install & Run

Copy the files from this repository onto the Pi, or clone using:

```
git clone https://github.com/llvllch/btcticker.git
cd btcticker
```


Install the required modules using pip:

```
python3 -m pip install -r requirements.txt
```

If you'd like the script to persist once you close the session, use [screen](https://linuxize.com/post/how-to-use-linux-screen/).

Start a screen session:

```
screen bash
```

Run the script using:

```
python3 btcticker.py
```

Detatch from the screen session using CTRL-A followed by CTRL-D

The ticker will now pull data every 10 minutes and update the display. 

# Interface

The ePaper is slow. There is a lag of a few seconds between button press and a change to the display. 

Here's what the buttons do:
- Button 1: Toggle to next currency listed in config.yaml
- Button 2: Rotate Display -90 degrees
- Button 3: Invert Display
- Button 4: Hide Display. Replace with 1 coin = 1 coin message

Update frequency can be changed in the config.yaml file (default is 600 seconds).

Fork original CODE by "llvllch/btcticker" and customize your coins!
- Update Coins name by changing one of the existing coins to your desired coin in the config.yaml file. Example and quirk: Small love potion should be written as small-love-potion (no spaces). Make sure you then add an Image to go with the coin.  Click Image directory, Click Currency directory, and add file there which should be named nameofyourcoin.bmp.

OR

Fork my changes and just replace the Axie Graphic for your own.
 - Update Graphic (axie) of your custom Coin. Click Image directory, Click Currency directory, delete current small-love-potion graphic and upload 100x100bmp file of your own Axie (rename to small-love-potion.bmp) or do the same with the official SLP graphic.

# Contributing

To contribute, please fork the repository and use a feature branch. Pull requests are welcome.

# Links

- A low(er)-effort kit and frame can be obtained at [https://llvll.ch/btcticker.html](https://llvll.ch/btcticker.html)


# Licencing

The code in this project is licensed under MIT license.
