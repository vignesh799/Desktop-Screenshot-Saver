# Screenshot Saver

Screenshot Saver is a simple Windows desktop app built with Python and tkinter.

## Folder structure

```text
Screenshot Saver/
  assets/
    background.png
    background_app.png
    camera.png
    pause.png
  screenshot_saver.py
  requirements.txt
  README.md
```

When the app runs, it creates a temporary `screenshot_temp` folder beside the script or `.exe`. Each click of **Camera** saves one screenshot of the current screen. After you click **Pause / Stop**, it creates a Word document and removes the temporary screenshots.

## Run from Python

1. Open PowerShell in this folder.
2. Create a virtual environment:

```powershell
python -m venv .venv
```

3. Activate it:

```powershell
.\.venv\Scripts\Activate.ps1
```

4. Install dependencies:

```powershell
pip install -r requirements.txt
```

5. Run the app:

```powershell
python screenshot_saver.py
```

## Build the .exe

Run this command from the same folder:

```powershell
pyinstaller --onefile --windowed --name "Screenshot Saver" --add-data "assets;assets" screenshot_saver.py
```

The `.exe` file will be created here:

```text
dist\Screenshot Saver.exe
```

## How to use

1. Open `Screenshot Saver.exe`.
2. Click **Camera** to take a screenshot of the current screen.
3. Move to the next page and click **Camera** again whenever you want another screenshot.
4. Click **Pause / Stop** when you are done.
5. A Word document named like `Screenshots_YYYY-MM-DD_HH-MM-SS.docx` is saved beside the app.
6. Click **Exit** when finished.

The app never captures silently. It only captures when **Camera** is clicked, and the popup window stays visible while it is running.
