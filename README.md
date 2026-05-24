# CHM_9001_00_Frequency_Conversion
<br><br>
The CHM_9001_00 Trinitron monitor was originally designed for 25kHz horizontal scanline frequency, required for the video on the original HP logic analyzer unit that it was associated with. This makes it difficult to use with a standard VGA source. But with some relatively simple mods, it can be made to work at 31.5kHz for standard 640x480 VGA resolution and 60Hz refresh.<br><br>

## Modifications to CHM-9001-00 CRT boards for operation at 31.5kHz
* 20kOhm resistor in parallel with R504 on Board D in order to bias the horizontal oscillator circuit. Some adjustment of pot RV501 will likely be necessary to get it to sync to 31.5kHz.<br><br>
![D_mod](D_mod1.png)
* 400kOhm resistor in parallel with R018 on Board B in order to sufficiently decrease the duration of the "HD" pulse to fit within a 31.5kHz period. Again, adjustment of the associated pot RV001 is still necessary to get the horizontal raster to look correct.<br><br>
![B_mod](B_mod1.png)
* Optionally, add 47 Ohm resistors across R915, R926, and R935 of Board B. These resistors appear to be for scaling the current sources used on the RGB signals that are sent to the neck board (it appears to use current waveforms instead of voltage, probably to reduce the effects of interference on the associated cable). I found that I needed to add these resistors to boost the current a bit to increase the contrast. I suspect that the increase in horizontal frequency results in a small decrease in some of the flyback-generated supplies, including the one used for the cathode amplifiers. So boosting the RGB signal a bit helps to compensate.<br><br>
* Brightness (blue) and contrast (green) inputs jumpered directly to the 12V (white/red stripe) pin on the "B2" connector/cable, in which case the "Sub Brightness" and "Sub Contrast" pots on Board B can be used to make manual adjustments.<br><br>
![cable](cable_jump1.PNG)
<br><br>
I plan to include more information about the 120V power supply that I designed to run my CHM-9001-00. I'll have more to post soon, hopefully.<br><br>
Tom Verbeure's excellent GitHub repository on the CHM-9001-00 has lots of additional information about this Trinitron monitor, available [here](https://tomverbeure.github.io/2022/10/05/Sony-CHM-9001-00-CRT.html).<br><br>
