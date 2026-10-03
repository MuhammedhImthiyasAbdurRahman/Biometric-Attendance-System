# Biometric Attendance System

**Arduino · C++ · Fingerprint sensor · 16×2 LCD · 4×4 keypad**

An academic hardware prototype exploring fingerprint identification and an LCD-based attendance workflow.

## At a glance

| Area | Implementation |
| --- | --- |
| Identification | Fingerprint capture and matching with the Adafruit Fingerprint library |
| Interaction | Keypad commands and on-screen LCD prompts |
| User templates | Enrolment, deletion and replacement workflows |
| Attendance feedback | Displays a recognised user ID and attendance confirmation |

## Hardware and libraries

- Arduino-compatible board; verify pin numbering for your chosen board.
- Compatible serial fingerprint sensor, 16×2 parallel LCD, 4×4 keypad and connecting wires.
- Arduino IDE with **Adafruit Fingerprint Sensor Library**, **Keypad**, **LiquidCrystal** and **SoftwareSerial**.

### Pin assignments in the sketch

| Component | Sketch pins |
| --- | --- |
| LCD RS / EN / D4 / D5 / D6 / D7 | 14 / 15 / 16 / 17 / 18 / 19 |
| Fingerprint SoftwareSerial RX / TX | 2 / 3 |
| Keypad rows | 12 / 11 / 10 / 9 |
| Keypad columns | 8 / 7 / 6 / 5 |

Check sensor voltage requirements and connect sensor TX to the board RX, and sensor RX to board TX.

## Explore the prototype

1. Download or clone the repository.
2. Open `Biometric Attendance System.ino` in Arduino IDE. Let the IDE create a matching sketch folder if requested.
3. Install the libraries and select the correct board and port.
4. Review the wiring and the implementation notes below before compiling and uploading.
5. The sketch configures the serial monitor at **9600 baud** and fingerprint communication at **57600 baud**.

### Keypad commands

| Key | Intended action |
| --- | --- |
| E | Enrol a fingerprint template |
| D | Delete a template by ID |
| O | Replace a user template |

IDs are entered as three digits, for example `001`.

## Current implementation notes

This repository preserves the original academic sketch. Hardware operation has not been revalidated in this documentation update.

- The `getPassword()` routine needs correction: the entered values are not compared with the configured code, and the counter is incremented unconditionally. The password prompts currently do not provide effective access control.
- Review the local array declaration inside that routine before compiling.
- Attendance confirmation is displayed on the LCD; persistent logs, timestamps and a database are not included.

## Next development steps

- Correct and test password validation and administrative actions.
- Add timestamped attendance storage and export.
- Add a circuit diagram, prototype photographs and hardware test results.

## Author

**Abdur Rahman Imthiyas** · [Portfolio](https://abdurrahmanimthiyas.wordpress.com/) · [LinkedIn](https://www.linkedin.com/in/muhammedh-imthiyas-abdur-rahman-606a4a245)
