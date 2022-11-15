# Final Project

These are the step by step instructions to make a system using a breadboard and Rasberry Pi. What this sytem does is uses a distance sensor to light up different LED lights depending how far away they are from the distance sensor. Also after starting up python, a button is needed to start the system. This system could be used as a detector to see how far you are from something with lights when you can't see how far you are from something. For example, you could put it on the back of your car. When you are parallel parking the lights would light up depending on how far you are from the car behind you.

The needed materials will be:
 - Rasberry Pi
 - Breadboard
 - Button
 - Distance Sensor
 - Eight male-to-female jumper cables
 - Three LED lights
 - Five resistors

Here is a final look at the system when it is all connected:

![Final Picture](https://user-images.githubusercontent.com/115035059/201990778-a829a142-8247-4b92-91cd-689e2588886f.jpeg)

**WARNING! You could permanently damage your Pi:**

- Turn off your Pi when connecting cables to the GPIO ports.
- Use a resistor, the LED will consumer as much voltage as it can. This may damage         your Pi.
- Do not bend the GPIO pins.
- Ground yourself electrically before proceeding.

**Step 1**

First I connected the three LED lights to the breadboard shown below:


I hooked up the male-to-female wire to the cathode of each of the led. I then connected each of the resistors to each of the anodes of the LEDs. The red LED light is connected to GPIO 2. The yellow light is connected to GPIO 3. The green light is connected to GPIO 4. There is also a ground wire that is connected to pin 9. 

**Step 2**
The next step that I took is connecting the distance sensor to the Rasberry Pi. Here is a picture of what that looked like:


The ground wire is connected to pin 6 on the Rasberry pi. The echo wire is connected to GPIO 23. The trigger wire is connected to GPIO 24. Finally the VCC wire is connected to pin 2, which is giving out 5 volts. One of the resistors is connecting the ground wire and the VCC wire. The other resistor is connected from the echo to the VCC wire.

**Step 3**
In this step, the button is going to be connected. To do this place the button and wires just like this:


The ground wire is connected to pin 39. The other male-to-female wire is connected to GPIO 13.

**Step 4**
Now for the part that gets the system to work, the code. The code that can be used is shown below:

