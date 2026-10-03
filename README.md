# Eastern Era Modding Guide (Beginner Friendly)

A step-by-step guide to making your first mod for **Eastern Era**.
No experience needed. If you get stuck, open an [Issue](../../issues) and ask!

> This is a fan-made guide. It is not made by or affiliated with the Eastern Era developers.

---

## 📋 Table of Contents

1. [What you need](#-what-you-need)
2. [Step 1 – Install Unreal Engine 5.6](#step-1--install-unreal-engine-56)
3. [Step 2 – Get the official Mod Kit](#step-2--get-the-official-mod-kit)
4. [Step 3 – Open the Mod Kit in Unreal](#step-3--open-the-mod-kit-in-unreal)
5. [Step 4 – Create your first mod](#step-4--create-your-first-mod)
6. [Step 5 – Package your mod](#step-5--package-your-mod)
7. [Step 6 – Test your mod in the game](#step-6--test-your-mod-in-the-game)
8. [Step 7 – Publish to Steam Workshop](#step-7--publish-to-steam-workshop)
9. [Troubleshooting](#-troubleshooting)
10. [Useful links](#-useful-links)

---

## 🧰 What you need

| Thing | Why | Where to get it |
|---|---|---|
| Eastern Era (on Steam) | To test your mod | Steam |
| Epic Games Launcher | To install Unreal Engine | https://www.epicgames.com/store/download |
| Unreal Engine **5.6** (exact version!) | The Mod Kit only opens in 5.6 | Inside the Epic Games Launcher |
| Visual Studio 2022 *(only if Unreal asks to "rebuild modules")* | Compiles the project code | https://visualstudio.microsoft.com/ |
| About 100 GB of free disk space | Unreal is big | — |

---

## Step 1 – Install Unreal Engine 5.6

1. Install and open the **Epic Games Launcher**. Sign in (a free account is fine).
2. Click **Unreal Engine** on the left, then the **Library** tab at the top.
3. Click the **+** next to "Engine Versions".
4. Click the version number on the new slot and choose **5.6**.
5. Click **Install**. Wait (this can take an hour or more).

## Step 2 – Get the official Mod Kit

1. Download the official Eastern Era Mod Kit here: **`https://github.com/L1ngan/EasternEraMod`**
2. If it is a `.zip` file: right-click it → **Extract All…**
3. Move the extracted folder somewhere with a **short path and no spaces**, for example:
   `C:\Mods\EasternEraMod`
   (Long paths like `C:\Users\Me\Downloads\New Folder (3)\...` can cause Unreal errors.)

## Step 3 – Open the Mod Kit in Unreal

1. Open the Mod Kit folder.
2. Double-click **`EasternEra.uproject`**.
3. If a box says *"modules are missing or built with a different engine version — rebuild?"* click **Yes**.
   - This needs Visual Studio 2022 with the **"Game development with C++"** option installed.
4. The first open is **slow** (it compiles shaders). Let it finish — don't close it.

## Step 4 – Create your first mod

1. In the Unreal Editor top menu, click **Tools → Modding**.
2. Choose **Create Mod**. Give it a name with **no spaces** (example: `MyFirstMod`).
3. Your mod lives in: `Content/Mods/MyFirstMod/`
   - ⚠️ It must be **directly** inside `Content/Mods/`. Not in a sub-folder.
4. Open the **Mod Info Editor** and fill in:
   - **ModId** – unique name, letters only, no spaces (example: `MyFirstMod`)
   - **ModName** – the name players see
   - **Version** – start with `1.0.0`
   - **Author** and **Description**
5. Click **Save**.

### What can a mod contain?

```
MyFirstMod/
├── ModInfo.json      ← your mod's info (required)
├── Main.lua          ← optional script
├── Config/           ← optional JSON files that change game data
├── MyFirstMod.png    ← optional icon
└── MyFirstMod.pak    ← made for you when you package
```

**Easiest first mod:** use our ready-made **[Starter Mod](StarterMod/)**. It renames the Wolf King, changes one of its stats, and adds a hello message, so you can see your mod working right away.

You can also change numbers in the game (like animal stats) using a JSON file in `Config/`.
Look at the example mods included in the Mod Kit (`BlueprintAPI_ModAuthors/Examples/`), such as **ChangeAttribute** and **ChangeNumberOfCharacters**.

## Step 5 – Package your mod

1. **Tools → Modding → Package Mod**.
2. Tick your mod and click **Package**. (It may "Cook" first — that's normal and can take a while.)
3. When finished, your packaged mod is in:
   `<Mod Kit folder>\Mods\<YourModId>\`

## Step 6 – Test your mod in the game

1. Copy the whole `Mods\<YourModId>\` folder.
2. Paste it into your game folder here:
   `...\Steam\steamapps\common\EasternEra\EasternEra\Content\Mods\<YourModId>\`
   - Tip: In Steam, right-click Eastern Era → **Manage → Browse local files** to find the game folder.
   - ⚠️ It must be inside **`Content\Mods`**. If the `Mods` folder doesn't exist, create it.
3. Start the game → **Workshop / Mods** menu → **Local Mods** tab → **enable** your mod.
4. To check it loaded, open the in-game console and type: `Mod.Status`

## Step 7 – Publish to Steam Workshop

1. Use the Workshop upload tools in the game/editor.
2. Fill in the title, description, preview image, and visibility.
3. Each time you update, raise the **Version** number (e.g. `1.0.0` → `1.0.1`) and write change notes.

---

## 🛠 Troubleshooting

| Problem | Fix |
|---|---|
| "Wrong engine version" | You must use Unreal **5.6** exactly. |
| Mod doesn't show up in game | Check the folder is `Content\Mods\<ModId>\`, not `EasternEra\Mods\`. |
| Packaging error about the mod path | Your mod must be directly in `Content/Mods/<ModName>/`, not a sub-folder. |
| My Lua script does nothing | Only the one file named in `MainLuaFile` (default `Main.lua`) is loaded. `require`, `io`, and `os` are not allowed. |
| My messages don't show in the log | Release builds hide normal logs. Use `Warning` or `Error` level. |
| JSON error | The log tells you the line and column. Paste your JSON into https://jsonlint.com to find the typo. |

---

## 🔗 Useful links

- Official Mod Kit: `[https://github.com/L1ngan/EasternEraMod)]
- Mod Kit docs (inside the kit): `Docs/en-US/ModDocumentationIndex.md`
- Full developer guide (inside the kit): `BlueprintAPI_ModAuthors/Examples/ModDevelopmentGuide_EN.md`
- Eastern Era on Steam: `PUT STEAM LINK HERE`
- Community Discord: `PUT DISCORD LINK HERE (or delete this line)`

---

## 🤝 Contributing

Found a mistake or know a better way? You can help:
- Open an **Issue** to report a problem or ask a question.
- Or click the ✏️ pencil icon on this page to suggest an edit.

## 📄 License

This guide is shared under the [MIT License](LICENSE).
The Eastern Era game and the official Mod Kit belong to their developers.
