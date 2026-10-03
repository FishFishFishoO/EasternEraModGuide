# UE4SS – 1. Setup

[⬅ Back to UE4SS](README.md) · Next: [2. Make a new mapping file ➡](2-MakeMapping.md)

---

> ⚠️ **Read first**
> - UE4SS changes how the game runs. It can **crash** the game sometimes. That's normal for this tool.
> - **Turn it off** when you're just playing (see [Turn UE4SS off](#-turn-ue4ss-off-or-remove-it)).
> - Don't send bug reports to the developers while UE4SS is installed.
> - Only download UE4SS from the official link below.

---

## Step 1 – Download the right version

Eastern Era uses **Unreal Engine 5.6**, so you need the **experimental** version of UE4SS. The older "stable" one doesn't support 5.6.

1. Go to **https://github.com/UE4SS-RE/RE-UE4SS/releases**
2. Find the release called **experimental-latest** (it has a "Pre-release" tag).
3. Under **Assets**, download the file named like **`UE4SS_v3.0.1-XXXX-gXXXXXXX.zip`**.
   - ❌ **Not** the one starting with `zDEV-` (that's for developers).
   - ✅ This guide was tested with **`UE4SS_v3.0.1-1111-g97b7e501`**.
4. Right-click the ZIP → **Extract All…**

Inside you'll see:
```
dwmapi.dll
ue4ss\
```

## Step 2 – Find the game's Win64 folder

1. In Steam, right-click **Eastern Era** → **Manage → Browse local files**.
2. Open: `EasternEra` → `Binaries` → `Win64`
3. You're in the right place if you see **`EasternEra-Win64-Shipping.exe`**.

Full path is normally:
```
C:\Program Files (x86)\Steam\steamapps\common\EasternEra\EasternEra\Binaries\Win64\
```

⚠️ **Not** the first folder that has `EasternEra.exe`. UE4SS must sit next to **`EasternEra-Win64-Shipping.exe`**.

## Step 3 – Copy UE4SS in

Copy **`dwmapi.dll`** and the **`ue4ss`** folder into `Win64`. It should look like:

```
Win64\
├── EasternEra-Win64-Shipping.exe
├── dwmapi.dll          ← new
└── ue4ss\              ← new
    ├── UE4SS.dll
    ├── UE4SS-settings.ini
    ├── Mods\
    └── ...
```

## Step 4 – Change the settings (important!)

1. Open the `ue4ss` folder.
2. Right-click **`UE4SS-settings.ini`** → **Open with → Notepad**.
3. Press **Ctrl + F** to find each setting below and change it.

| Find this | Default | Change to | Why |
|---|---|---|---|
| `MajorVersion =` | *(empty)* | `MajorVersion = 5` | Tells UE4SS the game uses Unreal **5**.6 |
| `MinorVersion =` | *(empty)* | `MinorVersion = 6` | Tells UE4SS the game uses Unreal 5.**6** |
| `ConsoleEnabled =` | `0` | `ConsoleEnabled = 1` | Shows the log window |
| `GuiConsoleEnabled =` | `0` | `GuiConsoleEnabled = 1` | Turns on the UE4SS window |
| `GuiConsoleVisible =` | `0` | `GuiConsoleVisible = 1` | Shows that window when the game starts |
| `GraphicsAPI =` | `opengl` | `GraphicsAPI = dx11` | Stops the window being blank or crashing |

When you're done, those parts look like this:

```ini
[EngineVersionOverride]
MajorVersion = 5
MinorVersion = 6
```
```ini
[Debug]
ConsoleEnabled = 1
GuiConsoleEnabled = 1
GuiConsoleVisible = 1
```
```ini
GraphicsAPI = dx11
```

4. Press **Ctrl + S** to save.
   - "Access denied"? Save it to your Desktop, then drag it back into the `ue4ss` folder and choose **Replace**.

## Step 5 – Check the Keybinds mod is on

1. Open `ue4ss\Mods\` and open **`mods.txt`** in Notepad.
2. Make sure this line is there and ends in **1**:
   ```
   Keybinds : 1
   ```
3. Save.

## Step 6 – Test it

1. Start Eastern Era from Steam like normal.
2. A **black log window** and a **UE4SS window** should open with the game. ✅
3. Nothing opened? See the problems below.

---

## 🛠 Problems

| Problem | Fix |
|---|---|
| No UE4SS windows open | `dwmapi.dll` must be in `Binaries\Win64`, next to `EasternEra-Win64-Shipping.exe`. |
| Game crashes on start | Check `MajorVersion = 5` and `MinorVersion = 6`. Try the newest **experimental-latest** UE4SS. |
| UE4SS window is blank/white | Set `GraphicsAPI = dx11`. |
| Antivirus deletes `dwmapi.dll` | This is a known false alarm for UE4SS. Only download from the official GitHub link. |
| Can't save the settings file | Save to Desktop, then drag it back in and replace. |
| What went wrong? | Open `ue4ss\UE4SS.log` in Notepad and look at the last lines. Share it in an Issue. |

---

## 🔌 Turn UE4SS off (or remove it)

- **Turn off:** rename `dwmapi.dll` to `dwmapi.dll.off`. Rename it back to turn it on again.
- **Remove:** delete `dwmapi.dll` and the `ue4ss` folder from `Win64`.

[⬅ Back to UE4SS](README.md) · Next: [2. Make a new mapping file ➡](2-MakeMapping.md)
