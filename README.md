# LocalTweaks

Personal XML tweaks for a RimWorld 1.7 mod list. Fixes that only paper over another mod's bug are written as
conditionals that retire themselves once that mod is fixed.

## Tweaks

| File | Mod | Change |
|---|---|---|
| `Patches/VQEA_DeconstructibleTubes.xml` | Vanilla Quests Expanded - Ancients | Decorative pneumatic tubes in vaults can be deconstructed (launch port and termini left alone, they have code behind them) |
| `Patches/ReGrowth_RemovedPlants.xml` | Cyanobot's Plant Gen Patches + Biomes! Oasis | Drops `RG_Plant_JoshuaTree` / `RG_Plant_WingCactus` from biome wild plants while ReGrowth 2 keeps those defs commented out |
| `Patches/ConsistentText_UraniumRecipe.xml` | Consistent Text | Restores the Alpha Animals refinery recipe label (`AA_ExtractUranium`) its patch deletes |
| `Patches/AlphaGenes_WretchBlacklist_CherryPicked.xml` | Alpha Genes + Cherry Picker | Removes the cherry-picked `AG_DecreasedCommandRange` gene from the random-mutation blacklist (load error "Could not load reference ... AG_DecreasedCommandRange") |
| `Patches/FlourishEveryday_FloorDrawNoHands.xml` | Flourish - Everyday Animations + Show Me Your Tools | Children's floor drawing: Flourish hand tracks and body-lowering track removed, so only Show Me Your Tools' crayon and hands are drawn and line up |
| `Patches/FlourishEveryday_TelescopeMirror.xml` | Flourish - Everyday Animations | Telescope pose mirrored so the pawn stands on the eyepiece side, facing East |
| `Patches/ShowMeYourTools_NoTelescopeSpyglass.xml` | Show Me Your Tools | No floating handheld spyglass while using a telescope (kept for skygazing) |
| `Patches/HaulersDream_BatchCraftAnimations.xml` | Hauler's Dream | Batch crafting gets the same Flourish animations and Show Me Your Tools tools as a normal bill |
| `Patches/VeinMining_ChocolateJadeite.xml` | Alpha Biomes + Vanilla Landmarks Expanded | Chocolate and jadeite rock can be designated with "Mine vein" |

Load order: after VQE Ancients, Cyanobot's Plant Gen Patches, Consistent Text, Flourish Everyday, Alpha Biomes and Vanilla Landmarks Expanded (declared in `About/About.xml`).

Companion C# fixes: [Harmony3StrictCompat](https://github.com/hugalafutro/Harmony3StrictCompat).
