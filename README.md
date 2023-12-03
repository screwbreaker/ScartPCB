# ScartPCB
A little PCB to buld a SCART cable for console and old computers

![Board](https://raw.githubusercontent.com/screwbreaker/ScartPCB/master/render/ScartPCB-bottom.png)

### Summary
This is a little PCB made to make easy to assemble a SCART cable for console and old computers.

### History
As anyone else I made my SCART cables by hand. Using THT components, and by soldering them directly on the SCART connector.
This works well, except for some console. Like the Sega Mega Drive.
The Mega Drive require a lot of stuff inside the connector.
Capacitors, resistors, a boost converter, a little buffer for the csync sygnal.
Make the SCART for the Mega Drive by hand, in the old way is possible, but, is very annoing, and ir require a lot of time.

My original plan was to make a PCB for each console.
But I made this PCB in a way so it can be used almost in any case.
Most console require the same thigns.
Some require a resistor in series with the signal, other require a resistor in parallel with the signal.
Some require a capacitor in serie with the signal, some don't.
Some require a buffer on the csync, some don't.
Some are mono, some are stereo.
Almost all of them require a boost converter to get the 12V to allow the TV to auto switch in the correct aspect ratio.

With this PCB is possible to make a SCART cable for almost every console and computer.
It is pretty versatile.
And is made to fit inside almost any SCART connector, even the cheaper ones available online.

### Basic informations
The components value in the schematic and in the BOM are for a PAL Mega Drive, but read the warnings.

### Warnings
About the csync line, there is no standard value for this.
The Mega Drive have a problem with this signal. In the video connector the csync is connected on the wrong pin of the video encoder.
The csync is connected to the input pin of the encoder, not to the output pin.
This can cause some issue on some TV sets. That's why I placed a buffer on the line.
The buffer can be bypassed if not needed by closing the NOBUF jumper. In this case, do not populate any component on the buffer section.

The csync on the Mega Drive is also a TTL level signal, to compensate this a 300-470 ohm reistor can be placed in series with the signal to reduce the voltage to something more like to the standard.
Most of the time also a 220uF capacitor in series with the signal is required.
Not only the Mega Drive use a TTL signal on the csync, it cab be present also on other systems.

Unfortunately not all TV do like this values for the csync line.
So, the values can be adjusted to match your TV set requirements.
Be careful with the level of the signals, they must be in a range that do not cause any damage to your TV.

The values on the csync line, that are on the schematic or in the BOM are for a PAL Mega Drive.
With this set of components I can use my modded MD on my TV, by switching from PAL to NTSC withouth any issue.
To make the SCART for other systems, use the components in theyr own SCART schematic.

### How it work
The PCB allow to put components in series and in parallel with the signals.
This allow to use this PCB to buld almost any SCART cable for any system.

To make a Mega Drive cable is necessary to put a 220uF capacitor in series with the RGB signals, since is really complicated to find small, and cheap SMD capacitors of this value, the PCB allow to put multiple capacitors in parallel. So, to make a 220uF capacitor is possible to put two 100uF 1206 plus one 22uF 0603.

To make a SNES cable put a 0 ohm resistor in place of RR1, RG1, RB1, and place a 75 ohm resitor to ground on each singal by using RR2, RG2, RB2.

If you have a mono audio, like in the first model of Mega Drive, is possible to close the MONO jumper, this make a short on the left and right signal.

The video buffer is there mostly for the Mega Drive, it is nor required on most of the other systems.
To bypass the video buffer, close the NOBUF jumper, in this case do not populate any components on the buffer section.

The RGB jumper can be left open on systems that don't have an RGB output, like a C64.

In general, choose the components to match what do you need to make your video cable. By using 0 ohm resistor as jumper is possible to make almost any combination.

### BOM
The BOM is for a PAL Mega Drive.
To make SCART cables for other system choose the components according to the specific schematic.

### PCB Manufacturing
Unfortunately, due to the space contrainst inside the SCART connector, this PCB is a 4 layer board.
And for the same reason, some components are 0402.

The PCB still very cheap to produce, since it is very small, and it use standard via and traces.

Soldering 0402 components by hand require a bit of skill on soldering.

### Bonus
Almost all the SCART connector I bought have an hawful issue. The cable locker. The plastic thing that close the SCART shell. Is made of the most brittle material in the world.
Initially I tought that this is because I got the cheapest SCART connector avilabel on internet.
But even the one bought on thust resellers or on electronic shops have this issue.
So, I made a replacement that can be 3D printed. It's far to be perfect. I have no skills on CADs. But it do the job.

### License
The PCBs are under the CERN OHL license.
The firmwares, under the GPL3.

This is an OPEN project.
So, like any other project like this, the hope is that others can improve it an reshare with the community.
Don't go out this basic guideline.

### Disclaimer
The hardware and the software are provided to you 'as is' and without any express or implied warranties whatsoever with respect to its functionality, operability or use, including, without limitation, any implied warranties of merchantability, fitness for a particular purpose or infringement. We expressly disclaim any liability whatsoever for any direct, indirect, consequential, incidental or special damages, including, without limitation, lost revenues, lost profits, losses resulting from business interruption or loss of data, regardless of the form of action or legal theory under which the liability may be asserted, even if advised of the possibility or likelihood of such damages.

