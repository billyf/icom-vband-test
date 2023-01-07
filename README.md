# icom-vband-test

An app for sending CW on VBand or Vail using only your radio (if it provides a USB soundcard).

It monitors the audio level and virtually presses the Ctrl key when it detects the sidetone (or any volume spike) from your rig.

## Usage:
1. Download [main.py](https://raw.githubusercontent.com/billyf/icom-vband-test/main/main.py)
2. Rotate RF/SQL knob to maximum squelch (choose a quiet band if needed)
3. Run `python main.py` (or `python3 main.py`)
4. Switch to the VBand/Vail tab, then key your radio (with BK-IN off).

The VBand/Vail tab needs to stay in focus to receive the Ctrl key.  
Quit the app before undoing the squelch so the Ctrl key won't be sent from band noise.

## Setup:
### VBand / Vail
- Settings -> Mode = **Straight Key / Cootie**
- You can disable your sidetone in the channel if listening to the rig sidetone

### Radio (Icom 7300 example)
- `Menu -> Set -> Connectors -> ACC/USB AF SQL` = **ON**  
(so no audio is passed through while the squelch is enabled)

### For other USB devices:
- Modify AUDIO_THRESHOLD for the levels on your soundcard.  
You can set `PRINT_RMS_VALUES = True` to see what they are during key up and key down.

## Requirements:
- **pyaudio**
- **pyautogui** (Linux) or **pydirectinput** (Windows)

`python -m pip install -r requirements.txt`