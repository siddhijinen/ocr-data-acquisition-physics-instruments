# Spectra Scan: Real-Time OCR Data Acquisition for Physics Instruments

`Spectra Scan` is a Python-based automation pipeline designed to extract real-time numerical readings from legacy or proprietary GUI displays of laboratory instruments (such as spectrometers) without direct hardware or software integration.

It uses region-targeted screen capture and Optical Character Recognition (OCR) to convert visual data readouts into structured, time-stamped `.xlsx` records mapped against experimental independent variables.

---

## Key Features

* **Non-Invasive Data Extraction:** Reads dynamic numerical readouts straight from GUI displays without requiring proprietary software exports or expensive hardware upgrades.
* **Real-Time Hotkey Triggering:** Intercepts global keystrokes (`F9`) to take instant snapshots of target screen coordinates with low latency.
* **Image Preprocessing:** Converts regions of interest to grayscale to maximize Tesseract OCR engine accuracy.
* **Automatic Excel Logging:** Generates structured Excel workbooks named after trial parameters (e.g., wavelength) with timestamps, step increments, and raw intensity readings.
* **Precision Handling:** Prevents floating-point error accumulation across step increments.

---

## Tech Stack

* **Language:** Python 3.10+
* **OCR Engine:** Tesseract OCR (v5.0+)
* **Libraries:** `pyautogui`, `pytesseract`, `keyboard`, `openpyxl`, `Pillow`

---

## Getting Started

### Prerequisites

1. Install [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) on your machine.
2. Update the Tesseract executable path in `main.py` if installed outside default directories:
   ```python
   pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'
   ```

### Installation

```bash
git clone [https://github.com/siddhijinen/ocr-data-acquisition-physics-instruments.git](https://github.com/siddhijinen/ocr-data-acquisition-physics-instruments.git)
cd ocr-data-acquisition-physics-instruments
pip install pyautogui pytesseract keyboard openpyxl pillow
```

### Usage
Run the script:

```bash
python main.py
```

* Enter the experimental parameter inputs when prompted (e.g., target wavelength, starting step value, step increment).

* Press F9 during the experiment to record a snapshot reading to Excel.

* Press Esc to stop the script.
