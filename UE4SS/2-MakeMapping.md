# UE4SS – 2. Make a New Mapping File

[⬅ 1. Setup](1-Setup.md) · [Back to UE4SS](README.md)

Do this when FModel starts showing errors after a **game update**.

---

## 🧭 How do I know I need a new one?

- FModel worked before, but after a game update files show **errors** or **empty data**.
- Or the newest file in [Mappings](../FModel/Mappings/README.md) has an **older build number** than your game.

---

## Step 1 – Start the game with UE4SS on
1. Make sure UE4SS is set up: [1. Setup](1-Setup.md).
2. Start Eastern Era from Steam.
3. **Wait** until you reach the **main menu**. Even better, load a save and wait until you're in the world.
   (More of the game is loaded then, so the mapping is more complete.)

## Step 2 – Make the mapping file

Pick **one** way:

### Way A – Keyboard shortcut (easiest)
1. Click on the game window so it's selected.
2. Press **Ctrl + Numpad 6** (the **6** on the number pad on the right of your keyboard, not the 6 above the letters).
   - No number pad? Use Way B.

### Way B – UE4SS window
1. Go to the **UE4SS window** that opened with the game.
2. Click the **Dumpers** tab.
3. Click **Generate .usmap file**.

Wait a few seconds. The black log window will say it's done.

## Step 3 – Find the file

1. Go to the `ue4ss` folder:
   ```
   ...\steamapps\common\EasternEra\EasternEra\Binaries\Win64\ue4ss\
   ```
2. Look for a new **`.usmap`** file. Its name looks like this:
   ```
   EasternEra-5.6.1-44394996+++UE5+Release-5.6-97b7e501.usmap
   ```
   - `5.6.1` = Unreal version
   - `44394996` = **game build number** (changes with updates)
   - `97b7e501` = UE4SS version used
3. Sort by **Date modified** if there are several. The newest is yours.

## Step 4 – Use it in FModel

1. Copy the `.usmap` next to FModel (e.g. `C:\Modding\FModel\`).
2. In FModel: **Settings → General → Mapping File Path → …** and pick the new file.
3. Click **OK** and **restart FModel**.
4. Load the game files again. The errors should be gone. ✅

## Step 5 – Share it (optional, but very helpful!)

Help others by adding it to this repository:

1. **Rename** it to something simple, without `+` signs (they break download links). Keep the build number:
   `EasternEra-5.6.1-<build number>.usmap`
2. Go to [FModel/Mappings](../FModel/Mappings/README.md) on GitHub.
3. **Add file → Upload files**, drag in your `.usmap`, then **Commit changes**.
   - Not the owner of the repository? GitHub will make a **pull request** for you. That's a request to add your file, and the owner can accept it.
4. Edit [`FModel/Mappings/README.md`](../FModel/Mappings/README.md) and add a new row **at the top** of the table with the build number and today's date.

---

## 🔌 Done? Turn UE4SS off

You only need UE4SS to make the mapping. When you're done, rename `dwmapi.dll` to `dwmapi.dll.off` in `Win64`. [More info](1-Setup.md#-turn-ue4ss-off-or-remove-it)

---

## 🛠 Problems

| Problem | Fix |
|---|---|
| Ctrl + Numpad 6 does nothing | Click the game window first. Check `Keybinds : 1` in `ue4ss\Mods\mods.txt`. Or use Way B. |
| No `.usmap` file appears | Read the end of `ue4ss\UE4SS.log` for errors. |
| Game crashes while making it | Wait longer before pressing it (load into the world first), and try again. |
| FModel still shows errors | Did you restart FModel? Is the UE version still **`GAME_UE5_6`**? A big update may need a newer UE4SS too. |

[⬅ 1. Setup](1-Setup.md) · [Back to UE4SS](README.md)
