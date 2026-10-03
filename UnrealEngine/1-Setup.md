# Unreal Engine – 1. Setup

[⬅ Back to main page](../README.md) · Next: [2. How to use it ➡](2-HowToUse.md)

---

## 🧰 What you need

| Thing | Why | Where to get it |
|---|---|---|
| Eastern Era | To test your mods | [Steam](https://store.steampowered.com/app/3446240/Eastern_Era/) |
| Epic Games Launcher | Installs Unreal Engine | https://www.unrealengine.com/download |
| Unreal Engine **5.6** (exact version!) | The Mod Kit only opens in 5.6 | Inside the Epic Games Launcher |
| Visual Studio 2022 *(only if Unreal asks to "rebuild")* | Compiles the project code | https://visualstudio.microsoft.com/ |
| About **100 GB** free disk space | Unreal is big | — |

---

## Step 1 – Install the Epic Games Launcher

1. Go to **https://www.unrealengine.com/download**.
2. Click **Download** and run the installer.
3. Open the **Epic Games Launcher** and sign in (a free account is fine).

## Step 2 – Install Unreal Engine 5.6

1. In the launcher, click **Unreal Engine** on the left.
2. Click the **Library** tab at the top.
3. Click the **+** next to **Engine Versions**.
4. Click the version number on the new slot and choose **5.6**.
5. Click **Install**. Wait. This can take an hour or more.

## Step 3 – Download the official Mod Kit

1. Go to **https://github.com/L1ngan/EasternEraMod/tree/main**.
2. Click the green **Code** button → **Download ZIP**.
3. Right-click the ZIP → **Extract All…**
4. Move the extracted folder somewhere with a **short path and no spaces**, for example:
   `C:\Mods\EasternEraMod`

   ⚠️ Long paths like `C:\Users\Me\Downloads\New Folder (3)\...` cause Unreal errors.

## Step 4 – Open the Mod Kit

1. Open the Mod Kit folder.
2. Double-click **`EasternEra.uproject`**.
3. If it asks which engine to use, pick **5.6**.
4. If a box says *"modules are missing or built with a different engine version. Rebuild?"*, click **Yes**.
   - This needs **Visual Studio 2022** with the **"Game development with C++"** option ticked in its installer.
5. The first open is **slow** (it compiles shaders). Let it finish. Don't close it.

## Step 5 – Check it worked

1. In the Unreal top menu, click **Tools**.
2. You should see **Modding** in the list. ✅ You're ready!

---

## 🛠 Problems

| Problem | Fix |
|---|---|
| "Wrong engine version" | Use Unreal **5.6** exactly. |
| "Modules missing… rebuild?" then it fails | Install Visual Studio 2022 with **Game development with C++**, then try again. |
| No **Modding** in the Tools menu | The Mod Kit didn't load fully. Close Unreal and reopen `EasternEra.uproject`. |
| Unreal crashes on open | Move the Mod Kit to a short path like `C:\Mods\EasternEraMod`. |

---

[⬅ Back to main page](../README.md) · Next: [2. How to use it ➡](2-HowToUse.md)
