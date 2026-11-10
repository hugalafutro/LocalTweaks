# LocalTweaks

Personal XML tweaks for a RimWorld 1.7 mod list. Fixes that only paper over another mod's bug are written as
conditionals that retire themselves once that mod is fixed.

## Tweaks

| File | Mod | Change |
|---|---|---|
| `Patches/VeinMining_ChocolateJadeite.xml` | Alpha Biomes + Vanilla Landmarks Expanded | Chocolate and jadeite rock can be designated with "Mine vein" |
| `Patches/AlphaGenes_WretchBlacklist_CherryPicked.xml` | Alpha Genes + Cherry Picker | Removes the cherry-picked `AG_DecreasedCommandRange` gene from the random-mutation blacklist (load error "Could not load reference ... AG_DecreasedCommandRange") |
| `Patches/BetterGPS_BiomesCavernsRoof.xml` | Better ground-penetrating scanner + Biomes! Caverns | The "allow under a roof" setting can actually place the scanner: Biomes swaps the roof check for its own class, which the setting never removes (unticking it only restores the vanilla check until the next restart) |
| `Patches/BigLittleModPatch_LinkableGroupAbstractDefs.xml` | Big Little Mod Patch + Linkable Groups | Drops the entries in its `LinkableGroupDef`s that name abstract parents (`BasicBedBase`, `VFE_*BedBase`, `VFES_AdvancedBedBase`, `TableSimpleProsthetic`) or the 1.5-only `Table_LightEndTable` (load errors "Could not resolve cross-reference to Verse.ThingDef named ... (wanter=affected)"); Linkable Groups already lists the concrete beds, so no link is lost |
| `Patches/BiomesCaverns_SingleNogtyl.xml` | Biomes! Caverns | Only one "nogtyl" per plant menu: the cave copy (`BMT_Nogtyl`) sows only in fungiponics basins, the marsh one (`BMT_NogtylMarsh`) in growing zones and VCE aquatic growers; wild growth unchanged |
| `Patches/Blueprints_Waylith17_FernyCompat.xml`, `Defs/Blueprints_Waylith17_Tips.xml` | Blueprints - 1.7 Waylith (Unofficial) + Better Architect Menu / Loading Screen Repository | Those two only load their Blueprints extras for the old `defi.blueprints.fork`; same extras for the 1.7 fork: Blueprints tab nested under Colony, and the blueprint loading tip |
| `Patches/ConsistentText_UraniumRecipe.xml` | Consistent Text | Restores the Alpha Animals refinery recipe label (`AA_ExtractUranium`) its patch deletes |
| `Patches/TechLevel_KeepNeolithicBuildings.xml` | Core + Vanilla Factions Expanded - Tribals | Hoopstone ring, Game of Ur board and VFE Tribals' floor painting stay buildable after VFE Tribals advances the colony past Neolithic (their `maxTechLevelToBuild` cap removed) |
| `Patches/ReGrowth_RemovedPlants.xml` | Cyanobot's Plant Gen Patches + Biomes! Oasis | Drops `RG_Plant_JoshuaTree` / `RG_Plant_WingCactus` from biome wild plants while ReGrowth 2 keeps those defs commented out |
| `Patches/FlourishEveryday_FloorDrawNoHands.xml` | Flourish - Everyday Animations + Show Me Your Tools | Children's floor drawing: Flourish hand tracks and body-lowering track removed, so only Show Me Your Tools' crayon and hands are drawn and line up |
| `Patches/Fortifications_NoWorldArtilleryOnTurretGuns.xml` | Fortifications - Industrial + VFE Security | Multi-barrel mortar launcher, field howitzer and field cannon lose the world artillery comp, which null-refs on them once player-owned (they are not `Building_Artillery`) and wipes the gizmo bar, Uninstall included |
| `Patches/Gulden_CapricornHorseMeat.xml` | Gulden Biome (Continued) | Capricorns butcher into vanilla horse meat, so "horse meat" no longer shows twice (old saves: rename `Meat_Gulden_Animal_Capricorn` to `Meat_Horse`) |
| `Patches/HaulersDream_BatchCraftAnimations.xml` | Hauler's Dream | Batch crafting gets the same Flourish animations and Show Me Your Tools tools as a normal bill |
| `Patches/Casino_TableGames.xml` | Hospitality: Casino + Det's Xenotypes - Boglegs + VFE Settlers | The tongo table and the vanilla billiards table become casino equipment like Casino's poker table: pricing gizmo, silver held and total earned. Tongo also becomes `Gamble` joy (as poker does); billiards stays `Gaming_Dexterity`. Both keep their own job drivers (tongo cards, billiards shots); the charge per game comes from Harmony3StrictCompat. The VFE Settlers faro table, which already plays with vanilla's poker driver, gets everything Casino gives the poker table: comp, `Gamble` joy and Casino's paying poker driver. Colonists play for free |
| `Patches/MSSFP_ExorcismGoldCount.xml` | MSS Flavour Pack | The exorcism operation costs 10 gold as its description says, not 100 (its `count` 10 was in volume units, and gold counts 0.1 per piece) |
| `Patches/UIRethemed_NoLoadoutStateCard.xml` | UI Rethemed - Inspector Tabs + Compositable Loadouts | No "Loadout state" card in the Gear tab overview |
| `Patches/ShowMeYourTools_NoTelescopeSpyglass.xml` | Show Me Your Tools | No floating handheld spyglass while using a telescope (kept for skygazing) |
| `Languages/English/Keyed/TweaksGalore_Fixes.xml` | Tweaks Galore | The "Trader available" alert no longer shows a literal `{0}` before the trader list (its code appends the list to the translated string instead of formatting it); same key without the placeholder, later-loaded keyed entries replace earlier ones |
| `Patches/Scanners_NotForMechs.xml` | Fortifications - Industrial (any mod scanner) | Mechs no longer take scanner jobs that null-ref on their missing skills (`JobDriver_OperateScanner` null-ref on Fabricors at the radio): `canBeDoneByMechs` false as on vanilla's scanners, for every scanner work giver that omits it |
| `Patches/RimsenalSecurity_TurretRangeRings.xml` | Rimsenal - Security Pack | Range ring while placing the shard sentry, ULM cannon, barrage turret, cannon and rotary gun turret (vanilla `PlaceWorker_ShowTurretRadius`, which the mod left off). Incinerator and graser turrets excluded: their beam verb makes the vanilla placeworker null-ref |
| `Patches/VFE_ErgonomicChairReplacesChairs.xml` | Vanilla Furniture Expanded | The ergonomic chair gets the `Chair` replace tag, so it can be placed directly over existing chairs and stools (with Replace Stuff it swaps in place) |
| `Languages/English/Keyed/VPWE_GivesAbility.xml` | Vanilla Persona Weapons Expanded | The persona-weapon psycast stat line reads "Gives ability" instead of the raw key `VREA.GivesAbility` (its code uses a key that only ships with Vanilla Races Expanded - Archon) |
| `Patches/VQEA_DeconstructibleTubes.xml` | Vanilla Quests Expanded - Ancients | Decorative pneumatic tubes in vaults can be deconstructed (launch port and termini left alone, they have code behind them) |
| `Patches/UniversalBlueprints_RimBuilderEnglish.xml` | Universal Blueprints Alpha Pack / DMS Pack | Their one childhood backstory (`rimcreator`, "边缘建造师") ships in Chinese only; English title, short title and description. Both packs define the identical def, so one patch covers whichever is active |

Load order: after VQE Ancients, Big Little Mod Patch, Cyanobot's Plant Gen Patches, Consistent Text, Flourish Everyday, Alpha Biomes, Vanilla Landmarks Expanded, Gulden Biome, Biomes! Caverns, Vanilla Furniture Expanded, Det's Boglegs and Hospitality: Casino (declared in `About/About.xml`).

Companion C# fixes: [Harmony3StrictCompat](https://github.com/hugalafutro/Harmony3StrictCompat).
