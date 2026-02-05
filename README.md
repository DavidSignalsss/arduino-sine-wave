# Arduino Sine-Scope
This project implements a sine wave generator with morphing to a sawtooth waveform using an Arduino Nano (or other ATmega328P compatible) and displays it on a 128x64 I2C OLED screen using the U8g2 library.  It's ideal for audio testing, DIY synthesizers, and waveform teaching.

# Arduino Waveform Generator with OLED Oscilloscope

This project is a **waveform generator with real-time oscilloscope display**, capable of producing sine, sawtooth, and blended waveforms. Designed for **Arduino Nano** and similar boards.

## 🎛 Features

- 🎶 **Generates waveforms** from sine to sawtooth
- 🎚 Real-time control via **3 potentiometers**
  - `A0`: Frequency (50 Hz to 1000 Hz)
  - `A1`: Volume
  - `A2`: Waveform shape (Sine ↔ Saw)
- 🖥️ **128x64 OLED display** acts as a mini oscilloscope
- 🔉 Audio output via **PWM on pin D9**
- ⏱ Accurate frequency control using **Timer2 interrupts**
- 💾 Optimized memory usage (wave table in RAM + partial display buffer)

## 🧰 Hardware Requirements

- Arduino Nano or Uno
- 3 Potentiometers (connected to A0, A1, A2)
- SSD1306 OLED Display (128x64, I2C)
- Audio output connected to D9 (add a low-pass filter for smoother audio)

## 📦 Required Libraries

Install these from the Arduino Library Manager:

- [`U8g2`](https://github.com/olikraus/u8g2) by olikraus

## ⚙️ Code Structure

- `setupPWM()` – Configures PWM output on D9
- `setupTimer2()` – Sets up the timer interrupt for waveform updates
- `generateWaveform()` – Creates waveform data based on potentiometer input
- `drawScope()` – Renders the waveform visually on the OLED
- `updateTimerForFrequency()` – Dynamically adjusts output frequency

## 🔊 How It Works

The code fills a waveform table (`waveTable[]`) with amplitude values and uses **Timer2** to output those values through PWM (Timer1 on D9).  
Meanwhile, the OLED graphically shows the waveform, emulating an oscilloscope.

## 📸 Demo

<p align="center">
  <img src="ArduinoSineScope.jpeg" alt="Step 1" width="300">
</p>
<p align="center"><em>Figure – OLED Screen with Sine Scope.</em></p>


## 🪪 License

This project is licensed under the [MIT License](./LICENSE).  
You are free to use, modify, and distribute it.

---

## 👨‍💻 Developed by

**David Rábago Félix**  
Mechatronics Engineer  
🇲🇽 Mexico, 2025
