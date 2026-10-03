# FModel – 3. File Index

[⬅ 2. How to use it](2-HowToUse.md) · [Back to FModel](README.md)

Where to find the important files in FModel.
All paths start from **`EasternEra/Content/`**. In mod files, `/Game/` means the same thing.

> Based on game build **44394996**. Paths can change after updates.

---

## 📋 Contents
- [Characters (humans)](#-characters-humans)
- [Animals & monsters](#-animals--monsters)
- [Traits & buffs](#-traits--buffs)
- [Weapons, armor & equipment](#️-weapons-armor--equipment)
- [Items & crafting](#-items--crafting)
- [Martial arts & skills](#-martial-arts--skills)
- [Buildings & technology](#️-buildings--technology)
- [New game settings](#-new-game-settings)
- [Portraits & character pictures](#-portraits--character-pictures)
- [World, events & dialogue](#-world-events--dialogue)
- [Animations & skeleton](#-animations--skeleton)

---

## 👤 Characters (humans)

| File | What's in it |
|---|---|
| `Configs/Character/DefaultHuman/DT_HumanData` | All human characters: names, stats, gear, skills. The `PlayerCharacter` row is the template. |
| `Configs/Character/DefaultHuman/DT_PresetCustomizationProfiles_V10` | Appearance presets (gender, hair, face) |
| `Configs/Character/DT_AnatomyProfiles_V10` | Body types, e.g. `ERWMaleAdult` |
| `Configs/Character/DT_CharacterPresetConfig` | Preset characters and their starting gear and skills |
| `Configs/Character/DT_CharacterName` / `DT_CharacterFirstName` | Random name lists |
| `Configs/Character/DT_CharacterAvatarConfig` | Character portrait settings |
| `Configs/CharacterAttribute/DT_CharacterAttributeInfo` | What each stat (attribute) means |
| `Configs/Character/Organ/DT_CharacterOrganConfig` | Body parts |
| `Configs/SpawnerConfig/DT_RandomDiscipleConfig` | Random recruitable disciples |
| `CharacterEditor/CharacterParts/DataAssets/` | Hairstyles and other character parts |

## 🐺 Animals & monsters

| File | What's in it |
|---|---|
| `Configs/Character/DT_AnimalData` | All animals and monsters (134 rows). **`10000` = Wolf King** |
| `Configs/Character/DT_SummonsData` | Summoned creatures |
| `Configs/Character/DT_AnimalCultivationConfig` | Animal growth and training |
| `Configs/GOAP/DT_AnimalActionAbility` | Animal behaviours (idle, sleep…) |
| `Configs/GameAbility/DT_GameAbilityInfo` | Attacks and abilities (for animals too) |
| `Configs/SpawnerConfig/DT_SpawnAnimalConfig_1` / `_2` / `_3` / `_WolfKing` | Where and how animals spawn |
| `Configs/SpawnerConfig/DT_MonsterGenerationConfig` | Monster spawning |

## ✨ Traits & buffs

| File | What's in it |
|---|---|
| `Configs/Character/DT_CharacteristicInfo` | **All traits**, e.g. `Characteristic_S_1011`, `Training_Orange_028` |
| `Configs/Character/DT_CommonBuff` | Buffs and effects |
| `Configs/Character/DT_BuffTagInfo` | Buff categories |
| `Configs/Character/DT_HobbyConfig` *(in DefaultHuman)* | Hobbies |

## ⚔️ Weapons, armor & equipment

| File | What's in it |
|---|---|
| `Configs/Weapon/DT_Weapon` | **All weapons**, e.g. `Bow_A_YeHu` |
| `Configs/Weapon/DT_Tool` | Tools |
| `Configs/Equipment/DT_CharacterApparelEquipment` | **Armor, pants, shoes, pendants**, e.g. `Armor_Lv_03_Purple` |
| `Configs/EquipmentAttribute/DT_EquipmentAttribute` | Equipment stats |
| `Configs/Fabricate/DT_EquipmentQualityRange` | Quality tiers (Green → Golden) |
| `Configs/Fabricate/DT_GenerateEquipmentData` | Random equipment generation |

## 🎒 Items & crafting

| File | What's in it |
|---|---|
| `Configs/Inventory/DT_InventoryItem` | **All items** |
| `Configs/Inventory/DT_ItemClassify` | Item categories |
| `Configs/Inventory/Consumable/DT_ConsumableData` | Food, potions, consumables |
| `Configs/Fabricate/DT_FormulaData` | Crafting recipes |
| `Configs/Collector/DT_DropItemConfig` | Loot drops |

## 🥋 Martial arts & skills

| File | What's in it |
|---|---|
| `Configs/MartialArts/DT_MartialArtsBookData` | **All martial arts**, e.g. `S_QiJueJing_Internal`, `C_JinZhong_Moves` |
| `Configs/MartialArts/DT_MartialArtsBookCategory` | Martial arts categories |
| `Configs/MartialArts/DT_MartialArtsEntries` | Martial arts effects |
| `Configs/MartialArts/DT_RealmData` | Cultivation realms |
| `Configs/BreakThrough/DT_SkillPoolConfig` | Skill pools for breakthroughs |

## 🏗️ Buildings & technology

| File | What's in it |
|---|---|
| `Configs/Build/DT_Buildconfig` | **All buildings** |
| `Configs/Build/DT_RoomConfigData` | Rooms |
| `Configs/Technology/DT_TechnologyConfig` | Technology tree |
| `Configs/Technology/DT_TechUnlockItemConig` | What each technology unlocks |

## 🆕 New game settings

| File | What's in it |
|---|---|
| `Configs/NewGameConfigAsset` | **New-game setup**: player portraits, starting points, unlocks. The [portrait example](../UnrealEngine/Examples/NewGamePortraits/README.md) adds to this. |
| `Configs/DA_WorldGameConfigurationAsset` | World settings |
| `Configs/StoryBackground/DT_StoryBackground` | Starting backstories |

## 🖼️ Portraits & character pictures

All in `Art/UI/GameMain/Character/`:

| Folder | Pictures | Size (pixels) |
|---|---|---|
| `New_Head/` | Head icons (`W_093`, …) | **102 × 103** |
| `HalfBody/` → `W_Banshen_…` | Half-body | **630 × 580** |
| `HalfBody/` → `W_Danren_…` | Large half-body | **1536 × 1053** |
| `HalfBody/` → `W_Wuren_…` | Tall narrow | **239 × 860** |
| `CenterHalfBody/` → `T_Zhuangbei_…` | Center UI | **418 × 378** |

Other UI pictures are in `Art/UI/` (icons, menus, martial arts, buildings…).

## 🌍 World, events & dialogue

| File | What's in it |
|---|---|
| `Configs/WorldSystem/DT_WorldPlaceInfoConfig` | Places on the world map |
| `Configs/WorldSystem/DT_WorldForceInfoConfig` | Factions |
| `Configs/WorldSystem/WorldEvent/DT_WorldEventInfoConfig` | World events |
| `Configs/Emergence/DT_EmergentEventConfig` | Random events |
| `Configs/Dialogue/DT_DialogueInfo` / `DT_DialogueOption` | Dialogue lines and choices |
| `Configs/Task/DT_CommonTaskCondition` | Quest conditions |
| `Configs/StringTable/` | **All game text** (Chinese + English) |

## 🏃 Animations & skeleton

| File | What's in it |
|---|---|
| `Art/Animations/Characters/Mannequins/Meshes/SK_Mannequin` | **The human skeleton.** Character models must use it. |
| `Art/Animations/CloseCombat/AM_Death` | Default death animation |
| `Art/Animations/Hit/` | Hit reactions (`HitBody_F/L/R/B_Montage`) |
| `Blueprints/Character/Animation/BPA_CharacterAnimation_Template` | Character animation blueprint |

---

Found something useful that's missing? Open an **Issue** or suggest an edit!

[⬅ 2. How to use it](2-HowToUse.md) · [Back to FModel](README.md)
