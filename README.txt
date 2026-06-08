
================================================================================

# Smart Robot Car V4.0 Project Documentation

This document aims to help users configure the development environment, compile the code, and upload it to the Smart Robot Car V4.0 hardware.

## 1. Project Introduction
Smart Robot Car V4.0 is a smart robot car project developed by ELEGOO. The code in this project implements the core control logic of the car, including motion control, sensor data acquisition (line tracking, ultrasonic, gyroscope), RGB lighting control, and IR/serial command processing.

**Current Version**: 2.1.2

## 2. Environment Preparation

Before starting, please ensure that the following software is installed on your computer:

### 2.1 Integrated Development Environment (IDE)
We recommend using one of the following IDEs:
*   **Arduino IDE** (Recommended for beginners): [Download Link](https://www.arduino.cc/en/software)
*   **Visual Studio Code** (with Arduino extension): Suitable for advanced users.

### 2.2 Library Installation
This project depends on the following Arduino libraries. Please install them via the Arduino Library Manager before compiling:
1.  **FastLED**: For controlling RGB LEDs.
2.  **Servo**: For controlling servos.
3.  **ArduinoJson**: For parsing serial JSON commands (This project already includes the `ArduinoJson-v6.11.1.h` header file, no extra installation is needed, but please ensure the include path is correct).
4.  **Wire**: Standard Arduino library (usually built-in).
5.  **SPI**: Standard Arduino library (usually built-in).

## 3. Hardware Configuration & Pin Definitions

The hardware pins for Smart Robot Car V4.0 are already predefined in the code and usually do not need modification. For reference only:

*   **Motor Driver**:
    *   Left Motor: PWM Pin 6, Direction Pin 8
    *   Right Motor: PWM Pin 5, Direction Pin 7
    *   Standby Control (STBY): Pin 3
*   **Sensors**:
    *   Line Tracking Module: Right (A0), Middle (A1), Left (A2)
    *   Voltage Detection: A3
    *   Button Input: Pin 2
    *   RGB LED: Pin 4
    *   MPU6050: I2C Interface (SDA/SCL)

## 4. Compilation & Upload Guide

### Using Arduino IDE
1.  Double-click to open the `SmartRobotCarV4.0.ino` file.
2.  In the menu bar, select **Tools** > **Board** > **Arduino AVR Boards** > **Arduino Uno**.
3.  Connect the car to the computer via a USB cable.
4.  In the menu bar, select **Tools** > **Port** and choose the corresponding COM port.
5.  Click the **Verify** button (checkmark icon) to check for code errors.
6.  Click the **Upload** button (right arrow icon) to burn the code to the main board.

### Using Visual Studio Code
1.  Open the project folder `SmartRobotCarV4.0`.
2.  Ensure the Microsoft Arduino extension is installed.
3.  Configure via the status bar or `.vscode/arduino.json`:
    *   Board: `arduino:avr:uno`
    *   Port: Select the actual connected port (e.g., `COM3`)
4.  Press `F1`, type `Arduino: Upload` to compile and upload.

## 5. Debugging & Usage
*   **Serial Monitor**: After successful upload, you can open the Serial Monitor.
*   **Baud Rate**: Set to **9600** baud.
*   **Startup Message**: After reset, the serial port should print `SmartRobotCarV4.0 - System Ready`.
*   **Communication Protocol**: The car uses JSON format to receive commands via the serial port.

## 6. FAQ
*   **Compilation Error**: If prompted that `FastLED.h` or `Servo.h` cannot be found, please check if the libraries are correctly installed.
*   **Upload Failure**: Please check if the USB connection is stable, the port is selected correctly, and the board driver is installed.
*   **Car Not Moving**: Check the battery level and whether the `STBY` pin is correctly pulled high (handled in the code, but ensure the hardware switch is on).


================================================================================

# Smart Robot Car V4.0 项目说明文档

本文档旨在帮助用户配置开发环境、编译代码并将其上传到 Smart Robot Car V4.0 硬件中。

## 1. 项目简介
Smart Robot Car V4.0 是由 ELEGOO 开发的智能机器人小车项目。本项目代码实现了小车的核心控制逻辑，包括运动控制、传感器数据采集（循迹、超声波、陀螺仪）、RGB 灯光控制以及红外/串口命令处理。

**当前版本**: 2.1.2

## 2. 环境准备

在开始之前，请确保您的计算机上已安装以下软件：

### 2.1 集成开发环境 (IDE)
推荐使用以下任意一种 IDE：
*   **Arduino IDE** (推荐初学者): [下载地址](https://www.arduino.cc/en/software)
*   **Visual Studio Code** (配合 Arduino 扩展): 适合高级用户。

### 2.2 依赖库安装
本项目依赖以下 Arduino 库，请在编译前通过 Arduino 库管理器 (Library Manager) 安装：
1.  **FastLED**: 用于控制 RGB 灯珠。
2.  **Servo**: 用于控制舵机。
3.  **ArduinoJson**: 用于解析串口 JSON 命令 (本项目已包含 `ArduinoJson-v6.11.1.h` 头文件，无需额外安装，但请确保引用路径正确)。
4.  **Wire**: Arduino 标准库（通常自带）。
5.  **SPI**: Arduino 标准库（通常自带）。

## 3. 硬件配置与引脚定义

代码中已预定义了 Smart Robot Car V4.0 的硬件引脚，通常无需修改。仅供参考：

*   **电机驱动**:
    *   左电机: PWM引脚 6, 方向引脚 8
    *   右电机: PWM引脚 5, 方向引脚 7
    *   待机控制 (STBY): 引脚 3
*   **传感器**:
    *   循迹模块: 右(A0), 中(A1), 左(A2)
    *   电压检测: A3
    *   按键输入: 引脚 2
    *   RGB LED: 引脚 4
    *   MPU6050: I2C 接口 (SDA/SCL)

## 4. 编译与上传指南

### 使用 Arduino IDE
1.  双击打开 `SmartRobotCarV4.0.ino` 文件。
2.  在菜单栏选择 **工具 (Tools)** > **开发板 (Board)** > **Arduino AVR Boards** > **Arduino Uno**。
3.  通过 USB 线将小车连接到电脑。
4.  在菜单栏选择 **工具 (Tools)** > **端口 (Port)**，选择对应的 COM 端口。
5.  点击 **验证 (Verify)** 按钮（对号图标）检查代码是否有误。
6.  点击 **上传 (Upload)** 按钮（右箭头图标）将代码烧录到主板。

### 使用 Visual Studio Code
1.  打开项目文件夹 `SmartRobotCarV4.0`。
2.  确保已安装 Microsoft 的 Arduino 扩展。
3.  状态栏或 `.vscode/arduino.json` 配置如下：
    *   Board: `arduino:avr:uno`
    *   Port: 选择实际连接的端口 (例如 `COM3`)
4.  按 `F1` 输入 `Arduino: Upload` 进行编译和上传。

## 5. 调试与使用
*   **串口监视器**: 上传成功后，可以打开串口监视器 (Serial Monitor)。
*   **波特率**: 设置为 **9600** baud。
*   **启动信息**: 复位后，串口应打印 `SmartRobotCarV4.0 - System Ready`。
*   **通信协议**: 小车使用 JSON 格式通过串口接收指令。

## 6. 常见问题
*   **编译错误**: 如果提示找不到 `FastLED.h` 或 `Servo.h`，请检查库是否已正确安装。
*   **上传失败**: 请检查 USB 连接是否稳固，端口是否选择正确，以及主板驱动是否安装。
*   **小车不动作**: 检查电池电量，以及 `STBY` 引脚是否被正确拉高（代码中已处理，需确保硬件开关打开）。

---
@Author: ELEGOO
@Date: 2026-03-06