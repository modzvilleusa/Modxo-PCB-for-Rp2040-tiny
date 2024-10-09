<h1>Modxo Carrier board for use with Waveshare rp2040-tiny or rp2040-zero</h1>
Download the latest Gerbers and BOM from the releases page.

![IMG_1253](https://github.com/user-attachments/assets/f37602a9-f79a-43a2-96df-271a5d4a3954)

<p>The board has been updated to use the latest Modxo 1.0 or PrometheOS firmware.</p>

https://github.com/Team-Resurgent/Modxo/releases/tag/latest

<p>For flashing the firmware, check section 3. Flashing Firmware here</p>

https://github.com/Team-Resurgent/Modxo

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
The lpc rebuild should be like this. Credit to reddit user u/strictlyfocused02 for this image of very clean lpc rebuild wiring.</p>

![lpc_rebuild_strictlyfocused02](https://github.com/user-attachments/assets/77a8541e-2900-4f08-bd49-cae636353577)

<p>1.6 is unique in that the 5v line of the LPC is always active when the console is plugged in. This is no good since the lcd and rgb lighting both run off of 5v. 
Therefore we need to remove the 5v pin from the pinheader and pull 5v from elsewhere.</p> 
<p>Remove the following pin from the pinheader.</p>

![IMG_1250](https://github.com/user-attachments/assets/b2802e55-673a-4d08-8d79-1a3d15fe610a)

Now we're going pull 5v from the vreg near the top of the 1.6 board here. I recommend using 26 or 28awg 

![IMG_1249](https://github.com/user-attachments/assets/45447013-5c01-4922-a1b1-32296a5e6a69)

Now wire the other end the to 5v input pad on the adapter board here. 

![IMG_1251](https://github.com/user-attachments/assets/e80fc9ff-ca87-4dbd-a544-610b6278208e)

<h1>LCD support.</h1> 

**PLEASE NOTE!** - The current public release (at the time of writing 1.4.0) of PrometheOS does not have support for LCD or RGB led output. I've tested a private build in which it is indeed working. However if you're interested in building these specifically for those features, I'd recommend waiting until they're added to the public release of PrometheOS. 

<p>For an lcd you will need to use a spi2par adapter similar to OpenXenmium. 
The spi2par code has been tweaked for modxo, you will want to flash the spi2par firmware from here and follow the wiring diagram. 
I will be making a custom spi2par board soon that uses the same connectors as this modxo board to make the install easier.</p>

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

**I2C pinout**

![i2c pinouts](https://github.com/user-attachments/assets/8b594de7-c147-44b5-b538-1f9f15cf9374)

<h1>Preassembled adapters</h1>

If you'd like to get one of these adapters prebuild (minus the rp2040-tiny) you can grab one from my shop here

https://modzvilleusa.com/products/xbox-modxo-adapter-for-rp2040-tiny















