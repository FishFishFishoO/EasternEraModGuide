# FModel – 1. Setup

[⬅ Back to FModel](README.md) · Next: [2. How to use it ➡](2-HowToUse.md)

---

## 🧰 What you need

| Thing | Where to get it |
|---|---|
| Eastern Era installed | [Steam](https://store.steampowered.com/app/3446240/Eastern_Era/) |
| FModel | https://fmodel.app/ |
| .NET 8 Desktop Runtime (FModel needs it) | https://dotnet.microsoft.com/download/dotnet/8.0 → **.NET Desktop Runtime** → **Windows x64** |
| The mapping file (`.usmap`) | [Mappings folder](Mappings/README.md) |

### ❓ What's a mapping file?

Eastern Era uses **Unreal Engine 5**, which saves data **without the field names**. You'd see the numbers but not their labels, like "SightRadius".
The **mapping file** (`.usmap`) has those names, so FModel can put them back.

- **Without it:** files won't open or show errors.
- **With it:** everything reads normally.

---

## Step 1 – Download FModel
1. Go to **https://fmodel.app/** and click **Download**.
2. Right-click the ZIP → **Extract All…**
3. Put `FModel.exe` in **its own folder**, e.g. `C:\Modding\FModel\`. FModel makes its own files next to it.
4. Doesn't open? Install the **.NET 8 Desktop Runtime** (link above).

## Step 2 – Download the mapping file
1. Open the **[Mappings](Mappings/README.md)** folder.
2. Click the newest `.usmap` file.
3. Click **Download raw file** (the ⬇ button, top right of the file box).
4. Put it next to FModel, e.g. `C:\Modding\FModel\EasternEra-5.6.1-44394996.usmap`

## Step 3 – Add Eastern Era
The first time you open FModel, a **Directory Selector** window appears.

1. Double-click `FModel.exe`.
2. Click **Add undetected game** (you may need to click a small arrow to show it).
3. Fill in:
   - **Name:** `EasternEra`
   - **Directory:** your game folder, normally
     `C:\Program Files (x86)\Steam\steamapps\common\EasternEra`
     *(Not sure? In Steam, right-click Eastern Era → **Manage → Browse local files**, then copy the address bar.)*
4. Click **+** to add it.
5. Choose **EasternEra** in the top dropdown.
6. **UE Versions:** pick **`GAME_UE5_6`**.
7. Click **OK**.
8. Asked for an **AES key**? Leave it **empty**. Eastern Era's files aren't locked.

> Made a mistake? **Directory → Selector** opens this window again.

## Step 4 – Link the mapping file
1. Top menu: **Settings**. Stay on the **General** tab.
2. Find **Mapping** and tick **Local Mapping File**.
3. Next to **Mapping File Path**, click **…** and pick your `.usmap` file.
4. Check **Output Directory**. That's where exported files go. Change it if you want.
5. Click **OK**.
6. **Close and reopen FModel.**

✅ Done! Next: [2. How to use it ➡](2-HowToUse.md)

---

## 🛠 Problems

| Problem | Fix |
|---|---|
| FModel won't open | Install **.NET 8 Desktop Runtime (x64)**. |
| Files show errors or empty data | Mapping isn't linked. Redo Step 4 and **restart FModel**. |
| Broke after a game update | Mapping is out of date. Get a newer one from [Mappings](Mappings/README.md) or [make one with UE4SS](../UE4SS/README.md). |
| Junk text / version errors | **Directory → Selector**, set UE version to **`GAME_UE5_6`**. |
| Asks for an AES key | Leave it empty and click OK. |

[⬅ Back to FModel](README.md) · Next: [2. How to use it ➡](2-HowToUse.md)
