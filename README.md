# openrocket_internship
Static test pads are often used to conduct systematic tests on rocket motors and engines  of various sizes and types. To produce time-resolved thrust data, a programme controls  both the motor ignition and data gathering devices



Rocket Motor Static Test Pad 

What is a Rocket Motor Static Test Pad?
•	Static test pads are often used to conduct systematic tests on rocket motors and engines of various sizes and types. To produce time-resolved thrust data, a programme controls both the motor ignition and data gathering devices.


Basic working principle of Rocket Motor Static Test Pad:

 ![image](https://user-images.githubusercontent.com/11870995/191512656-11460595-9636-4088-8c0a-1971eb0b6e11.png)


Design: 
The rocket engine is held in place by the frame, which also provides stability and support while the rocket motor is fired for testing. The avionics bay, which houses the avionic components, is likewise housed in the frame.
Avionics: 
The avionics include components that collect and analyse data, such as the load cell (for measuring thrust), Temperature sensor, and the SD Card (for storing the data of thrust and temperature).
The rocket motor is mounted on or near to the motor mount depending on the orientation of the rocket motor, and when it is fired, the load cell is deflected/compressed, resulting in the rocket motor's thrust, which is processed and stored using the avionic circuit.

Why to make Rocket Motor Static Test Pad?
Before being employed for spaceflight, launch vehicles are frequently put through system tests. Prior to launch, a fully integrated space launch vehicle and its associated ground support equipment go through a wet dress rehearsal and a more extensive static fire. During the WDR or static fire, the spacecraft or payload may or may not be attached to the launch vehicle, but enough components of the rocket and all relevant ground support equipment are in place to help verify that the rocket is ready for flight, with the goal of allowing problems to be seen before the actual launch. A wet dress rehearsal is included in the static fire test, as well as firing the engines at maximum force. The launch vehicle, with or without payload, is held firmly attached to the launch mount while the engine is operated for a few seconds. This device measures pressure, temperature, and propellant-flow gradients while testing engine start-up. The information acquired in these tests may be utilised to create a unique set of criteria that would be used in the automatic launch software's go/no-go decision tree on the actual launch day, which is usually a few days later. The engines have been fired for up to twelve seconds in some static fire tests, while shorter firings are more common.


Architecture:
1]DESIGN
•	Good strength/weight ratio
•	Good aesthetics and ergonomics
•	Easy assemble/disassembly
•	Includes electronics & power installation
•	Simulate operation with minimal errors
2]AVIONICS
•	Acquire and process data
•	Design electrical power system
•	Build a test control system
•	Data storage
•	Facilitate real-time data transmission & reception



Basic components, software required to build a Static Test Pad:

>List of Component for design:                      >List of Component for Avionics:

Clamp Holder                                                                    Load Cell
Clamp	                            HX711 
Clamp Plate                                                                       Arduino UNO 
      Clamp rubber                                                                    SD Card Module 
Cover	Resistor
Hexagonal	capacitor
Ring(each)	LED
Base Plate	LCD
Rods	Buzzer
Nuts	relay
Bolts	battery
	Push Button and SPDT switch
 	Temperature senor


•	List of Software’s used:

1.Arduino IDE- used to programme Arduino to carry out particular avionics’ commands

2.Proteus- used in simulating the complete Avionics.

3.Fusion 360- used for designing the test pad

4.Eagle CAD-used for designing the PCB for our final product avionics
          
	
Procedure to build Avionics for Static Test Pad:

As I was Avionics designer, I will primarily discuss about the procedure to build the avionics and little bit touch on design side. My individual contribution was Ignition, thrust measurement, GUI and complete avionics.

Procedure to build avionics is separated into three parts:

