# Unreal Engine – 2. How to Use It

[⬅ 1. Setup](1-Setup.md) · [Back to main page](../README.md)

---

## 📋 Contents

1. [Create a mod](#1-create-a-mod)
2. [Fill in Mod Info](#2-fill-in-mod-info)
3. [What goes in a mod folder](#3-what-goes-in-a-mod-folder)
4. [Link your data tables](#4-link-your-data-tables)
5. [Package your mod](#5-package-your-mod)
6. [Test it in the game](#6-test-it-in-the-game)
7. [Publish to Steam Workshop](#7-publish-to-steam-workshop)
8. [Problems](#-problems)

---

## 1. Create a mod

1. Open the Mod Kit (`EasternEra.uproject`).
2. Top menu: **Tools → Modding → Create Mod**.
3. Type a name with **no spaces** (example: `MyFirstMod`).
4. Your mod is now at: `Content/Mods/MyFirstMod/`

   ⚠️ A mod must be **directly** inside `Content/Mods/`. `Content/Mods/MyFirstMod/SubFolder` won't work.

## 2. Fill in Mod Info

1. **Tools → Modding → Mod Info Editor**.
2. Pick your mod folder (`Content/Mods/MyFirstMod`).
3. Fill in:

| Field | What to type |
|---|---|
| **ModId** | A unique name. Letters/numbers only, no spaces. Never change it after you publish. |
| **ModName** | The name players see |
| **Version** | Start with `1.0.0`. Raise it every update. |
| **Author** | Your name |
| **Description** | What your mod does |
| **Icon** | A `.png` picture in your mod folder (optional) |
| **NewGameLoad** | Tick it if your mod only works when starting a **new** game (characters, portraits) |

4. Click **Save**.

## 3. What goes in a mod folder

```
MyFirstMod/
├── ModInfo.json        ← mod's info (made by the Mod Info Editor)
├── DA_ModDataAsset     ← lists your data tables (made by Create Mod)
├── Main.lua            ← optional script
├── Config/             ← your data tables (characters, items, stats…)
├── UI/                 ← portraits and icons
└── Art/                ← models, textures, materials
```

## 4. Link your data tables

Most mods change the game's **data tables** (lists of characters, items, animals…).

1. Open **`DA_ModDataAsset`** in your mod folder (double-click it).
2. Under **Data Tables**, click **+** to add a row.
3. Set **Mod Config Type** (example: `CharacterConfig`).
4. Set **Data Table** to your table inside `Config/`.
5. Save.

⚠️ The table's **row type must match** the Mod Config Type, or the game won't read it.
See the [character example](Examples/CharacterMod_LuYuanning/README.md) for a full walk-through.

**Tip:** Use [FModel](../FModel/2-HowToUse.md) to look at the game's original tables and copy their IDs and values.

## 5. Package your mod

1. **Tools → Modding → Package Mod**.
2. Tick your mod.
3. Click **Package**. It may "Cook" first. That's normal and can take a while.
4. When it's done, your finished mod is in:
   `<Mod Kit folder>\Mods\<YourModId>\`

## 6. Test it in the game

1. Open `<Mod Kit folder>\Mods\` and copy the **whole** `<YourModId>` folder.
2. Open your game folder. In Steam: right-click **Eastern Era** → **Manage → Browse local files**.
3. Go into `EasternEra\Content\` and open or create a folder called **`Mods`**.
4. Paste your mod folder there. It should look like:
   ```
   steamapps\common\EasternEra\EasternEra\Content\Mods\<YourModId>\
       <YourModId>.pak
       ModInfo.json
       ...
   ```
   ⚠️ It must be in **`Content\Mods`**, not `EasternEra\Mods`.
5. Start the game → **Workshop / Mods** → **Local Mods** tab → **enable** your mod.
6. To check it loaded, open the in-game console and type `Mod.Status`.

## 7. Publish to Steam Workshop

1. Use the Workshop upload tool in the game.
2. Fill in the title, description, preview image, and visibility.
3. For updates: raise the **Version** (e.g. `1.0.0` → `1.0.1`), package again, upload, and write change notes.

---

## 🛠 Problems

| Problem | Fix |
|---|---|
| Mod not in the Local Mods list | Folder must be `Content\Mods\<ModId>\`. |
| Packaging error about the mod path | Mod must be directly in `Content/Mods/<ModName>/`. |
| Mod loads but nothing changes | Check `DA_ModDataAsset` links the right tables with the right Mod Config Type. |
| My Lua messages don't show | Released games hide normal logs. Use `Warning` or `Error` level. |
| Lua script errors | Only the one Lua file in `MainLuaFile` loads. `require`, `io`, and `os` are blocked. |
| JSON error | The log gives the line number. Paste the file into https://jsonlint.com to find the typo. |

**More detail:** [official docs](https://github.com/L1ngan/EasternEraMod/blob/main/Docs/en-US/ModDocumentationIndex.md) · [official developer guide](https://github.com/L1ngan/EasternEraMod/blob/main/BlueprintAPI_ModAuthors/Examples/ModDevelopmentGuide_EN.md)

---

[⬅ 1. Setup](1-Setup.md) · [Back to main page](../README.md)
