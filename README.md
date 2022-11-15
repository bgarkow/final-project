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

**from gpiozero import LED
from gpiozero import DistanceSensor
from time import sleep
from gpiozero import Button

button = Button(13)

sensor = DistanceSensor (echo=23, trigger=24, max_distance=2.0)

red = LED(2)
yellow = LED(3)
green = LED(4)
while True:
  if button.is_pressed:
    while True:
      distance = sensor.distance * 100
      print("Distance: %.2f" % distance)
      sleep(1)
      
      if disance>=0 and distance <= 33:
        red.on()
        yellow.off()
        green.off()
      if distance > 33 and distance <= 66:
        yellow.on()
        red.off()
        green.off()
      if distance > 66:
        green.on()
        red.off()
        yellow.off()**
 
 
To create this code start by opening a terminal on the Rasberry Pi or linux machine in general. Type in the terminal "vim" and whatever the filename is then ".py" to show that is it a python file. For this example the filename is called, "final_project.py". 


After that, vim will open and the script can now be typed. When finished, enter ":wq!" to save the script and exit out of vim. This will return you to the main terminal. 

**Step 5**

Finally enter python3 and whatever the file is called. For this example what was used is, "python3 final_project.py". **Note: If this does not work then python3 may not be downloaded. If not downloaded use, "sudo apt install python3".**

**Conclusion** 
 
The system should now be working after following these steps. Here is a video of what the system should look like if done correctly.

