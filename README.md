# 📅 EventBoard – RTC-Driven Message Display System

An Embedded C project developed using the **LPC2148 ARM7 Microcontroller** that automatically displays scheduled messages on a **16x2 LCD** based on real-time clock (RTC). The system also monitors room temperature using an **LM35 temperature sensor** and provides a password-protected **Admin Mode** for editing time and event settings. :contentReference[oaicite:0]{index=0}

---

## 📌 Project Overview

EventBoard is a real-time embedded system designed to automate message display for classrooms, offices, laboratories, and institutions.

The system continuously reads the current time from the **LPC2148 RTC**. Whenever the current time matches a predefined event, the corresponding message scrolls on the LCD.

If there is no scheduled event, the LCD displays:

- Current Date
- Current Time
- Room Temperature

The room temperature is measured using the **LM35 Temperature Sensor**, whose output voltage is directly proportional to the temperature in Celsius. :contentReference[oaicite:1]{index=1}

---

# ✨ Features

- 🕒 Real-Time Clock (RTC) based scheduling
- 📺 16x2 LCD scrolling message display
- 🌡️ LM35 temperature monitoring
- 🔢 4x4 Matrix Keypad interface
- 🔒 Password-protected Admin Mode
- 🟢 Green LED indicates active scheduled event
- 🔴 Red LED indicates normal display mode
- ⚙️ Edit RTC Date & Time
- 📝 Enable or Disable scheduled messages
- 💾 Stores up to 10 predefined event messages

These behaviors are described in the project workflow and admin-mode design. :contentReference[oaicite:2]{index=2} :contentReference[oaicite:3]{index=3}

---

# 🛠 Hardware Used

| Component | Description |
|-----------|-------------|
| LPC2148 | ARM7 Microcontroller |
| 16x2 LCD | Displays time, temperature and messages |
| 4x4 Matrix Keypad | User input |
| RTC | Real-Time Clock (Built into LPC2148) |
| LM35 | Temperature Sensor |
| Green LED | Event Active Indicator |
| Red LED | Idle Indicator |
| Push Button Switch | Enter Admin Mode |
| Power Supply | 5V Regulated |

---

# 💻 Software Used

- Embedded C
- Keil uVision
- Flash Magic
- Proteus (Simulation)

---

# 📂 Project Structure

```
EventBoard/
│
├── main.c
├── lcd.c
├── lcd.h
├── rtc.c
├── rtc.h
├── adc.c
├── adc.h
├── keypad.c
├── keypad.h
├── delay.c
├── delay.h
├── event.c
├── event.h
├── README.md
```

---

# 🔄 Working Principle

### Normal Mode

The system continuously performs the following operations:

- Read RTC time
- Read LM35 temperature
- Display current date and time
- Display room temperature
- Compare current time with stored events

If no event is scheduled:

```
12:30:25 MON
26/07/2026 28°C
```

---

### Event Mode

When the RTC matches an event time:

```
*************************
Welcome to ARM Workshop
*************************
```

The LCD scrolls the complete message while the Green LED turns ON.

---

### Admin Mode

Press and hold the Admin Switch.

Enter Password using the keypad.

Available options:

```
1. RTC EDIT

2. EVENT EDIT

3. EXIT
```

RTC Edit allows changing:

- Hour
- Minute
- Second
- Date
- Month
- Year
- Day

Event Edit allows:

- Select Event
- Activate Event
- Deactivate Event

---

# 📈 System Flow

```
Start
   │
Initialize LCD
Initialize RTC
Initialize ADC
Initialize Keypad
   │
Read RTC
Read Temperature
   │
Is Event Time?
   │
 ┌──────────────┐
 │              │
Yes            No
 │              │
Display       Show
Message       Clock
 │             &
Green LED   Temperature
 │              │
Check Admin Switch
 │
Repeat
```

This flow follows the implementation plan defined for the project. :contentReference[oaicite:4]{index=4}

---

# 📸 Block Diagram

```
4x4 Keypad --------\
                    \
Switch -------------> LPC2148 ---------> LCD
                     |
LM35 -----> ADC -----|
                     |
                     +-------> Green LED
                     |
                     +-------> Red LED
                     |
                    RTC
```

---

# 🎯 Applications

- Digital Notice Boards
- College Laboratories
- Educational Institutions
- Office Reminder Systems
- Conference Rooms
- Industrial Shift Reminder Systems
- Smart Classrooms

---

# 🚀 Future Improvements

- EEPROM support for permanent event storage
- GSM message notification
- Wi-Fi or IoT connectivity
- Mobile application support
- Web-based event scheduling
- Multiple language support
- SD Card storage
- Buzzer notifications

---

# 👨‍💻 Author

**Sohel Shaik**

Embedded Systems Enthusiast

- ARM7 LPC2148
- Embedded C
- Device Driver Development

---
