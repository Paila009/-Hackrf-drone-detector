# HackRF Drone Detector

A Python-based desktop tool for scanning radio frequencies commonly used by consumer drones, visualizing signal behavior, and optionally triggering alerts or experimental jamming through a HackRF One device.

The project includes an English version and a Russian version of the interface:
- [hackrf-drone-detector-V05.py](hackrf-drone-detector-V05.py)
- [hackrf-drone-detector-V05_rus.py](hackrf-drone-detector-V05_rus.py)

## What this project does

The application is designed for:
- monitoring common drone-related frequency bands
- measuring RSSI strength over time
- displaying signal trends in a graphical interface
- detecting suspicious signal patterns using multiple heuristics
- sending optional email or Telegram alerts
- experimenting with jamming controls through HackRF tools

> Note: false positives are possible. The detector uses heuristics and should be treated as an experimental research tool rather than a guaranteed drone identifier.

## Features

- Scan multiple frequencies including 433 MHz, 868 MHz, 915 MHz, 2.4 GHz, and 5.8 GHz
- Real-time signal visualization with Matplotlib
- Tkinter-based graphical user interface
- Adaptive threshold support and signal trend analysis
- Optional audio alerts and notifications
- Experimental jamming support via hackrf_transfer

## Hardware and software requirements

### Hardware
- HackRF One device
- Compatible antenna
- A Linux computer with USB access to the HackRF device

### Software
- Python 3.8 or newer
- pip
- hackrf-tools / hackrf_transfer
- tkinter support for the GUI

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/Sh7yk/hackrf-drone-detector.git
cd hackrf-drone-detector
```

### 2. Create and activate a virtual environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install system dependencies

#### Ubuntu / Debian

```bash
sudo apt update
sudo apt install -y python3 python3-pip python3-tk python3-dev
sudo apt install -y hackrf libhackrf-dev
sudo apt install -y portaudio19-dev
```

#### Fedora

```bash
sudo dnf install -y python3 python3-pip python3-tkinter python3-devel
sudo dnf install -y hackrf hackrf-tools
```

#### Arch Linux

```bash
sudo pacman -S python python-pip tk
sudo pacman -S hackrf
```

### 4. Install Python packages

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Verify HackRF is detected

```bash
hackrf_info
```

If the command is not found, ensure the HackRF tools are installed and available in your PATH.

## Running the detector

Start the English version:

```bash
python3 hackrf-drone-detector-V05.py
```

Start the Russian version:

```bash
python3 hackrf-drone-detector-V05_rus.py
```

## Configuration

The program can create a configuration file named config.json for storing settings such as:
- scan frequencies
- signal thresholds
- bandwidth values
- notification options
- jamming parameters

## Important safety and legal notice

The jamming feature may be illegal in your country or region. Use it only in controlled lab environments or with explicit authorization where permitted.

This software is provided for educational and research purposes. The author is not responsible for any unauthorized use, interference, or hardware damage caused by misuse.

## Troubleshooting

- If HackRF is not detected, confirm that the device is connected and that hackrf_info works.
- If the GUI does not start, make sure tkinter is installed.
- If audio alerts are not available, pygame may be missing; the application can still run without them.
- If you see many false positives, adjust thresholds and scan settings in the interface or configuration file.

## File overview

- [hackrf-drone-detector-V05.py](hackrf-drone-detector-V05.py) - main English implementation
- [hackrf-drone-detector-V05_rus.py](hackrf-drone-detector-V05_rus.py) - Russian-language version
- [requirements.txt](requirements.txt) - Python dependencies
