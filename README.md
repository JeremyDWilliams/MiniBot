# MiniBot
A small open source mini robot project with reliability, ease of use, repair and assembly as well as cost being a priority.
<br>
 <br>
 <br>
<p align="center">
<a href="https://drive.google.com/uc?export=view&id=1bo4GhHph75oDg3j69xkk8u2KKWCbzn7q"><img src="https://drive.google.com/uc?export=view&id=1bo4GhHph75oDg3j69xkk8u2KKWCbzn7q" style="width: 400px; max-width: 70%; height: auto" title="Click for the larger version." /></a>

The purpose of the MiniBot is to afforably educate while having the ablity to do simple light tasks. A key feature of it is tha it has a physical articulated representation of the MiniBot for easy intuitive tele-op control. This is accomplished using inexpensive potentiometers and a miniture of the MiniBot. Controls are provided to record 'Skits' of movements which can be saved and replayed later with no coding. A future project (want to help?) will be able to manipulate these Skits, create new ones, edit them and copy/paste them into decision trees or onto timelines. The MiniBot itself is fully self-contained and does not require additonal computers to use.

<br>
 <br>
 <br>


<p align="center">
<a href="https://drive.google.com/uc?export=view&id=1ikl5Oti2HGW07uHvnFWjVrtxpKifyfDb"><img src="https://drive.google.com/uc?export=view&id=1ikl5Oti2HGW07uHvnFWjVrtxpKifyfDb" style="width: 200px; max-width: 50%; height: auto" title="Click for the larger version." /> </a>
<br>
 <br>
 <br>

  
## Arduino Servo Control with Recording and Playback

This Arduino project allows you to control multiple servos using a tiny MiniBot tele-op control using potentiometers, record servo movements for playback, and implement stall and burnout protection for the servos using software-based PID control.

## Functionality

### Potentiometer Control
- The project uses 5 potentiometers to manually control the positions of 5 servos.
- Adjusting the potentiometers changes the angle of the corresponding servo.

### Servo motors
- The project uses 5 servos to  control the positions of the MiniBot's 5 degrees of freedom.
- The design features short moment arms allowing relatively small and inexpensive servos.

### Design
- All strutural parts are 3D printed. STL's are provided. Metric screws are used for assembly. Wires are routed internally to provide a clean esthetic. It is fully servicable and can be dissasembled for repair, upgrade or maintenance. 
- It is recommended to use silicone wires as they bind less in use. It is important to deburr all 3D printed parts to allow for wire movment.


### Recording and Playback
- Pressing the record button starts recording servo movements. The movements, called a 'Skit', are saved as a file to an SD card.
- Pressing the play button starts playing back the last recorded Skit.
- Single pressing the pause/end button pauses the recording/playback. Press again and it resumes playing or recording. You can also click the record or start button to continue recording/playing.
- Double tap the pause/end button to stop recording/playback

- There are three LEDs to show what mode it is in:

| LED | SATUS | MODE |
|:-----:|:---:|:---------------|
|  Blue |On|      Power ON         |
|  Blue |Off|      Power OFF         |
|     Red| On|       Recording a Skit       |
|     Red| Off|       Recording Mode Off       |
|     Red| Flashing|       Recording paused       |
|     Green | On|       Playing a Skit       |
|     Green | Off|       Playing Mode Off       |
|     Green | Flashing|       Playing paused       |


### Stall and Burnout Protection
- The project implements software-based PID control to prevent servo stalling or burning out.
- It continuously monitors estimated servo positions and adjusts power to prevent damage.
- This is accomplished by testing stall and load characteristics of the servos spec'ed in this project. Times and capabilites are noted and used to modify servo outputs to maintain safe levels. This is open looped using 'best guess' from testing as far as the PID control goes, with the associated downsides with that system. A closed loop system with feedback would be superior, however that would increase costs beyond the scope of requirements of this project. Fortunately servoes have their own feedback for positional control which is relied on to not lose desired positions.

## Wiring Instructions
- This chart is a placeholder and should not be used.
- 
| PIN | KIND | ASSIGMENT |
|:-----:|:---:|:---------------|
|  1 |Digital Out|      Servo 1, ARM        |
|  2 |Digital Out|      Servo 2, WRIST        |
|     3| Analog IN|       Potentiometer ARM      |
|     4| Analog IN|       Potentiometer WRIST        |
|     5| Analog IN|       Potentiometer BASE       |
|     6 | Digital OUT|       Servo 3, WRIST       |
|     7 | Digital OUT |       Servo 4, WRIST       |
|     8 | Digital OUT |      Servo 5, WRIST       |
|     6 | Digital IN|       Switch, PLAY       |
|     7 | Digital IN |       Switch, RECORD       |
|     8 | Digital IN |      Switch, PAUSE       |

### Components Needed
- 5 Servos
- 5 Potentiometers
- 3 Push Buttons
- 3 LEDs (Red, Green and Blue)
- Arduino Board
- SD Card Module (for recording movements)

### Wiring Diagram

[NOT the correct Wiring Diagram, This is a place holder image]
<picture>
 <img alt="Arduino and 5 servos" src="https://i.stack.imgur.com/dn2h8.png">
</picture>


- Connect each servo to a PWM pin on the Arduino (servoPins array).
- Connect each potentiometer to an analog pin on the Arduino (potPins array).
- Connect the play, record, and pause/end buttons to digital pins on the Arduino (playButtonPin, recordButtonPin, pauseEndButtonPin).
- Connect the red and green LEDs to digital pins on the Arduino (redLedPin, greenLedPin).

## Usage

1. Connect the Arduino and upload the code (`servo_control.ino`).
2. Wire the components according to the wiring diagram.
3. Power on the system and adjust potentiometers to control servo positions.
4. Press the record button to start recording movements.
5. Press the play button to play back recorded movements.
6. Press the pause/end button to pause or stop recording/playback.

## Contributors

- [JeremyDWilliams](https://github.com/jeremydwilliams)

## Project Status

This is an open source project consiting of software and hgardware. Contributions are welcome. It is supported by [Williams Robotics](https://www.williamsrobotics.io) Parts and components are available for purchase as are complete or partial kits and complete turnkey builds. All parts for the base MiniBot can also be sourced directly from other parts vendors. Parts sold by Williams Robotics in purchased builds/kits may differ from those on this github and feature improvements in performance or usability but are generally interchangable.

For prebuilt units or for parts, please 
## License

This project is licensed under the GNU AGPLv3 License - see the [LICENSE.md](https://github.com/JeremyDWilliams/MiniBot/blob/main/LICENSE) file for details.
