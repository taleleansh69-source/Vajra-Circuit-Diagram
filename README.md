# 🚁💜⚡ VAJRA 1 // NEURAL FLIGHT SYSTEM ⚡💜🚁

<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0500FF,15:00E5FF,30:7F00FF,45:FF00E5,60:0500FF,75:00FFFF,90:7F00FF,100:FF00E5&height=280&section=header&text=VAJRA%201&fontSize=90&fontColor=FFFFFF&animation=fadeIn&fontAlignY=35&desc=NEURAL%20FLIGHT%20SYSTEM%20%7C%20CYBERPUNK%20ROBOTICS&descAlignY=58&descSize=17"/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=800&size=23&duration=1800&pause=500&color=00E5FF&center=true&vCenter=true&width=850&lines=%5B+SYSTEM+BOOTING...+%5D;%5B+NEURAL+INTERFACE+ONLINE+%5D;%5B+FLIGHT+CONTROL+INITIALIZING+%5D;%5B+BLE+COMMUNICATION+READY+%5D;%5B+WELCOME+TO+VAJRA+1+%5D" alt="Animated VAJRA 1 system status"/>

### 🔮🌌 WELCOME TO THE NEON ROBOTICS LAB 🌌🔮

💠 🤖 🧠 💻 ⚡ 🔋 🚁 🛸 📡 🎮 🕹️ 🧭 🌀 🔧 🛠️ 🔩 🔌 🪫 🌐 🚀 ✨ 💎

<img src="https://img.shields.io/badge/PROJECT-VAJRA%201-7F00FF?style=for-the-badge&logo=github&logoColor=white"/>
<img src="https://img.shields.io/badge/CORE-ESP32--C3-00E5FF?style=for-the-badge&logo=espressif&logoColor=black"/>
<img src="https://img.shields.io/badge/SENSOR-MPU6050-FF00E5?style=for-the-badge"/>
<img src="https://img.shields.io/badge/CONTROL-BLE%20%2B%20UART-0500FF?style=for-the-badge"/>
<img src="https://img.shields.io/badge/MOTORS-QUAD%20BRUSHLESS-00FFFF?style=for-the-badge"/>

💜━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━💜

**📱 ANDROID 🎮 → 📡 BLE → 🧠 MAIN ESP32-C3 → 🔄 UART → 🚁 FLIGHT ESP32-C3 → ⚡ ESCs → 🛸 MOTORS**

💙 🩵 💜 🔮 🌌 ⚡ 🚀 🤖 📡 🎮 🔋 🧭 ✨ 💎

</div>

---

## 🌌💠 01 // PROJECT OVERVIEW 💠🌌

> 🧠 **MISSION:** Build a custom quadcopter platform using ESP32-C3 boards, BLE commands, an MPU6050 motion sensor, four ESCs, and four brushless motors.

| 💜 SYSTEM MODULE | ⚡ FUNCTION |
|---|---|
| 📱 Android Controller | 🎮 Sends joystick commands |
| 📡 BLE Link | 🔗 Wireless command transport |
| 🧠 Main ESP32-C3 | 📥 Receives and validates commands |
| 🔄 UART Link | 📡 Transfers commands between boards |
| 🚁 Flight ESP32-C3 | 🎛️ Generates ESC control signals |
| 🧭 MPU6050 | 📊 Measures acceleration and angular velocity |
| ⚡ 4 × ESC | 🔋 Controls brushless motor power |
| 🔄 4 × Brushless Motors | 🚀 Produce thrust |
| 🔋 3S LiPo | ⚡ Supplies the propulsion system |
| 🛡️ Safety Logic | 🛑 Handles arming and communication loss |

💜✨━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━✨💜

## 🗺️⚡ 02 // ULTRA NEON CIRCUIT ARCHITECTURE ⚡🗺️

```text
        🌌╔════════ VAJRA 1 NEURAL CORE ════════╗🌌

                       📱 ANDROID 📱
                  ┌───────────────────┐
                  │ 🎮 BLE JOYSTICK   │
                  │ 🕹️ MOVE COMMANDS  │
                  │ ⬆️⬇️⬅️➡️ AXES     │
                  └─────────┬─────────┘
                            │
                      📡 BLE WIRELESS
                            │
                            ▼
                  ┌───────────────────┐
                  │ 🧠 MAIN ESP32-C3  │
                  │ 📥 BLE RECEIVER   │
                  │ 🔍 COMMAND CHECK  │
                  └─────────┬─────────┘
                            │
                     🔄 UART SERIAL
                     TX ───────► RX
                     RX ◄─────── TX
                     GND ◄────► GND
                            │
                            ▼
                  ┌───────────────────┐
                  │ 🚁 FLIGHT ESP32-C3│
                  │ 🧭 MPU6050 INPUT  │
                  │ 🎛️ ESC OUTPUTS    │
                  │ 🛡️ FAILSAFE       │
                  └────┬────┬────┬────┘
                       │    │    │
                 ┌─────┘    │    └─────┐
                 ▼          ▼          ▼
               ⚡ ESC 1   ⚡ ESC 2   ⚡ ESC 3 / 4
                 │          │          │
                 ▼          ▼          ▼
                🔄 M1      🔄 M2      🔄 M3 / M4

        🔋 3S LiPo ──► 🔌 POWER DISTRIBUTION ──► ⚡ ESCs
        🧭 MPU6050 ──► 📊 MOTION DATA ──► 🧠 FLIGHT SOFTWARE

        🌌╚════════════════════════════════════╝🌌
```

