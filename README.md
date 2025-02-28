<h1>Modxo Carrier board for use with Waveshare rp2040-tiny or rp2040-zero</h1>
Download the latest Gerbers and BOM from the releases page.

![Screenshot_3](https://github.com/user-attachments/assets/f6cd644e-5291-44d5-9a10-b467c80b790d)

<h1>Firmware</h1>

<p>The board has been updated to use the latest Modxo 1.0 or PrometheOS firmware.</p>

https://github.com/Team-Resurgent/Modxo/releases/tag/latest

<p>For flashing the firmware, check section 3. Flashing Firmware here</p>

https://github.com/Team-Resurgent/Modxo

<p>I recommend getting the latest build of prometheos from pandora/xbins here</p>

https://github.com/Team-Resurgent/Pandora/releases/tag/V1.0.7

<p>You can find it under Xbox/Console Based Applications/bios/PrometheOS/ Use the Modxo uf2 for rp2040-zero / tiny </p>

Here's a video of how to use Pandora by MrMario2011

https://www.youtube.com/watch?v=Uk_AdbIqSWE&t=1s

<h1>Assembly</h1>
In order to use the RGB led output, You will need to run a wire from the bottom right pad of the RGB led to the RGB pad on the PCB like so.

![IMG_1255](https://github.com/user-attachments/assets/61c7ff4a-5ed2-4fc8-bc32-996b869e4a24)


<h1>Installation (1.0 - 1.4)</h1>

<p>Remove the following pin from the pinheader. I like to use a pair of flush cutters to push the pin out from the bottom then use the flush cutters to grab the pin and pull it out from the top.</p>

![IMG_1243](https://github.com/user-attachments/assets/3ae1c83e-5911-4d70-b2ce-20e8d06d57e5)
![IMG_1241](https://github.com/user-attachments/assets/21c5bd0b-2db4-48c6-9749-0ba2b586394a)
![IMG_1238](https://github.com/user-attachments/assets/14ae1f93-e90f-450c-9cc7-c6db32ba11b2)

<p>Solder the pinheader to the xbox lpc port, plug in to modxo adapter board and solder a wire from D0 on the xbox motherboard to the D0 pad on the Modxo adapter. These vias are quite weak, I recommend 30awg kynar single core and tacking the wire to the board with some uv resin. If the wire gets snagged it can easily pull up the via along with the trace it's connected to. The uv resin will protect the joint in the event the wire gets snagged.</p>

![d0](https://github.com/user-attachments/assets/fd69e073-a91a-47c9-8a60-6056d05772e9)

<h1>Installation (1.6)</h1>

<p>For 1.6 you will need to do an LPC rebuild along with lframe rebuild like you would for an Open Xenium install. 
The lpc rebuild should be like this.
Try with the Lframe rebuilt method first. If it gives you issues booting try the lframe grounded install. 
With lframe grounded you won't be able to boot the stock bios unless you flash the stock bios to the Modxo.</p>

With Lframe rebuilt
![FF586098-C050-4E43-8B7D-17D598F497E0](https://github.com/user-attachments/assets/228ba1be-fea1-4963-a583-0f95e122f3d8)

With Lframe Grounded 
![2BC9E43C-2028-46A6-ADC2-11434AEFD480](https://github.com/user-attachments/assets/51e14cf8-0c9d-4583-9b30-3b4ebff9d4dd)

<h1>V3 board install (1.6)</h1>
<p></p>The V3 can be identified by having the hole in the center for easier rp2040 zero installs, extra xb i2c port up top, and power switch ic that shuts off 5v from the lpc when 3v3 isn't active (shout out Ack Ack on the XS discord for sharing the idea)</p>

![Screenshot_3](https://github.com/user-attachments/assets/9a9d6244-c199-426d-ae88-92d9a2aba52d)
<p>To install this revision</p>
<p>-install the pinheader</p>
<p>-Do an lpc rebuild using one of the above photos or using an lpc rebuild qsb.</p>
<p>-plug in the Modxo.</p>
<p>If you have issues booting try grounding Lframe instead of rebuilding it (Second LPC rebuild photo)</p>


<h1>V2 board install (1.6)</h1>

<p>1.6 is unique in that the 5v line of the LPC is always active when the console is plugged in. This is no good since the lcd and rgb lighting both run off of 5v. 
Therefore we need to remove the 5v pin from the pinheader and pull 5v from elsewhere.</p> 
<p>Remove the following pin from the pinheader.</p>

![IMG_1250](https://github.com/user-attachments/assets/b2802e55-673a-4d08-8d79-1a3d15fe610a)

Now we're going pull 5v from the vreg near the top of the 1.6 board here. I recommend using 26 or 28awg 

![IMG_1249](https://github.com/user-attachments/assets/45447013-5c01-4922-a1b1-32296a5e6a69)

Now wire the other end the to 5v input pad on the adapter board here. 

![IMG_1251](https://github.com/user-attachments/assets/e80fc9ff-ca87-4dbd-a544-610b6278208e)

**NOTE - Some people have reported  stability issues using the external 5v source. 
Hopefully this can be addressed in the software at some point. For better support for 1.6 consoles, use the V3 adapter.
If you purchased a V2 from my shop and would like to exchange it for a V3, Send an email with your order number to modzvilleusa@proton.me and I'll swap it out for you.**

<h1>LCD support.</h1> 

**PLEASE NOTE!** - The current public release (at the time of writing 1.5.0) of PrometheOS Supports LCDs over i2c, smbus or with a spi2par adapter using modified code for Modxo. 

<p>I will be updating this section with a proper guide soon.</p>

https://github.com/Team-Resurgent/ModxoLegacyLCD/blob/main/ArdruinoProMicro/README.md

<h1>Pinout</h1>

<p>This board was designed with the latest Modxo 1.0 pinout for rp2040-zero / rp2040-tiny</p>

![RP2040_Zero_pinout](https://github.com/user-attachments/assets/8bb324b5-3fb9-411d-94c5-e6c52e82c89f)

Here are the pinouts for the various connectors. 
for expansion boards, we've decided to do a 1:1 pinout which means the cables will have inverted connectors. 
If you would like to design an add on board, please keep this as a standard. 


**LCD Pinout**

![lcd pinout](https://github.com/user-attachments/assets/77d86c3c-afd5-4e27-962c-50bbee0bff0d)

**RGB pinout**

![RGB_pinout](https://github.com/user-attachments/assets/8cd43ad6-99b2-4169-82a5-e4a21057de6a)

**I2C pinout V2** 
The V2 uses 3.3v for the power source. 
![i2c pinouts](https://github.com/user-attachments/assets/8b594de7-c147-44b5-b538-1f9f15cf9374)

**I2C pinout V3**
On the V3 changed to 5v on both of the i2c connectors. 

![Screenshot_2](https://github.com/user-attachments/assets/4213d602-086b-42dc-844c-78ed21b4d74e)

![Screenshot_4](https://github.com/user-attachments/assets/c7db8b43-8653-4c1b-ad5f-078ddd10be3e)

<h1>Early V3 Silkscreen issues</h1>
<p>The first small run of the v3 adapters sold on my shop have a couple of blunders with the silkscreen. </p>

![OXHD MISPRINT](https://github.com/user-attachments/assets/d24528b4-1931-4675-a2f1-2c2f9b0d71e6)

The second i2c port is labeled OXHD. This is due to a miscomunication. I was under the impression that the OXHD would tap into I2C, I was mistaken. 
I've opted to keep the second i2c port as I believe it will come in handy down the line. 
These revisions also have the polaritory of the 0603 led reversed on the silkscreen. Since these only exist already manufactured, it shouldn't be an issue for anyone but figured it's worth a mention. 




<h1>Preassembled adapters</h1>

If you'd like to get one of these adapters prebuilt you can grab one from my shop here

https://modzvilleusa.com/products/xbox-modxo-adapter-for-rp2040-tiny















