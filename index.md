# Spinng LED Display

### Project Overview
This project seeks to spin a row of 8 LED lights and flash them in a pattern to display a readable message to the user, as displayed in the video before.

Project concept and abstract:
> The Spinning light display uses a motor to spin the board at high speed while pulsing the lights to make patterns in the air as it zooms around. The LED's on the PCB light up in a specific pattern. As the motor spins the board around, one is able to see the pattern. The board is designed so it can be mounted on other spinning things, like bicycle wheels. Also, Arrows, animation, and text characters are all possible patterns.

Adapted from [Spinning LED Display](https://www.instructables.com/Spinning-LED-Display/)

<iframe width="635" height="360" src="https://www.youtube.com/embed/Sob4olFqeOM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Physical Assembly
We chose a design of a system that had an electric motor spinning the PCB. Our design called for a beam interrupter to act as position sensor so that the Microcontroller would be able to track the revolutions of the motor and would be able to flash the lights appropriately, but unfortunately due to soldering issues with the motor, we could never actually get the motor to spin. 
![image](https://user-images.githubusercontent.com/39937655/146619437-accb797b-7b3c-4058-ba77-35a9d456f658.png)

### System Architecture
As said earlier, because the motor could no longer spin, we had to adapt our code to have a periodic interrupt in order to let the microcontroller know that it is time to flash the lights. Our system archetecture is as follows.
![image](https://user-images.githubusercontent.com/39937655/146622184-883a387b-da37-4b66-a7bc-dc8df06357aa.png)

### Design and Implementation
Several Graphics showing how we implemented our design.

![image](https://user-images.githubusercontent.com/39937655/146622295-12ceabd5-6fa7-4c6a-bb85-37d3d096883f.png)

![image](https://user-images.githubusercontent.com/39937655/146622342-82ed54ae-1e30-4268-9dd9-81aef6721d40.png)

### Bitmask Alphabet
[This](font.h) is a link to our alphabet. In that file, is an array of bitmasks that represent various letters and symbols to be displayed by our Spinning LED array. We assign every character 6 different flashes of the array, so each character requires 6 different bit patterns. The image below shows how each bit pattern is represented with a hexademical number, showing how the hexademical number for the first pattern in the letter 'A' is found.

![image](https://user-images.githubusercontent.com/39937655/146619547-390835c1-8dae-44d9-abd4-b2cbf27592a9.png)

#### Other Used Coding Files
[startup file](startup_rvmdk.S)
[main body](Spinning_Led.c)

### Results
As mentioned, due to our hardware issues and lack of time, we were not able to spin the motor. This device can only display message if either the viewer or their frame of reference in regards to the PCB board is moving (i.e. either the viewer or the board must be moving in the direction of the message to view the message). Below is an image of the board simply flashing, we will work on getting a video properly showing the phonenomenon of a message being displayed by having the camera move in relation to the board.

![image](https://user-images.githubusercontent.com/39937655/146622619-8db450b5-a5d0-4420-93da-f7a9379ba91d.png)
