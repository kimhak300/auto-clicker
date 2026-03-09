# Auto Clicker Pro v2

A modern, full-featured Windows desktop auto clicker with dark theme UI, keyboard recording, macro editor, scheduler, and web automation.

## Features

### 1. Simple Clicker
- Click interval: hours, minutes, seconds, milliseconds
- Mouse button: left / right / middle
- Click type: single, double, triple
- Repeat: infinite or fixed count
- Random jitter option for human-like clicking

### 2. Coordinate Clicker
- Define (x, y, delay) coordinate sequences
- F8 hotkey to pick coordinates by clicking on screen
- Multi-monitor support (shows all monitor positions)
- Loop count and button selection

### 3. Record & Replay
- Record **mouse clicks + keyboard presses** with precise timing
- Toggle recording for mouse only, keyboard only, or both
- Replay at 0.25x, 0.5x, 1x, 2x, 4x, or 8x speed
- Save/load recordings as JSON files
- Hotkey F7 to start/stop recording

### 4. Image Recognition Click
- Provide a screenshot of a UI element (button, icon, etc.)
- Continuously scans the screen for that image
- Adjustable confidence threshold (0-1)
- Optional search region to limit where it looks
- Actions: click, double-click, right-click, or move only

### 5. Web Browser Automation (Selenium)
- Launch Chrome, Edge, or Firefox (headless optional)
- Auto-installs drivers via webdriver-manager
- Script commands:
  - `click css=#btn` - click an element
  - `type id=input Hello` - type text
  - `keys id=input ENTER` - send special keys
  - `wait 2.0` - pause seconds
  - `wait css=#result` - wait for element
  - `scroll 500` - scroll pixels
  - `hover css=#menu` - hover element
  - `select css=#drop Option` - dropdown selection
  - `screenshot file.png` - save screenshot
  - `js document.title` - execute JavaScript
- Loop scripts with configurable delays

### 6. Macro Editor
- Visual step builder with add/edit/delete
- Action types: Mouse Click, Mouse Move, Key Press, Type Text, Wait, Image Click, Scroll
- **Drag-and-drop reordering** of steps
- Move up/down buttons and duplicate
- Save/load macros as JSON files
- Run macros with loop count

### 7. Scheduler
- Schedule saved macros to run at specific times
- Repeat options: Once, Daily, Weekdays, Weekends, or specific day
- Enable/disable individual schedules
- Shows next run time
- Background scheduler thread checks every 30 seconds

## Setup

```bash
pip install -r requirements.txt
```

### Dependencies

| Package | Purpose |
|---------|---------|
| customtkinter | Modern dark theme UI |
| pyautogui | Mouse/keyboard automation |
| pynput | Mouse/keyboard event capture |
| Pillow | Image handling |
| keyboard | Global hotkeys |
| opencv-python | Image recognition |
| screeninfo | Multi-monitor detection |
| selenium | Web browser automation |
| webdriver-manager | Auto browser driver install |

## Run

```bash
python auto_clicker.py
```

## Hotkeys

| Key | Action |
|-----|--------|
| F6 | Start / Stop simple clicker |
| F7 | Start / Stop recording |
| F8 | Pick screen coordinate |

## Safety

- **Failsafe:** Move mouse to the **top-left corner** to immediately abort any automation.
- All automation stops when the window is closed.
- Scheduler and background threads cleanly shut down on exit.

## Tips

- For image recognition, take a **small, unique** screenshot of the element (save as PNG).
- Use coordinate picker (F8) to quickly build click sequences across multiple monitors.
- Recordings and macros are saved as JSON - you can edit them manually.
- Macros saved from the Macro Editor can be scheduled in the Scheduler tab.