💙🩵💜🔮⚡🚀🤖📡🎮🔋🧭✨💎🌠🛸

---

## 📱🎮 03 // BLUETOOTH COMMAND NETWORK 🎮📱

<div align="center">

📱 **PHONE**  
⬇️ 📡 BLE  
🧠 **MAIN BOARD**  
⬇️ 🔄 UART  
🚁 **FLIGHT BOARD**  
⬇️ 🎛️ PWM  
⚡ **ESCs**  
⬇️ 🔋  
🛸 **MOTORS**

</div>

- 📲 Android joystick sends control commands.
- 📡 Main ESP32-C3 receives BLE data.
- 🔍 Firmware validates the command format and range.
- 🔄 Main board transmits accepted commands over UART.
- 🧠 Flight firmware checks command freshness and arming state.
- 🎛️ ESC outputs remain at a safe stop command until arming conditions are satisfied.
- 🛑 Lost communication must trigger a verified motor-stop failsafe.

⚠️ **BLE connection alone does not prove that valid flight commands are reaching the flight controller.**

---

## 🔄🧠 04 // MAIN ↔️ FLIGHT UART WIRING 🧠🔄

```text
      💜 MAIN ESP32-C3 💜
     ╔══════════════════════╗
     ║ 📡 BLE               ║
     ║ 🎮 COMMAND PARSER    ║
     ║                      ║
     ║ TX ──────────────────╬──────────┐
     ║ RX ◄─────────────────╬──────┐   │
     ║ GND ◄────────────────╬───┐  │   │
     ╚══════════════════════╝   │  │   │
                                │  │   │
                            GND │  │   │ TX
                                │  │   ▼
     ╔══════════════════════╗   │  │
     ║ RX ◄─────────────────╬───┼──┘
     ║ TX ──────────────────╬───┘
     ║ GND ◄────────────────╬───────
     ║                      ║
     ║ 🚁 FLIGHT ESP32-C3   ║
     ╚══════════════════════╝

       🔵 TX → RX     🟣 RX ← TX
       ⚫ GND ↔ GND
```

| 🔌 CONNECTION | 🧠 MAIN BOARD | 🚁 FLIGHT BOARD |
|---|---|---|
| 📤 Transmit | TX pin chosen in firmware | RX pin chosen in firmware |
| 📥 Receive | RX pin chosen in firmware | TX pin chosen in firmware |
| ⚫ Ground | GND | GND |

🟡 Choose UART pins that are genuinely available on your particular ESP32-C3 SuperMini boards. The diagram intentionally does not assign new UART GPIO numbers.

---

## 🚁🎛️ 05 // FOUR-MOTOR CONTROL MATRIX 🎛️🚁

| 🛸 MOTOR | ⚡ ESC | 🧠 FLIGHT GPIO | 🟢 SIGNAL |
|---|---|---|---|
| 🔄 M1 | ⚡ ESC 1 | GPIO 2 | 🟢 PWM |
| 🔄 M2 | ⚡ ESC 2 | GPIO 3 | 🟢 PWM |
| 🔄 M3 | ⚡ ESC 3 | GPIO 4 | 🟢 PWM |
| 🔄 M4 | ⚡ ESC 4 | GPIO 5 | 🟢 PWM |

```text
          🚁 FLIGHT ESP32-C3
       ╔════════════════════════╗
       ║ GPIO 2 ──🟢── ⚡ ESC 1 ║── 🔄 M1
       ║ GPIO 3 ──🟢── ⚡ ESC 2 ║── 🔄 M2
       ║ GPIO 4 ──🟢── ⚡ ESC 3 ║── 🔄 M3
       ║ GPIO 5 ──🟢── ⚡ ESC 4 ║── 🔄 M4
       ╚════════════════════════╝

       🟢 SIGNAL ≠ 🔋 MOTOR POWER
       ⚡ ESC POWER STAGE DRIVES THE MOTOR
```

⚠️ GPIO assignments reflect your planned wiring. Check the exact board, boot behavior, and firmware configuration before use. A PWM signal does not guarantee safe motor operation.

---

## 🧭📊 06 // MPU6050 SENSOR GRID 📊🧭

| 🧭 SENSOR PIN | 🚁 FLIGHT BOARD | 🔬 PURPOSE |
|---|---|---|
| 🔴 VCC | 3V3 | ⚡ Sensor supply |
| ⚫ GND | GND | 🔌 Reference ground |
| 🔵 SDA | GPIO 8 | 📡 I²C data |
| 🟣 SCL | GPIO 9 | ⏱️ I²C clock |

