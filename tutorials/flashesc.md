---
title: Flashing BLHeli to an ESC
layout: default
---

## Flashing BLHeli to an ESC


**If you don’t have BLHeli Suite:**
1. Download and install BLHeli suite. BlHeli Suite 32 is available [here](https://github.com/bitdump/BLHeli/releases), but you can also find it just by searching BLHeli Suite 32. 
2. Note: BlHeli_S is not BLHeli 32
3. What you need depends on the ESC that you’re using.
4. 32 talks to Mamba

**Step 1: Open BLHeli 32 Suite**
1. We use an arduino to talk to the ESC. (There are other options but this is what we use).

**Step 2: Connect the Pins:**
1. On the ESC, we have current, telemetry, 4,3,2,1, VBat and Ground.
2. Different ESCs have different pin-outs for the same connector. (Some might have telemetry and current swapped, or VBat and Ground swapped → look at the actual ESC’s pins)
3. Plug in cable to the ESC:
- Pin that is negative plugs into the ground cable. (i.e. ground goes to ground.)
- Don’t use Plus. This is battery voltage out, and we don’t want to feed it into the Arduino. We only care about ground and signal.
- For our current set up, connect the Arduino digital pins to the ESC pins as follows:
-   Arduino 11 → ESC 1
-   Arduino 10 → ESC 2.
-   Arduino 9 → ESC 3.  (Note: you might not need all four pins)
-   Arduino 8 → ESC 4.
4. Don’t use: Current & Telemetry & VBat

**Step 3: Connect to BLHeli**
*What com port to use?*
1. In BLHeli Suite, click on the port drop down in the bottom left.
- One of them is the arduino.
- To check which one: Go into device manager, unplug arduino & see which one leaves. That device is the arduino you are using.
- Choose it in the port drop down menu in BlHeli Suite.
2. If you need to flash a fresh arduino:
- Go into ‘Make Interface’
- Choose the arduino: here it’s Uno
- Default Board
- Choose 4 way interface
- Next dropdown → Multi
- Click the Arduino 4-way interface to actually flash it.
3. Go to ESC Set up
4. Power the ESC. (connect the battery and turn on your robot).
- *Recommended:* use a smoke stopper to prevent any parts from being ruined in case any of your solder joints are touching. There is one in the left drawer at the right soldering station.
5. In BLHeli, go to the bottom left, click connect. (Make sure your on the correct comport)
6. If it didn’t connect, check the comport, baud, and ‘Select BlHeli interface at the top menu’.
7. In the bottom right, you can right click one of the numbers to isolate it.
8. You can name it by changing the name in the top left.
9. Also care about motor direction. 
9. When you change from ESC to ESC you need to save by hitting ‘Write Setup’ or it **WON'T SAVE**.
