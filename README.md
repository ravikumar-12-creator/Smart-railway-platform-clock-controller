# Smart-railway-platform-clock-controller
Smart Railway Platform Controller using LPC2148 and Embedded C. Features train scheduling, real-time clock, platform management, train status monitoring, LCD display, keypad input, and interrupt-based control for efficient railway platform automation.
# 🚆 Smart Railway Platform Clock Controller

## 📌 Project Overview

The **Smart Railway Platform Clock Controller** is an embedded-system project developed using the **LPC2148 ARM7 microcontroller**. The system is designed to provide railway platform information through a **16×2 LCD display**, while maintaining accurate time using the microcontroller's RTC.

It combines real-time clock management, train schedule monitoring, passenger information display, keypad-based data entry, and visual/audio indications into a single embedded application.

The main purpose of the project is to demonstrate how an embedded controller can be used to automate basic railway platform information and reduce dependence on manual updates.

---

## 🎯 Objectives

* Display the current time and date on the platform display.
* Maintain railway train schedule information.
* Show train arrival and departure details.
* Identify the current status of scheduled trains.
* Provide LED and buzzer indications for important train events.
* Allow authorized users to modify train and time information.
* Demonstrate practical use of ARM7 and Embedded C programming.

---

## ⚙️ System Working

The LPC2148 acts as the central controller of the system.

The internal RTC maintains the current date and time. The controller continuously compares the RTC value with the stored train schedule. Based on the comparison, the system determines the corresponding train status.

The LCD is used to present the information to passengers. Different display screens can show the current clock, train details, platform information, and train status.

A keypad provides an interface for entering or modifying schedule information. LEDs and a buzzer provide additional indications whenever a particular train event needs attention.

### Basic operation:

1. The system initializes the LPC2148 peripherals.
2. The RTC is configured with the current date and time.
3. Train schedule information is loaded into the system.
4. The current time is continuously monitored.
5. Train timings are compared with the RTC.
6. Appropriate train information is displayed on the LCD.
7. LEDs and buzzer indicate selected train conditions.
8. Authorized users can modify schedule or clock settings through the keypad.

---

## ✨ Main Features

* ⏰ Real-time clock and calendar display
* 🚉 Train arrival and departure monitoring
* 📺 16×2 LCD-based passenger information display
* 🔢 4×4 keypad interface
* 💡 LED-based train status indication
* 🔔 Buzzer notification
* 🔐 Password-protected administrative access
* 📝 Editable train schedule information
* 🕒 RTC time and date modification
* 💻 Embedded C implementation
* 🔧 Modular peripheral drivers

---

## 🧰 Hardware Components

| Component        | Purpose                             |
| ---------------- | ----------------------------------- |
| LPC2148          | Main ARM7 microcontroller           |
| 16×2 LCD         | Displays time and train information |
| RTC              | Maintains date and time             |
| 4×4 Keypad       | User input and menu navigation      |
| LEDs             | Visual status indication            |
| Buzzer           | Audio notification                  |
| Power Supply     | Provides required operating voltage |
| Connecting Wires | Hardware interconnection            |

---

## 💻 Software & Technologies

* **Programming Language:** Embedded C
* **Microcontroller:** NXP LPC2148
* **Processor:** ARM7TDMI-S
* **IDE/Compiler:** Keil uVision
* **Programming Tool:** Flash Magic
* **Communication:** UART
* **Display:** 16×2 LCD
* **Input:** 4×4 Matrix Keypad

---

## 🧩 Software Modules

The project is divided into separate modules to make the program easier to understand, debug, and maintain.

### 1. Application Module

Controls the main program flow and coordinates different peripherals.

### 2. RTC Module

Handles initialization, reading, and modification of the current time and date.

### 3. LCD Module

Provides functions for displaying characters, strings, numbers, and commands on the LCD.

### 4. Keypad Module

Scans the matrix keypad and obtains user input for menus and data entry.

### 5. Train Schedule Module

Stores train-related information such as arrival time, departure time, platform number, and status.

### 6. Scheduler Module

