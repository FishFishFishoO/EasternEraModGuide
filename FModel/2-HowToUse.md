# FModel – 2. How to Use It

[⬅ 1. Setup](1-Setup.md) · [Back to FModel](README.md) · Next: [3. File index ➡](3-FileIndex.md)

---

## Step 1 – Load the game files
1. Top menu: **Directory → Archives** (or the **Archives** tab on the left).
2. You'll see files like `pakchunk0-Windows.pak`, `pakchunk101-Windows.pak`, …
3. Click one, then press **Ctrl + A** to select all.
4. Click **Load**.
5. Wait for the bottom bar to finish. `pakchunk0` is about **5 GB**, so be patient.
6. Click the **Folders** tab. You'll see `EasternEra` → `Content` → …

## Step 2 – Find things

### Browse
- Double-click folders to open them.
- Double-click a file to view it. The data shows on the right as text.

### Search (faster!)
1. Press **Ctrl + Shift + F** (or **Packages → Search**).
2. Type part of a name, like `DT_AnimalData` or `DT_Weapon`.
3. Double-click a result to open it.
4. Right-click a result → **Go To** to see its folder.

Not sure what to search for? See the **[File index](3-FileIndex.md)**.

## Step 3 – Read a DataTable

**DataTables** (names start with `DT_`) are lists. Each **row** is one thing: one animal, one item, one skill.

Example: `Configs/Character/DT_AnimalData`, row `10000` (the Wolf King):

```json
"Rows": {
  "10000": {
    "ID": "10000",
    "CharacterName": { "LocalizedString": "Wolf King", ... },
    "SightRadius": 1250.0,
    ...
  }
}
```

| What you see | What it means for your mod |
|---|---|
| `"10000"` | The **row name / ID**. Use it in your mod. |
| `SightRadius`, … | **Field names**. Use the same names in your mod's tables. |
| `1250.0` | The **original value**. Write it down before you change it! |
| `"LocalizedString": "Wolf King"` | The English name shown in game |

**Tip:** Press **Ctrl + F** in the text view to search inside the file.

## Step 4 – Export (save) things

Right-click a file:

| Option | You get |
|---|---|
| **Save Properties (.json)** | The data as a text file. Best for DataTables. |
| **Save Texture** | Pictures and icons as `.png` |
| **Save Model** | 3D models (open in Blender) |
| **Export Raw Data (.uasset)** | The original file (rarely needed) |

Files go to your **Output Directory** (Settings → General).

> 📌 The game's files belong to the developers. Use them to **learn and as a reference**. Don't re-upload the game's art, models, or files.

---

## 💡 Useful tricks

- **Find where an ID is used:** search with **Packages → Search**, or export the `Configs` folder (right-click → **Save Folder's Packages Properties (.json)**). Then search the `.json` files on your PC with Notepad++ or VS Code (**Find in Files**).
- **Copy a portrait's size:** open a texture and the size shows at the bottom of the preview.
- **English names:** text fields show `SourceString` (Chinese) and `LocalizedString` (English).

[⬅ 1. Setup](1-Setup.md) · [Back to FModel](README.md) · Next: [3. File index ➡](3-FileIndex.md)
