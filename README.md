# Arduino-LED-Botton
Arduino project for controlling an LED with a push-button.



1. Project Overview

This project consists of turning an LED on and off using a push button connected to an Arduino board.

Each time the button is pressed:

If the LED is off, it turns on.

If the LED is on, it turns off.

Difficulty: Beginner
Board used: Arduino Mega 2560.



2. Required Components

- 1 Arduino Mega 2560

- 1 LED

- 1 push button

- 1 220 Ω resistor

- 1 breadboard

- Jumper wires

- 1 USB cable to connect the Arduino to the computer



3. Building the Circuit

Component Connections

Component                            Arduino Connection

LED (long leg)                       Digital pin 8, with a 220 Ω resistor

LED (short leg)                      GND

Push button                          Digital pin 2

Other side of the button             GND

Important Information

- The long leg of the LED is the positive side (anode).

- The short leg is the negative side (cathode).

- The 220 Ω resistor protects the LED by limiting the electrical current.

- The button must connect pin 2 to GND when pressed.

We will use INPUT_PULLUP in the program. This function activates an internal resistor in the Arduino board. Therefore, there is no need to add an external resistor for the button.

Circuit Diagram




4. Arduino Programming

The complete Arduino program is available in the following file:

led_button.ino

You can download this file and open it directly with Arduino IDE.




5. Program Explanation


A. Pin Declaration

const int ledPin = 8;
const int buttonPin = 2;

These two lines tell the Arduino where the components are connected.

- ledPin = 8: the LED is connected to pin 8.

- buttonPin = 2: the button is connected to pin 2.


B. Component Configuration

pinMode(ledPin, OUTPUT);
pinMode(buttonPin, INPUT_PULLUP);

These instructions define the role of each pin.

- OUTPUT means that the pin sends an electrical signal.

- INPUT_PULLUP means that the pin receives information from the button using an internal resistor.

With INPUT_PULLUP, the button has two states:

- HIGH: the button is not pressed.

- LOW: the button is pressed.



C. Reading the Button

int reading = digitalRead(buttonPin);

This instruction allows the Arduino to read the button's state.

The Arduino checks whether the button is pressed or released.



D. Debouncing

const unsigned long debounceDelay = 50;

When a physical button is pressed, the electrical contact can produce several very fast signal changes.

This phenomenon is called button bouncing.

The program waits 50 milliseconds to check that the change is stable. This prevents the LED from changing its state multiple times after a single button press.



E. Changing the LED State

ledState = !ledState;

This is the main instruction of the project.

It reverses the LED state:

- If the LED is off, it turns on.

- If the LED is on, it turns off.

The following instruction applies this change:

digitalWrite(ledPin, ledState);

It sends the signal needed to turn the LED on or off.




6. Uploading the Program

To use the program:

1- Connect the Arduino Mega 2560 to your computer using the USB cable.

2- Open Arduino IDE.

3- Download or copy the led_button.ino file.

4- In the Tools menu, select the Arduino Mega 2560 board.

5- Select the COM port corresponding to your Arduino board.

6- Click the Upload button.

7- Wait until the upload is complete.

Once the upload is finished, the circuit is ready to use.




7. Expected Result

After the Arduino starts:

1/ The LED stays off.

2/ Press the button once: the LED turns on.

3/ Press the button a second time: the LED turns off.

4/ Repeat this operation as many times as you want.

The program runs continuously as long as the Arduino is powered.

Arduino Assembly




8. Common Problems

The LED does not turn on:

- Check the LED's orientation.

- Check the resistor.

- Make sure the LED is connected to pin 8.

The button does not work:

- Make sure the button is connected to pin 2 and GND.

- Check its orientation on the breadboard.

- Make sure the program uses INPUT_PULLUP.

The program cannot be uploaded:

- Check the USB cable.

- Make sure the correct board is selected.

- Make sure the correct COM port is selected.




9. Conclusion

This project introduces the basic concepts of using an Arduino board.

It shows how to read information from a push button and use that information to control an electronic component.

The concepts learned in this project can be reused in more advanced projects, such as controlling multiple LEDs, motors, or different sensors.




Author: REDSABEuR
Project: Arduino LED Push Button
Board: Arduino Mega 2560
