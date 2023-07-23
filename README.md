# PIR-Sensor

# Motion-Activated LED Control Arduino Sketch

This repository contains an Arduino sketch that allows you to control an LED based on the output of a motion sensor. The sketch turns on the LED when motion is detected and turns it off when the motion stops. Additionally, it sends messages to the Serial Monitor to indicate the motion status.

## Hardware Requirements

To use this Arduino sketch, you will need the following components:

1. Arduino board (e.g., Arduino Uno)
2. Passive infrared (PIR) motion sensor
3. LED
4. Resistor (220 ohms) for the LED (if needed)
5. Jumper wires to connect the components to the Arduino

## Circuit Connection

Connect the components to the Arduino board as follows:

- *PIR Sensor Output* to *Digital Pin 2 (Arduino)* (Use the OUTPUT pin of the PIR sensor)
- *LED Anode (+)* to *Digital Pin 13 (Arduino)*
- *LED Cathode (-)* to *GND (Arduino)* (through a 220-ohm resistor, if needed)

## How the Sketch Works

The Arduino sketch utilizes a passive infrared (PIR) motion sensor to detect motion. When motion is detected, the LED connected to Pin 13 on the Arduino board will turn on. When the motion stops, the LED will turn off.

Here's a brief overview of how the sketch works:

1. The PIR sensor output is connected to Digital Pin 2 on the Arduino, and the LED is connected to Digital Pin 13.
2. In the `setup()` function, the serial communication is initialized at a baud rate of 9600, and the pin modes for the LED (output) and the PIR sensor (input) are set.
3. In the `loop()` function, the sketch reads the status of the PIR sensor using `digitalRead()` to check for motion.
4. If the PIR sensor's output is HIGH (motion detected), the LED is turned on for 100 milliseconds to indicate motion.
5. Additionally, if the previous state was LOW (no motion detected), the sketch sends a "Motion detected!" message to the Serial Monitor.
6. If the PIR sensor's output is LOW (motion stopped), the LED is turned off for 200 milliseconds to indicate the end of motion.
7. Additionally, if the previous state was HIGH (motion was detected but now stopped), the sketch sends a "Motion stopped!" message to the Serial Monitor.
8. The loop continuously repeats these steps to monitor motion and control the LED accordingly.

## How to Use

To use this Arduino sketch:

1. Connect the PIR motion sensor and LED to the Arduino board following the circuit connection mentioned above.
2. Open the Arduino IDE and upload the sketch to your Arduino board.
3. Open the Serial Monitor in the Arduino IDE (set the baud rate to 9600) to view the motion detection messages.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- The sketch uses the Passive Infrared (PIR) Motion Sensor Library example provided in the Arduino IDE.
- Passive Infrared (PIR) Motion Sensor Library: [https://github.com/adafruit/Adafruit_PIR](https://github.com/adafruit/Adafruit_PIR)

---

