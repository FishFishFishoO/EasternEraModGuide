# Example: New-Game Portraits

[⬅ Back to Unreal Engine](../../README.md) · [Main page](../../../README.md)

This example adds **new portraits** for the player character to choose from when starting a **new game**.

> 📦 This folder has the **settings files** (`.json`).
> The portrait pictures (`.uasset`) are **not included**. You make your own.

---

## 📁 Files in this example

| File | What it is |
|---|---|
| [`ModInfo.json`](ModInfo.json) | The mod's info (ID `portraits`) |
| [`Config/NewGameConfiguration.json`](Config/NewGameConfiguration.json) | Tells the game which portrait pictures to add |

This mod uses a **Data Asset** (not a Data Table), type **`NewGameConfiguration`**.

---

## 🖼️ The 5 pictures you need for one portrait

Each portrait is a **set of 5 pictures**. Use these exact sizes. They match the game's own portraits:

| # | Field | Size (pixels) | Example file name | Game's own folder (see in FModel) |
|---|---|---|---|---|
| 1 | `protagonist…Avatar` | **102 × 103** | `T_Portrait_Test01_Head` | `Art/UI/GameMain/Character/New_Head` |
| 2 | `half_Protagonist…Avatar` | **630 × 580** | `T_Portrait_Test01_Banshen` | `Art/UI/GameMain/Character/HalfBody` (`W_Banshen_…`) |
| 3 | `half_Tour…Avatar` | **1536 × 1053** | `T_Portrait_Test01_Danren` | `Art/UI/GameMain/Character/HalfBody` (`W_Danren_…`) |
| 4 | `small_Tour…Avatar` | **239 × 860** | `T_Portrait_Test01_Wuren` | `Art/UI/GameMain/Character/HalfBody` (`W_Wuren_…`) |
| 5 | `half_Protagonist…CenterAvatar` | **418 × 378** | `T_Portrait_Test01_Zhuangbei` | `Art/UI/GameMain/Character/CenterHalfBody` |

**Tip:** Export one of the game's portraits with FModel and use it as a template so your framing matches. See [FModel → File index](../../../FModel/3-FileIndex.md#-portraits--character-pictures).

---

## 🪜 Step by step

### Step 1 – Create the mod
1. **Tools → Modding → Create Mod**, then name it `portraits` (or your own name, no spaces).
2. Make a `Textures` folder and a `Config` folder inside it.

### Step 2 – Import your pictures
1. Save your 5 pictures as `.png` at the sizes above.
2. Drag them into `Content/Mods/portraits/Textures/`.
3. Double-click each one and set **Texture Group** to **UI** and **Compression** to **UserInterface2D**, so they stay sharp.
4. Save.

### Step 3 – Create the New Game data asset
1. In `Config/`, right-click → **Miscellaneous → Data Asset**.
2. Pick **`ModNewGameConfigAsset`**.
3. Name it (example: `DA_NewGamePortraits`) and open it.

### Step 4 – Add your pictures to the lists
There are **two sets** of lists, one for **Female** and one for **Male** players:

| List | Put picture # |
|---|---|
| Protagonist Female Avatar / Protagonist Male Avatar | 1 (head) |
| Half Protagonist Female Avatar / Half Protagonist Male Avatar | 2 |
| Half Tour Female Avatar / Half Tour Male Avatar | 3 |
| Small Tour Female Avatar / Small Tour Male Avatar | 4 |
| Half Protagonist Female Center Avatar / … Male Center Avatar | 5 |

1. Click **+** on each list and pick your picture.
2. Want it for only one gender? Fill in only that gender's lists.
3. Adding several portraits? Add them **in the same order in every list**, so portrait #2 uses picture #2 in each list.
4. **Leave every other field at 0 or empty.** Those control starting skills, money, and unlocks. Zero means "don't change".
5. Save.

> The example adds the **same** portrait for both female and male. See [`NewGameConfiguration.json`](Config/NewGameConfiguration.json).

### Step 5 – Link it
1. Open `DA_ModDataAsset` in your mod folder.
2. Under **Data Assets**, click **+**.
3. **Asset Type:** `NewGameConfiguration`. **Asset:** your `DA_NewGamePortraits`.
4. Save.

### Step 6 – Mod Info, package, test
1. **Mod Info Editor:** fill in the info and tick **NewGameLoad**.
2. **Package Mod**, then copy it to the game → [How to package and test](../../2-HowToUse.md#5-package-your-mod).
3. Enable the mod, start a **new game**, and look through the portraits. Yours should be there. 🎉

---

## 🛠 Problems

| Problem | Fix |
|---|---|
| Portrait doesn't show | Did you start a **new** game? Is **NewGameLoad** ticked? |
| Picture is stretched or cut off | Check it's the exact size in the table. |
| Picture is blurry | Set Compression to **UserInterface2D** and Texture Group to **UI**. |
| Wrong picture shows in one spot | Your lists are in a different order. Make every list the same order. |

[⬅ Back to Unreal Engine](../../README.md)
