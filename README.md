# Line Follower Bot with ESP32

A complete line follower robot project using ESP32 microcontroller, featuring PID control, OLED display interface, and interactive menu system.

## 📋 Overview

This project implements a sophisticated line follower robot capable of:
- Following black lines on white surfaces using 13 IR sensors
- PID-based motor control for smooth navigation
- OLED display for real-time status and menu navigation
- Interactive button-based menu for configuration
- EEPROM storage for persistent settings
- Automatic handling of line loss and recovery

## 🛠️ Hardware Components

### Required Components:
1. **Microcontroller**: ESP32 DevKit V1
2. **Motor Driver**: TB6612FNG
3. **Motors**: N20 metal gear motors (1500 RPM) x 2
4. **Power Supply**: LM2596 5V buck converter + 11.1V LiPo battery (1500 mAh)
5. **Display**: 0.96" OLED display (SSD1306)
6. **Sensors**: 9-array TCRT5000L IR sensor module
7. **Input**: 5 push buttons (UP, DOWN, LEFT, RIGHT, MIDDLE)
8. **PCB**: Custom PCB for connections
9. **Resistors**: 220 ohm (for IR sensors) x 13
10. **Potentiometer**: 10k ohm (for sensor calibration)
11. **Miscellaneous**: Jumper wires, connectors

### Sensor Calibration Video
For detailed sensor building and calibration instructions: [YouTube Tutorial](https://www.youtube.com/watch?v=IZvZkyqCajg)

## 🔧 Software Requirements

- **Arduino IDE** with ESP32 board support
- **Libraries**:
  - Wire.h (built-in)
  - Adafruit_GFX.h
  - Adafruit_SSD1306.h
  - EEPROM.h (built-in)

## 📁 Project Structure

```
LineFollowerBot/
├── main_code.txt          # Main Arduino sketch
├── requirements.txt       # Hardware components list
├── Circuit diagram.png    # Overall circuit schematic
├── lfr_frame.stl         # 3D printable robot frame
├── Step 1 circuit diagram of IR array.png
├── Step 2.png
├── ... (additional step images)
└── README.md             # This file
```

## 🚀 Getting Started

### 1. Hardware Assembly
Follow the step-by-step images (Step 1.png through Step 19.png) for complete assembly:
- IR sensor array construction
- Motor and driver connections
- ESP32 and OLED wiring
- Button interface setup
- Power supply integration

### 2. Software Setup
1. Install Arduino IDE
2. Add ESP32 board support via Board Manager
3. Install required libraries via Library Manager
4. Open `main_code.txt` in Arduino IDE
5. Select ESP32 DevKit V1 board
6. Choose correct COM port
7. Upload the code

### 3. Configuration
- Use the OLED menu to adjust PID parameters (Kp, Kd)
- Calibrate sensor threshold using the potentiometer
- Set base speed and track mode
- Settings are automatically saved to EEPROM

## 🎮 Usage

### Menu Navigation
- **UP/DOWN**: Navigate menu options
- **LEFT/RIGHT**: Adjust values
- **MIDDLE**: Select/Start

### Main Menu Options
1. **Start**: Begin line following
2. **Settings**: Access configuration menu

### Settings Menu
- Track Mode
- Speed Value
- Sensor Threshold
- Kp (Proportional gain)
- Kd (Derivative gain)

### Operation
1. Place robot on track with line visible to sensors
2. Use menu to start operation
3. Robot will follow the line using PID control
4. Press middle button to stop and return to menu

## 🔍 PID Control Explanation

The robot uses a PID controller for smooth line following:

- **Proportional (P)**: Responds to current position error
- **Integral (I)**: Corrects for steady-state error
- **Derivative (D)**: Predicts future error based on rate of change

### Tuning Guidelines
- **Kp**: Increase for faster response, decrease for stability
- **Ki**: Usually set to 0 for line followers
- **Kd**: Increase to reduce oscillations

## 🛠️ Troubleshooting

### Common Issues
1. **Robot not following line**
   - Check sensor calibration
   - Verify sensor connections
   - Adjust PID values

2. **Motors not responding**
   - Check motor driver connections
   - Verify power supply voltage
   - Test motor wires

3. **OLED not displaying**
   - Check I2C connections (SDA=21, SCL=22)
   - Verify OLED address (0x3C)

4. **Line loss behavior**
   - Robot spins when line is lost
   - Timeout after 30ms triggers search pattern

## 📊 Technical Specifications

- **Microcontroller**: ESP32 (240MHz dual-core)
- **Sensors**: 13 IR sensors (multiplexed)
- **Motor Control**: PWM at 10kHz, 8-bit resolution
- **Display**: 128x64 OLED with I2C interface
- **Power**: 11.1V input, 5V regulated
- **EEPROM**: 128 bytes for settings storage

## 🤝 Contributing

Feel free to submit issues and enhancement requests!

## 📄 License

This project is open source. Please credit the original work when using or modifying.

## 📞 Support

For questions or issues:
- Check the troubleshooting section
- Review the step-by-step assembly images
- Watch the sensor calibration video

---

**Happy building!** 🏁🤖
