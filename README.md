# [Mini Pocket Radio ESP32S3-Si4732](https://github.com/halfmanhalftaco/Mini-Pocket-Radio-ESP32S3-Si4732)

This is my modification of the original repo to match up with the slightly-modified hardware present on the
cheaply-sold "mini pocket radio" on Aliexpress. The hardware is very similar to the Lilygo T-Display-S3 but with
some minor pin assignment changes and one additional control signal.

From what I can tell, these radios ship with a barely-modified version of this code, but I could not find a
copy of the modified source code of that (only binary artifacts). The original author's license doesn't require this.

The main things changed were pin assignments for the I2C bus and mute signal. Additionally, the Aliexpress
radio adds an "Amp Enable" signal to the audio amplifier chip that is pulled low and must be asserted high to
get sound out of the speaker/line out.

I also changed the default band plan to suit my needs, but the original band plan can by copy/pasted from the
original elsewhere in this repo.

When using the Arduino IDE, it will detect the board as a "TAMC Termod S3" which has defaults that don't match up with the
actual hardware in this radio. Switch to the "ESP32S3 Dev Module" board and select 16MB Flash with the 
"3MB Flash/9.9MB FATFS" partition scheme to match what the device ships with. I'm using version `2.0.14` of the 
ESP32 board package and the versions of TFT_eSPI and OneButton libraries from the T-Display-S3 repo.

On top of the T-Display-S3 libraries, you will need to install the PU2CLR SI4735 library (I used v2.1.8) and the 
Battery_18650_Stats (v1.0.0) library.

The modified code is in the `Mini_Pocket_Radio` subdirectory. The other subdirectories are unmodified from the upstream.

If anyone has a source for the STL/etc files for the 3D printed parts in the Aliexpress version I'd greatly appreciate if you'd let me know!

-Andrew KI7FXL

---
Original README:


# [SI4735 / SI4732 Radio](https://github.com/ralphxavier/SI4735)

This repository is intended to share my implementations using the Si4735/Si4732 chip with the library written by [PU2CLR/Ricardo Caratti.](https://pu2clr.github.io/SI4735/)

## Contents

* [TTGO T-Display Board](https://github.com/ralphxavier/SI4735/tree/master/TTGO_T-Display)
* [Lilygo T-Display S3 Board](https://github.com/ralphxavier/SI4735/tree/master/Lilygo_T-Display_S3)
