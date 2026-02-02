**Enhanced Driver’s Education Car Alarm System** 

**Team Members**

* Vivaan Gupta  
* Jaxon Sosa

**Project Overview**

Our project implements the car ignition and headlight control system of a Driver’s Education Car Alarm System using an ESP32-S3 microcontroller. Our main goal was to make the vehicle safer and more realistic by controlling when the engine can start and how the headlights behave. The ignition system checks basic safety conditions before allowing the engine to turn on. The engine can only be started if both the driver and passenger are sitting in their seats and both seatbelts are fastened. If any of these conditions are not met, the system blocks the ignition, sounds an alarm, and clearly explains on the display what is missing, such as an unfastened seatbelt or an empty seat. Once the engine is started, it continues running even if a seatbelt is removed or someone leaves the vehicle, and the engine can be turned off at any time by pressing the ignition button again.

Our project also includes an automatic headlight control system that mimics how headlights work in modern vehicles. The driver can manually turn the headlights ON or OFF, or select an AUTO mode where the system uses a light sensor to decide when the headlights should be on. In AUTO mode, the headlights turn on when it gets dark and turn off when it becomes bright, with short delays to prevent flickering during quick light changes. The headlights always turn off when the engine is off. Additionally, a manual high-beam and low-beam switch is implemented using extra LEDs, where low-beam is shown with one LED per headlight and high-beam is shown with two LEDs per headlight. Overall, this system demonstrates realistic vehicle behavior while focusing on safety, reliability, and clear feedback for both the driver and passenger of the driver’s ed vehicle.

**Test Cases for our Ignition Subsystem**

| Test Case | Driver Weight | Driver Seatbelt | Passenger Weight | Passenger Seatbelt | Green LED | Blue LED | Buzzer | Output |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 1 | Not pressed | Not pressed | Not pressed | Not pressed | OFF | OFF | ON | “Welcome to the enhanced alarm system model 218-W25” “Ignition Prohibited” “driver seat not occupied” “driver seatbelt not on” “passenger seat not occupied” “passenger seatbelt not on” “Please ensure that both seatbelts are fastened and both seats are occupied before starting the engine” |
| 2 | Pressed | Not pressed | Not pressed | Not pressed | OFF | OFF | ON | “Welcome to the enhanced alarm system model 218-W25” “Ignition Prohibited” “driver seatbelt not on” “passenger seat not occupied” “passenger seatbelt not on” “Please ensure that both seatbelts are fastened and both seats are occupied before starting the engine” |
| 3 | Pressed | Not pressed | Pressed | Not pressed | OFF | OFF | ON | “Welcome to the enhanced alarm system model 218-W25” “Ignition Prohibited” “driver seatbelt not on” “passenger seatbelt not on” “Please ensure that both seatbelts are fastened and both seats are occupied before starting the engine” |
| 4 | Pressed | Pressed | Not pressed | Not pressed | OFF | OFF | ON | “Welcome to the enhanced alarm system model 218-W25” “Ignition Prohibited” “passenger seat not occupied” “passenger seatbelt not on” “Please ensure that both seatbelts are fastened and both seats are occupied before starting the engine” |
| 7 | Not pressed | Not pressed | Pressed | Pressed | OFF | OFF | ON | “Ignition Prohibited” “driver seat not occupied” “driver seatbelt not on” “Please ensure that both seatbelts are fastened and both seats are occupied before starting the engine” |
| 8 | Pressed | Pressed | Pressed | Pressed | ON | ON | OFF | “Welcome to the enhanced alarm system model 218-W25” “Engine Started” |

**Table1: Ignition Subsystem Test Cases**

The ignition subsystem functions correctly for all defined test cases. When the required conditions for ignition are not met, the system inhibits engine start but allows repeated ignition attempts until all conditions are satisfied. Once the engine is started, pressing the ignition button again successfully shuts the engine off, as required.

**Test Cases for our Headlight Subsystem**

| Test Case | Engine Status | Potentiometer Status | Ambient Light  | Output |
| :---- | :---- | :---- | :---- | :---- |
| 1 | OFF | ON | HIGH | Headlights are turned OFF |
| 2 | ON | OFF | LOW | Headlights are turned OFF |
| 3 | ON | OFF | HIGH | Headlights are turned OFF |
| 4 | ON | ON | LOW | Headlights are turned ON |
| 5 | ON | ON | HIGH | Headlights are turned ON |
| 6 | ON | AUTO | LOW | Headlights are turned ON |
| 7 | ON | AUTO | HIGH | Headlights are turned OFF |

**Table 2: Headlight Subsystem Test Cases**
