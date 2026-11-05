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
| `Patches/Gulden_CapricornHorseMeat.xml` | Gulden Biome (Continued) | Capricorns butcher into vanilla horse meat, so "horse meat" no longer shows twice (old saves: rename `Meat_Gulden_Animal_Capricorn` to `Meat_Horse`) |
| `Patches/BiomesCaverns_SingleNogtyl.xml` | Biomes! Caverns | Only one "nogtyl" in the plant menu: the cave copy (`BMT_Nogtyl`) is no longer sowable, the marsh one (`BMT_NogtylMarsh`) is; wild growth unchanged |
| `Patches/VFE_ErgonomicChairReplacesChairs.xml` | Vanilla Furniture Expanded | The ergonomic chair gets the `Chair` replace tag, so it can be placed directly over existing chairs and stools (with Replace Stuff it swaps in place) |

Load order: after VQE Ancients, Cyanobot's Plant Gen Patches, Consistent Text, Flourish Everyday, Alpha Biomes, Vanilla Landmarks Expanded, Gulden Biome, Biomes! Caverns and Vanilla Furniture Expanded (declared in `About/About.xml`).

Companion C# fixes: [Harmony3StrictCompat](https://github.com/hugalafutro/Harmony3StrictCompat).
