# Example: Character Mod (Lu Yuanning · 陆远宁)

[⬅ Back to Unreal Engine](../../README.md) · [Main page](../../../README.md)

This example adds **Lu Yuanning**, a 19-year-old archer you can recruit or pick when starting a new game.
It shows the **3 data tables** every character needs, plus portraits, stats, gear, and skills.

> 📦 This folder has the **settings files** (`.json`) so you can read and copy them.
> The model, textures, and portraits (`.uasset` files) are **not included**. You make or import your own in Unreal.

---

## 📁 Files in this example

| File | What it is |
|---|---|
| [`ModInfo.json`](ModInfo.json) | The mod's info (ID `archer_m`, name, version, which tables to load) |
| [`Config/CharacterAnatomyProfiles.json`](Config/CharacterAnatomyProfiles.json) | **Table 1: Body.** Which 3D model and materials the character uses |
| [`Config/CharacterAppearancePreset.json`](Config/CharacterAppearancePreset.json) | **Table 2: Appearance.** Gender, race, hair, face details |
| [`Config/CharacterConfig.json`](Config/CharacterConfig.json) | **Table 3: Character info.** Name, story, portraits, stats, weapon, armor, skills |

**How they connect:** all 3 tables use the same row name, **`archerm`**.

```
CharacterConfig "archerm"
   └─ customizationId: "archerm" ──► CharacterAppearancePreset "archerm"
                                         └─ anatomy ──► CharacterAnatomyProfiles row (the body)
```

---

## 🪜 How to make your own character (step by step)

### Step 1 – Create the mod
1. **Tools → Modding → Create Mod**, then name it (no spaces), e.g. `archer_m`.
2. Make these folders inside `Content/Mods/archer_m/`:
   - `Config` (data tables)
   - `UI` (portraits)
   - `Art` (model, textures)

### Step 2 – Import the model
1. Import your character as a **Skeletal Mesh** (drag the `.fbx` into `Art/`).
2. In the import window, tick **Use Existing Skeleton** and pick:
   `Content/Art/Animations/Characters/Mannequins/Meshes/SK_Mannequin` (the **Skeleton** asset).

   ⚠️ Playable humans **must** use this skeleton, or animations and gear break.
   Official guide: [Model Import & Skeleton Matching](https://github.com/L1ngan/EasternEraMod/blob/main/Docs/en-US/ModelImportAndSkeletonMatching.md)

### Step 3 – Make the portraits
Make **5 pictures** at these sizes and import them into `UI/`:

| Field in CharacterConfig | Size (pixels) | Where it shows | Lu Yuanning's file |
|---|---|---|---|
| `avatar` | **102 × 103** | Small round head icon | `Lu_Avatar` |
| `half_Avatar` | **630 × 580** | Half-body picture | `Lu_HalfAvatar` |
| `half_TourAvatar` | **1536 × 1053** | Large half-body picture | `Lu_HalfTourAvatar` |
| `smallTourAvatar` | **239 × 860** | Tall narrow picture | `Lu_SmallTourAvatar` |
| `half_UIAvatar` | **418 × 378** | Center UI picture | `Lu_HalfUIAvatar` |

### Step 4 – Create the 3 data tables
In `Config/`, right-click → **Miscellaneous → Data Table**, and pick the row type:

| Table | Row type to pick | Mod Config Type |
|---|---|---|
| CharacterAnatomyProfiles | `FAnatomyProfile_V10` | `CharacterAnatomyProfiles` |
| CharacterAppearancePreset | `FCustomizationProfile_V10` | `CharacterAppearancePreset` |
| CharacterConfig | `ModHumanData` | `CharacterConfig` |

Add **one row** to each and give all 3 the **same row name** (e.g. `archerm`).

### Step 5 – Fill in Table 1: Body (CharacterAnatomyProfiles)
- **Body → Mesh:** your skeletal mesh.
- **Anim Instance Class:** `BPA_CharacterAnimation_Template` (same as the example).
- Use **one combined body model** (recommended), not a separate head and body.

### Step 6 – Fill in Table 2: Appearance (CharacterAppearancePreset)
| Field | Lu Yuanning | Notes |
|---|---|---|
| Name | `archerm` | Same as the row name |
| Anatomy | `ERWMaleAdult` | Male adult body type |
| Race | `Human` | Only Human works right now |
| Gender | `Male` | Male or Female |
| Generation | `Adult` | Only Adult works right now |

### Step 7 – Fill in Table 3: Character info (CharacterConfig)
The important fields (open [`CharacterConfig.json`](Config/CharacterConfig.json) to see them all):

| Field | Lu Yuanning | What it does |
|---|---|---|
| `iD` | `archerm` | **Must match the row name** |
| `templateId` | `PlayerCharacter` | Fills in anything you leave blank. **Don't change it.** |
| `customizationId` | `archerm` | Row name in Table 2 |
| `characterFirstName` / `characterName` | 陆 / 远宁 | Family name / given name. Fill in **both**. |
| `sex` / `age` | `true` / `19` | `true` = male, `false` = female |
| `height` / `weight` | 178 / 145 | |
| `backgroundStory` | *(text)* | Shown in the character's details |
| `refuseText` / `acceptText` / `joinText` | *(text)* | What they say when recruiting fails, starts, and succeeds |
| `bCanChooseNewGame` | `true` | Lets players pick them when starting a new game |
| `initWeapon` | `Bow_A_YeHu` | Starting weapon (an item ID from the game) |
| `initArmor` | helmet / armor / pants / shoes | Starting gear, e.g. `Armor_Lv_03_Purple` |
| `initInternalStrength` / `initMoves` | `S_QiJueJing_Internal`, … | Starting martial arts |
| `initCharacteristicIds` | `Characteristic_S_1011`, … | Starting traits |
| `attributes` | *(long list)* | All stats: health per body part, skills, attack, speed… |

**Gear name pattern:**
- Weapons: `Sword` / `Spear` / `Bow` / `Fist` + level + quality
- Armor: `Armor_Lv_0x_Quality`, `Pants_Lv_0x_Quality`, `Shoes_Lv_0x_Quality` (x = 1–4)
- Quality: `Green` → `Blue` → `Purple` → `Orange` → `Golden`

Find real item, trait, and skill IDs with FModel: [File index](../../../FModel/3-FileIndex.md).

⚠️ **Attributes tip:** body-part health comes in 3 groups that must match: `maxBody` / `body` / `curBody`, `maxHead` / `head` / `curMaxHead`, and so on. If you change one, change all three.

### Step 8 – Link the tables
1. Open `DA_ModDataAsset` in your mod folder.
2. Add 3 rows under **Data Tables**, one per table, each with its matching **Mod Config Type** (see Step 4).
3. Save everything.

### Step 9 – Mod Info, package, test
1. **Mod Info Editor:** fill in the info, and tick **NewGameLoad** (characters load when starting a new game).
2. **Package Mod**, then copy it to the game → [How to package and test](../../2-HowToUse.md#5-package-your-mod).
3. Start a **new game**. Your character should be on the character select screen. 🎉

---

## 📚 More help
- Official guide: [Character Configuration](https://github.com/L1ngan/EasternEraMod/blob/main/Docs/en-US/CharacterConfiguration.md)
- Official example: [ParagonSunWukong](https://github.com/L1ngan/EasternEraMod/blob/main/BlueprintAPI_ModAuthors/Examples/ParagonSunWukong/README.md)

[⬅ Back to Unreal Engine](../../README.md)