```text
          🧭 MPU6050
       ╔════════════════════╗
       ║ 🔴 VCC ─────► 3V3  ║
       ║ ⚫ GND ─────► GND  ║
       ║ 🔵 SDA ─────► GPIO8║
       ║ 🟣 SCL ─────► GPIO9║
       ╚══════════╤═════════╝
                  │
                  ▼
          🧠 FLIGHT ESP32-C3
                  │
       ┌──────────┼──────────┐
       ▼          ▼          ▼
     📐 ROLL    🎯 PITCH    🌀 GYRO
       │          │          │
       └──────────┼──────────┘
                  ▼
          📊 SENSOR PROCESSING
                  ▼
          🛡️ FLIGHT SOFTWARE
```

💡 The MPU6050 provides acceleration and angular-velocity measurements. A complete flight controller also needs appropriate estimation, feedback control, motor mixing, calibration, and failsafe logic.

---

## 🔋⚡ 07 // HIGH-POWER BATTERY NETWORK ⚡🔋

```text
             🔋 3S LiPo BATTERY
            ⚡ 11.1V NOMINAL
            ⚡ 12.6V FULL CHARGE
                     │
                     ▼
            🔌 POWER DISTRIBUTION
                     │
           ┌─────────┼─────────┐
           ▼         ▼         ▼
         ⚡ ESC 1  ⚡ ESC 2  ⚡ ESC 3 / 4
           │         │         │
           ▼         ▼         ▼
         🔄 M1     🔄 M2     🔄 M3 / M4

          🔌 VERIFIED BEC / REGULATOR
                     │
              ┌──────┴──────┐
              ▼             ▼
          🧠 MAIN       🚁 FLIGHT
          ESP32-C3      ESP32-C3
```

🚨 **POWER RULES**

- 🔴 Never connect LiPo voltage directly to a 3V3 pin.
- ⚡ Verify BEC voltage, current capacity, and wiring.
- 🚫 Do not connect multiple ESC BEC 5V outputs together unless specifically designed for that.
- ⚫ Ensure a common ground for signal references.
- 🔋 Disconnect the battery before modifying connections.
- 🔥 Use appropriate connectors, wire gauges, and battery precautions.

---

## 🎨🌈 08 // NEON CONNECTION LEGEND 🌈🎨

| 🌈 COLOR | ⚙️ MEANING |
|---|---|
| 🔴 RED | ➕ Positive supply |
| ⚫ BLACK | ⏚ Ground |
| 🟢 GREEN | 🎛️ ESC signal |
| 🔵 BLUE | 📡 UART / SDA |
| 🟣 PURPLE | 🧭 I²C clock |
| 🟡 YELLOW | ⚠️ Verify the connection |
| 🟠 ORANGE | 🔋 Power distribution |
| 💗 PINK | ✨ UI / project styling |

---

## 🛡️🚨 09 // PRE-FLIGHT SAFETY CHECKLIST 🚨🛡️

- [ ] 🌀❌ Remove all propellers during bench testing.
- [ ] 🔋🔌 Disconnect the LiPo before rewiring.
- [ ] 🔍 Verify every ESC power and signal connection.
- [ ] 🧭 Confirm the MPU6050 responds correctly.
- [ ] 🔄 Verify UART communication in both directions.
- [ ] 📱 Confirm BLE commands arrive in the expected format.
- [ ] 🛑 Implement and test communication-loss failsafe.
- [ ] 🔒 Prevent arming during startup or invalid commands.
- [ ] ⚡ Verify BEC outputs and power distribution.
- [ ] 🎛️ Verify motor order and rotation direction safely.
- [ ] 🧪 Complete controlled testing before considering flight.
- [ ] 🚁 Never fly based only on successful compilation or motor spinning.

---

## 💜⚡ 10 // CYBERPUNK LAB STATUS ⚡💜

<div align="center">

<img src="https://img.shields.io/badge/NEURAL_CORE-ESP32--C3-00FFFF?style=for-the-badge&logo=espressif&logoColor=black"/>
<img src="https://img.shields.io/badge/TELEMETRY-MPU6050-FF00E5?style=for-the-badge"/>
<img src="https://img.shields.io/badge/COMMUNICATION-BLE%20%2B%20UART-7F00FF?style=for-the-badge"/>
<img src="https://img.shields.io/badge/PROPULSION-4%20ESCs-0500FF?style=for-the-badge"/>

💻 CODE ➜ 🔌 CONNECT ➜ 📊 MEASURE ➜ 🧪 TEST ➜ 🛡️ VERIFY

🤖 🧠 💜 💙 🩵 🔮 ⚡ 🔋 🚁 🛸 📡 🎮 🧭 ✨ 💎 🌌 🚀

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:FF00E5,20:7F00FF,40:0500FF,60:00E5FF,80:7F00FF,100:FF00E5&height=200&section=footer&animation=fadeIn"/>

### 🚁💜 VAJRA 1 // BUILD • TEST • INNOVATE 💜🚁

**🌌 ROBOTICS × ELECTRONICS × EMBEDDED SYSTEMS × FLIGHT CONTROL 🌌**

</div>
