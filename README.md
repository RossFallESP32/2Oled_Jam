# 📡 2OLED Jam Device – RF Jamming Interface with ESP32

This project is a dual-bus RF jamming controller built around the ESP32 platform. It uses two OLED displays to provide a user interface and real-time feedback on RF channel activity across two independent RF24 modules (HSPI and VSPI).

![2OLED Jam Circuit Diagram](assets/YysXzo9yF6mmdvrqHnS6X.png)

> View the full circuit simulation on Cirkit Designer:  
👉 [Open the project in Cirkit Designer](https://app.cirkitdesigner.com/project/64a3d173-33f8-48d8-96f6-68df3df7daf9)

---

## 🧩 Features

- **Dual OLED Display (0.96")**  
  - Primary screen: Menu navigation and mode selection  
  - Secondary screen: Real-time RF channel status for both radios

- **RF24 Dual Bus Control**  
  - Independent control over HSPI and VSPI RF modules  
  - Supports multiple jamming modes

- **User Input Interface**  
  - 4 physical buttons: UP / DOWN / OK / BACK  
  - EEPROM saves last selected mode

- **Idle Animation**  
  - Displays alternating bitmap images when idle for more than 10 seconds

---

## ⚙️ Supported Modes

| Mode Name         | Description                                      |
|-------------------|--------------------------------------------------|
| `dualBLE`         | BLE jamming on both HP and SP radios             |
| `dualClassic`     | Classic Bluetooth jamming on both radios         |
| `dual125Ch`       | Random hopping across 125 channels               |
| `dualWifiCh`      | WiFi 2.4GHz channel jamming                      |
| `dualRand80`      | Random jamming across channels 0–79              |
| `dualRand125`     | Random jamming across channels 0–124             |
| `singleVSble`     | BLE jamming on SP radio only                     |
| `singleVSclassic` | Classic Bluetooth jamming on SP radio only       |
| `singleVSwifi`    | WiFi jamming on SP radio only                    |
| `singleVS80`      | Random SP jamming across channels 0–79           |
| `singleVS125`     | Random SP jamming across channels 0–124          |
| `singleHSble`     | BLE jamming on HP radio only                     |
| `singleHSclassic` | Classic Bluetooth jamming on HP radio only       |
| `singleHSwifi`    | WiFi jamming on HP radio only                    |
| `singleHS80`      | Random HP jamming across channels 0–79           |
| `singleHS125`     | Random HP jamming across channels 0–124          |

---

## 🖥️ How to Use

1. **Power Up**  
   Connect the ESP32, OLEDs, RF modules, buttons, and battery as shown in the circuit diagram.

2. **Navigate Menu**  
   - Use UP/DOWN buttons to scroll through options  
   - Press OK to select a mode  
   - The selected mode is saved to EEPROM

3. **Start Jamming**  
   - Enter the Jam or Test menu  
   - Press OK to toggle jamming ON/OFF  
   - The secondary OLED displays current RF channels for both radios

4. **Idle Mode**  
   - If no input is detected for 10 seconds, the secondary screen shows alternating idle images

---

## 🔧 Build & Upload

Using PlatformIO:
```bash



---

### ✅ Next Steps

To upload this to GitHub:

1. Save the above content into a file named `README.md` in your project root.
2. Create a folder named `assets/` and place your circuit image (`YysXzo9yF6mmdvrqHnS6X.png`) inside it.
3. Run the following Git commands:
```bash
git add README.md assets/YysXzo9yF6mmdvrqHnS6X.png
git commit -m "Add README with usage guide, mode descriptions, and circuit image"
git push origin main

pio run
pio run --target upload
pio device monitor