Compares the current RTC time with the stored schedule and determines which train information should be displayed.

### 7. LED and Buzzer Module

Controls visual and audio indications according to the current railway status.

### 8. Menu Module

Provides the administrative interface for modifying system settings and train information.

---

## 🔐 Admin Mode

An administrative section is included to allow authorized modification of system information.

After entering the correct password, the administrator can access options such as:

* Updating train arrival time
* Updating departure time
* Changing platform information
* Modifying delay information
* Correcting the RTC date and time
* Updating the administrator password

This avoids the need to modify the source code whenever schedule information needs to be changed.

---

## 🔄 System Flow

```text
             ┌───────────────────┐
             │   Power ON / Reset│
             └─────────┬─────────┘
                       ↓
             ┌───────────────────┐
             │ Initialize LPC2148│
             └─────────┬─────────┘
                       ↓
             ┌───────────────────┐
             │ Initialize RTC    │
             │ LCD / Keypad / I/O│
             └─────────┬─────────┘
                       ↓
             ┌───────────────────┐
             │ Read Current Time  │
             └─────────┬─────────┘
                       ↓
             ┌───────────────────┐
             │ Check Train Timing │
             └─────────┬─────────┘
                       ↓
             ┌───────────────────┐
             │ Update LCD Display │
             └─────────┬─────────┘
                       ↓
             ┌───────────────────┐
             │ LED / Buzzer Alert │
             └─────────┬─────────┘
                       ↓
             ┌───────────────────┐
             │ Check Admin Input  │
             └─────────┬─────────┘
                       ↓
                    Repeat
```

---

## 📂 Project Structure

```text
Smart-Railway-Platform-Clock-Controller/
│
├── application.c
├── rtc.c
├── rtc.h
├── lcd.c
├── lcd.h
├── kpm.c
├── kpm.h
├── scheduler.c
├── scheduler.h
├── trainDB.c
├── trainDB.h
├── menu.c
├── menu.h
├── led_buzz.c
├── led_buzz.h
├── delay.c
├── delay.h
├── eint1_sw.c
├── eint1_sw.h
├── all_peripheral_defines.h
└── types.h
```

---

## 🧪 Testing

The system can be tested by configuring different train timings and observing the LCD output.

The following conditions can be verified:

* Current time and date display
* Train schedule display
* Arrival-time detection
* Departure-time detection
* Delay indication
* LCD scrolling/display changes
* Keypad input
* Password verification
* Admin menu operation
* RTC modification
* LED and buzzer operation

---

## 🌟 Applications

The project can serve as a prototype for:

* Railway platform information systems
* Embedded passenger information displays
* Small railway station automation
* Train schedule monitoring
* Educational ARM7 embedded-system applications
* Real-time event monitoring systems

---

## 🚀 Future Improvements

The prototype can be extended with additional features such as:

* 📡 Wireless schedule updates
* 🌐 IoT-based remote monitoring
* 📱 Mobile application integration
* 🖥️ Larger graphical display
* 🔊 Voice-based train announcements
* ☁️ Cloud-based schedule management
* 🗃️ Larger train databases
* 🔄 Automatic synchronization with centralized railway data
* 📊 Historical train-status logging

---

## 📚 Learning Outcomes

Through this project, I gained practical exposure to:

* ARM7 microcontroller programming
* Embedded C development
* RTC programming
* LCD interfacing
* Matrix keypad interfacing
* Interrupt handling
* Modular programming
* Peripheral driver development
* Real-time event monitoring
* Embedded-system debugging

---

## 👨‍💻 Project Highlights

**Project:** Smart Railway Platform Clock Controller
**Microcontroller:** LPC2148
**Architecture:** ARM7TDMI-S
**Language:** Embedded C
**Display:** 16×2 LCD
**Input:** 4×4 Keypad
**Development Environment:** Keil uVision

---

## 📄 Conclusion

The Smart Railway Platform Clock Controller demonstrates how an ARM7-based embedded system can combine real-time clock management, train scheduling, display control, and user interaction into one practical application.

The project provides a foundation for developing more advanced railway information and automation systems using embedded technologies.