1.Igniton:
 ![image](https://user-images.githubusercontent.com/11870995/191512732-169502ee-7864-4ffa-8fbb-4dc046ca0437.png)

Fig 1

The fig 1 shows the first most part which was designed and simulated to perform ignition.
It consists of Relay, a 10 volts battery. And a ignitor . First turn off the safety switch, then the ignition button to be pressed in order for the ignition to begin. Once the button is pressed, around 10 secs wait time for the relay to be turned on in order to ignite the motor. The LED D1 will indicate if safety switch is turned on.
Output of ignition:
 ![image](https://user-images.githubusercontent.com/11870995/191512763-aab7f21a-0c60-4ab8-be1d-7f750e7f0214.png)

it can be seen that, once the safety switch is switched off and the button is pressed, the ignition period begins, which is around 10 seconds, and then the ignition is started for approximately 2 seconds.	
2. Thrust measurement and LCD:
 ![image](https://user-images.githubusercontent.com/11870995/191512804-e5951433-3e89-462f-8f95-bf10d020a728.png)

It can be deduced from the preceding diagram that the simulation of thrust will be presented on the LCD as well as serial monitor. It consists of load cell, hx711 amplifier, capacitors, resistors, transistors and LCD. We connected the outputs of hx711 to A0 and A1 of Arduino analog pins. It can be connected to digital pin as well. Due to limited pins in digital, we planned to use the analog pins.
Output:
 ![image](https://user-images.githubusercontent.com/11870995/191512829-d001b9cd-a997-4956-b153-4dfc22134bd8.png)

The output of thrust and time can be seen in above picture. It was programmed to show that first column is where time can be seen and in second column thrust in newton can be visualized. At 0.80 secs I have changed the load cell value and the thrust is changed can be observed.
3.SD card and Temperature sensor:
 
![image](https://user-images.githubusercontent.com/11870995/191512863-201ae335-65b5-42ff-8a33-608ddff68fb7.png)

From the above image it can be deduced that, it is the simulation diagram of SD card and temperature sensor. The working is that once ignition starts the temperature start to log the data to SD card in a notepad or excel sheet ,which can be used for plotting the graph between thrust ,time and temperature.

GUI for plotting graphs:
 
Above picture is the GUI which I created for plotting graphs of any two column, which can be selected from first data and second data in the GUI. For plotting we can select different type of plots.

Complete Avionics:
![image](https://user-images.githubusercontent.com/11870995/191512906-7ddeae1f-aeb9-48b7-9b2f-7b8ccec8637a.png)

 
Ignition, thrust measurement, and SD card with temperature has been combined and simulated in order to create complete avionics.

Output:
 ![image](https://user-images.githubusercontent.com/11870995/191512932-c3789bba-2af8-4bb1-a4bf-d7ad8bd5bd32.png)


The accompanying illustration shows the overall output of avionics. The safety switch is turned on in the virtual terminal, then it is turned off since I have switched SW1, and then a countdown from 0 to 10 seconds begins once the ignition button is hit. Then, as previously said, the ignition system operates. Then The time is displayed in the first column, and the thrust value measured from the load cell is displayed in the second column. With these two, the graph can be plotted, and the nature of our motor can be understood.
 
Procedure to build Design stand for Static Test Pad:
![image](https://user-images.githubusercontent.com/11870995/191513067-85f2d946-cccd-4c34-954e-f55a76a756cc.png)

 
•	Choose best from individual contributions
•	Hexagonal structure
•	Clamp favored over Screws
•	U-shaped arm with rubber coating for insulation
	Protects user when adjusting clamp
	Fastened onto hexagonal frame using nuts & bolts
•	Platform to hold rectangular load cell
CLAMPS:












	Largest shear force
	Optimized Factor of Safety and Weight by 
•	Incorporating trusses
•	Switching from ABS Plastic to SS

Hexagon Support:
>Highest Factor of Safety, and Lowest amount of stress









Static Stresses acting due to the clamp        	 Thermally induced stresses



Observation:


>Using Arduino has some disadvantages. To begin with, it is clear that the only way to obtain data is to transfer it to an SD card. The WIFI module might be utilised for live streaming and the SD card could be used as a backup. However, the price is low, and the number of pins is limited.
>Adding a safety switch increased the safety of the user.
>Easy to assemble and disassemble, as we use nuts and bolts for entire design.
>Fit any type of motor as Clamp favored over Screws
>LED and LCD is used for safety and indication of the avionics process.
> As the thrust value is noticed, the time in seconds is also recorded side by side, making graph plotting much easier, simpler, and more precise.
> Hexagon Support has the highest safety factor and the lowest stress level.

