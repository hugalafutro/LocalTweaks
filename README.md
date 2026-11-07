# LocalTweaks

Personal XML tweaks for a RimWorld 1.7 mod list. Fixes that only paper over another mod's bug are written as
conditionals that retire themselves once that mod is fixed.

## Tweaks

| File | Mod | Change |
|---|---|---|
| `Patches/VeinMining_ChocolateJadeite.xml` | Alpha Biomes + Vanilla Landmarks Expanded | Chocolate and jadeite rock can be designated with "Mine vein" |
| `Patches/AlphaGenes_WretchBlacklist_CherryPicked.xml` | Alpha Genes + Cherry Picker | Removes the cherry-picked `AG_DecreasedCommandRange` gene from the random-mutation blacklist (load error "Could not load reference ... AG_DecreasedCommandRange") |
| `Patches/BiomesCaverns_SingleNogtyl.xml` | Biomes! Caverns | Only one "nogtyl" in the plant menu: the cave copy (`BMT_Nogtyl`) is no longer sowable, the marsh one (`BMT_NogtylMarsh`) is; wild growth unchanged |
| `Patches/Blueprints_Waylith17_FernyCompat.xml`, `Defs/Blueprints_Waylith17_Tips.xml` | Blueprints - 1.7 Waylith (Unofficial) + Better Architect Menu / Loading Screen Repository | Those two only load their Blueprints extras for the old `defi.blueprints.fork`; same extras for the 1.7 fork: Blueprints tab nested under Colony, and the blueprint loading tip |
| `Patches/ConsistentText_UraniumRecipe.xml` | Consistent Text | Restores the Alpha Animals refinery recipe label (`AA_ExtractUranium`) its patch deletes |
| `Patches/TechLevel_KeepNeolithicBuildings.xml` | Core + Vanilla Factions Expanded - Tribals | Hoopstone ring, Game of Ur board and VFE Tribals' floor painting stay buildable after VFE Tribals advances the colony past Neolithic (their `maxTechLevelToBuild` cap removed) |
| `Patches/ReGrowth_RemovedPlants.xml` | Cyanobot's Plant Gen Patches + Biomes! Oasis | Drops `RG_Plant_JoshuaTree` / `RG_Plant_WingCactus` from biome wild plants while ReGrowth 2 keeps those defs commented out |
| `Patches/Buzzers_CompoundEyesTexture.xml` | Det's Xenotypes - Buzzers + VRE Insector | Buzzers' compound eyes (`DV_Eyes_Compound`) point at a texture no mod ships, so Buzzers had a magenta missing-texture square on the head; now drawn with VRE Insector's compound eyes. Only replaces the broken path, so it stops applying once Buzzers changes it |
| `Patches/FlourishEveryday_FloorDrawNoHands.xml` | Flourish - Everyday Animations + Show Me Your Tools | Children's floor drawing: Flourish hand tracks and body-lowering track removed, so only Show Me Your Tools' crayon and hands are drawn and line up |
| `Patches/Gulden_CapricornHorseMeat.xml` | Gulden Biome (Continued) | Capricorns butcher into vanilla horse meat, so "horse meat" no longer shows twice (old saves: rename `Meat_Gulden_Animal_Capricorn` to `Meat_Horse`) |
| `Patches/HaulersDream_BatchCraftAnimations.xml` | Hauler's Dream | Batch crafting gets the same Flourish animations and Show Me Your Tools tools as a normal bill |
| `Patches/Casino_TableGames.xml` | Hospitality: Casino + Det's Xenotypes - Boglegs + VFE Settlers | The tongo table and the vanilla billiards table become casino equipment like Casino's poker table: pricing gizmo, silver held and total earned. Tongo also becomes `Gamble` joy (as poker does); billiards stays `Gaming_Dexterity`. Both keep their own job drivers (tongo cards, billiards shots); the charge per game comes from Harmony3StrictCompat. The VFE Settlers faro table, which already plays with vanilla's poker driver, gets everything Casino gives the poker table: comp, `Gamble` joy and Casino's paying poker driver. Colonists play for free |
| `MorePhytokinXenotypes/` (`LoadFolders.xml`) | More Phytokin Xenotypes | With Anomaly + Odyssey + Starjack its `Modules/Odyssey` shadows six `Modules/Anomaly` def files with the same relative path (last load folder wins), so carrionkin / harbingerkin never load. Byte copies of the six files under other names, loaded only with all four mods; the patch there errors once a def exists twice (upstream fixed, delete the folder); Harmony3StrictCompat compares the copies against the upstream files at startup. Same method as workshop fix 3830670122 |
| `Patches/MSSFP_ExorcismGoldCount.xml` | MSS Flavour Pack | The exorcism operation costs 10 gold as its description says, not 100 (its `count` 10 was in volume units, and gold counts 0.1 per piece) |
| `Patches/ShowMeYourTools_NoTelescopeSpyglass.xml` | Show Me Your Tools | No floating handheld spyglass while using a telescope (kept for skygazing) |
| `Languages/English/Keyed/TweaksGalore_Fixes.xml` | Tweaks Galore | The "Trader available" alert no longer shows a literal `{0}` before the trader list (its code appends the list to the translated string instead of formatting it); same key without the placeholder, later-loaded keyed entries replace earlier ones |
| `Patches/VFE_ErgonomicChairReplacesChairs.xml` | Vanilla Furniture Expanded | The ergonomic chair gets the `Chair` replace tag, so it can be placed directly over existing chairs and stools (with Replace Stuff it swaps in place) |
| `Patches/VQEA_DeconstructibleTubes.xml` | Vanilla Quests Expanded - Ancients | Decorative pneumatic tubes in vaults can be deconstructed (launch port and termini left alone, they have code behind them) |

Load order: after VQE Ancients, Cyanobot's Plant Gen Patches, Consistent Text, Flourish Everyday, Alpha Biomes, Vanilla Landmarks Expanded, Gulden Biome, Biomes! Caverns, Vanilla Furniture Expanded, Det's Boglegs and Hospitality: Casino (declared in `About/About.xml`).

Companion C# fixes: [Harmony3StrictCompat](https://github.com/hugalafutro/Harmony3StrictCompat).
