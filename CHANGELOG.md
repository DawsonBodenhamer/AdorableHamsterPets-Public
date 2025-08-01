# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- 

### Changed
- 

### Fixed
-

---

## [3.0.0] - 2025-07-27

# **The Heist & The Haste Update**

## Your hamsters have developed expensive taste, learned new languages, and also contracted the zoomies.

Introducing the brand new **Diamond Stealing** mechanic, where your furry companions will snatch your valuables and challenge you to a game of keep-away. Feed them some **Steamed Green Beans** and witness the true meaning of "zoomies" as they tear around you in a chaotic, super-charged sprint. 

This update also includes a complete, config-driven overhaul of the entire biome spawning system for incredible mod compatibility, smarter AI, new animations, and a ton of critical bug fixes.

#### <font color="red"> **IMPORTANT:** Due to the extensive changes to the spawning system, it is **highly recommended** that you delete your existing config file (`/config/adorablehamsterpets/main.toml`) before loading a world with this version. This will allow the new, more detailed settings to generate correctly. Your old settings will be lost.</font>

---

### Added
- **Russian, Chinese, and Korean Language Support**
  -   Ever heard a hamster squeak in Chinese? I didn't think so. But now, you can! Or perhaps you would prefer a little bit of cooing in Russian... or a squeal in Korean? Thanks to a few of the awesome people in The Cheek Pouch Discord channel, the mod has been fully translated to three languages and more on the way!
- **New Major Feature: Item Stealing & Chase Mechanic**
  -   Tamed hamsters now have a configurable chance to notice valuable items dropped on the ground (defaults to just diamonds).
  -   Nearly every aspect of this feature is configurable, including which items can be stolen (you can add any item, multiple items simultaneously, and even items from other mods!).
  -   When they spot one, they'll perform a unique pounce animation and snatch the item, initiating a playful game of keep-away. The pounce sound effect is even dynamic, changing based on the material of the stolen item in case you modify it in the config!
  -   While in "heist mode," the hamster will flee if you get too close and cheekily taunt you from a distance with a new animation, encouraging a chase.
  -   The stolen item is visually rendered in the hamster's mouth, synced with all head movements and animations.
  -   To get your item back, you have to catch your speedy thief and right-click it. If you take too long, the hamster will get bored and drop the item. But then, hamsters have a short memory, so it will probably pick it up again.
- **New Major Feature: "Zoomies" for Buffed Hamsters**
  -   Hamsters under the effect of Steamed Green Beans will now get the "zoomies," a burst of energetic, high-speed activity.
  -   Instead of wandering aimlessly, they will sprint in dynamic, chaotic circles around their owner.
  -   When following their owner, they will no longer run in a straight line but will instead dart around randomly in the owner's general direction.
  -   This frenetic behavior is accompanied by a new custom particle trail that bursts outwards from the hamster as it sprints.
- **New Sprinting Animation & Standardized Speeds**
  -   A third-tier "sprinting" animation has been added for the hamster's highest speeds, used during zoomies and fleeing.
  -   All hamster movement speeds have been standardized across all AI goals for more consistent and predictable behavior.
  -   Walking and running animations are cuter.
- **Enhanced Idle Animations**
  -   Hamsters will now occasionally play one of three new, randomized "looking up" animations when their `LookAtEntity` AI goal is active and they are looking at a nearby target (like you).
- **New Wild Hamster Settle to Sleep Animations**
  -   Hamsters will now play one of three new, randomized "settle to sleep" animations, paired with the three already-existing sleeping animations when going to sleep, similar to how tamed hamsters already did when sitting.
- **Configurable Biome Spawning System (Major Rework)**
  -   The entire spawning system for both hamsters and world-gen features (bushes, sunflowers) is now controlled by the config file.
  -   Users can now define exactly where things spawn using biome IDs, vanilla biome tags, and "convention tags" (`c:is_cold`, `c:is_forest`, etc.) for vastly improved compatibility with modded biomes from packs like Terralith and Biomes O' Plenty.
  -   Each feature and the hamster itself has its own set of include/exclude lists and tag lists, offering granular control over world generation.
- **New Faster Throw Velocity for Buffed Hamsters**
  -   Throwing a hamster while it's under the effect of the Steamed Green Bean buff will now launch it at nearly double the default velocity.
  -   Both the default and buffed throw velocities are now configurable in a new "Hamster Yeet Settings" group in the config.
  -   (A special thanks to `@Petite` on Discord, who planned to defeat the Ender Dragon using only hamster projectiles. This idea inspired me to ensure they had enough velocity to reach the dragon in the first place! 😂)
- **Improved Shoulder Dismount Logic**
  -   When the player dismounts the hamster from their shoulder, it will now be placed at the location where the player was looking if it was safe and within reach. If not within reach, it will spawn at the player's feet.
- **New Config Option**
  -   Added a config option to change the default name of the hamster entity to "Hampter" instead of "Hamster," because I wanted to, so I did.

### Changed
- **Spawning Logic Overhaul**
  -   The internal logic for determining hamster color variants has been completely rewritten to be "hamster-centric." It now uses a combination of specific biome checks, vanilla tags, and universal convention tags to ensure hamsters spawn in thematically appropriate locations, even in heavily modded worlds. Note: I only had time to test this with Terrralith— so if you're using a different biome generation mod (Biomes O' Plenty, Oh The Biomes You'll Go) you may see more frequent orange hamsters, since they are the default fall back. Or maybe it will work perfectly! Lol.
  -   The custom sunflower replacement system is now also tag-aware. It will now correctly replace vanilla sunflowers with the harvestable version in any biome that is supposed to have them (including modded biomes), not just the vanilla Sunflower Plains.
- **Diamond Seeking AI Improved**
  -   The independent ore-seeking AI is now smarter. Hamsters will now prioritize pathfinding to exposed ores that are visible to the player before considering ores that are completely buried.
  -   A new particle breadcrumb trail has been added. When a hamster is leading you to an ore, it will now create a faint trail of dust particles along its intended path, making it much easier to see where your tiny prospector is headed.
- **Death Message Attribution**
  -   Death messages will now credit the hamster by its name (e.g., "Player was slain by Hampter") instead of attributing the kill to the hamster's owner. Hamsters are now fully complicit in their actions. 😁
- **Dependencies**
  -   The Jade mod is no longer a required dependency and is now correctly listed as optional for all mod loaders. The game will no longer crash if Jade is not installed.
- **Pathfinding & AI**
  -   Hamster pathfinding penalties around hazards have been strengthened. They will now be much more reluctant to pathfind into or near fire and lava.
  -   The idle AI goals (Wander, Look At, Look Around) have been re-balanced to prevent them from fighting with each other, resulting in much more natural and less "flickery" idle behavior.
- **Textures & Animations**
  -   The textures for the Blue and Lavender hamster variants have been updated with slightly increased saturation to make their colors more distinct and recognizable without being neon.
  -   The textures for the Wild Cucumber Bushes have been slightly desaturated to help them blend more naturally into the warmer, drier biomes where they typically spawn.
  -   The transition speed between animations has been reduced from 5 ticks to 2 ticks, resulting less of the "hamster sliding across the ground" type of effect when it is transitioning between movement animations.
  -   The rotation speed of the hamster has been overhauled to account for it not having a separate head and body like vanilla models, resulting much more snappy rotations and accurate target-facing. Vanilla Minecraft mobs move their head first, and body follows second at a much slower pace. Since my hamsters use Geckolib for the model, they do not have a separate head and body in the same way that vanilla mobs do, which resulted in a quick initial turn where the hamster would turn halfway toward its target, and then a slower finish. I basically combined both of them together to eliminate that weird behavior.
  -   The speed of the running animation has been decreased by 25% to better differentiate it from the new sprinting animation, giving it a more natural pace.

### Fixed
- **Fixed Shoulder Hamsters Being Deleted on Player Death**
  -   Resolved a critical bug where a shoulder-mounted hamster would be permanently deleted if the player died, even with `keepInventory` enabled. The system now correctly detects the player's respawn and safely dismounts the hamster at the player's death location.
- **Fixed Hamster Suffocation on Dismount/Throw**
  -   Implemented a robust safe-spawning algorithm that performs a multi-stage search for a valid, non-obstructed location when a hamster dismounts or lands from a throw. This should completely resolve all known suffocation bugs.
- **Fixed Right-Click Stack Splitting in Hamster Inventory**
  -   Corrected the underlying inventory logic to properly handle the `amount` parameter when removing items. Players can now correctly right-click to split stacks of items inside the hamster's cheek pouch inventory, just like in a vanilla chest.
- **Fixed Thrown Hamster Particle Desync**
  -   Adjusted the spawn position calculation for the in-flight particle trail. The trail now correctly originates from the hamster's model instead of appearing slightly ahead of it, which was most noticeable when viewing from a second player's perspective or with replay mods.
- **Fixed Black Hamster Overlay Spawning**
  -   Wild black hamsters will now only spawn with their solid base color. This makes their appearance in dark environments like caves more thematic and reserves their white overlay patterns as a special trait achievable only through breeding.

---

## [2.3.0] - 2025-07-16

# 1.20.1 Forge/Fabric/Quilt support has arrived!

## After a long and surprisingly complex battle with the Forge 1.20.1 datapack and build systems, the mod is now fully functional on Forge. Your hamsters are now free to cause chaos across multiple mod loaders.

### Added
- Official support for Minecraft 1.20.1 for Forge and Fabric.
- Official Quilt support for 1.21.1 and 1.20.1

### Changed

- Improved hamster dismount logic. Hamsters will now be placed at the block the player is looking at (within a 4.5 block range), providing more precise and intuitive placement. I don't know about you, but when I take a hamster off my shoulder in real life, I get to choose where I put it down. It just made sense lol
- **Particle Changes:**
  - The ominous trial spawner particles (diamond celebration) and GUST particles (hamster flight trail) both had to be switched out since they don't exist in 1.20.1. I'm using composting particles for the diamond celebration since they have an upward bias, and cloud particles for the hamster flight trail.

### Fixed
- Fixed a critical bug where hamsters could suffocate inside blocks when dismounted from the shoulder or after impacting a block from being thrown. A robust safe-spawning algorithm now works in tandem with the new dismount logic to ensure hamsters are always placed in a valid, non-obstructed location.
- Fixed a visual bug where the particle trail for a thrown hamster would appear ahead of its model during flight.
- Removed the non-functional Hamster Guide Book from the creative mode inventory tab to prevent confusion.
- Resolved a critical issue on Forge where no custom world generation (hamsters, wild bushes, custom sunflowers) would occur.
- Fixed a startup crash on Forge related to the Hamster Spawn Egg item registration order by implementing a platform-specific solution.
- Wrestled the Forge build process to properly include all necessary models, textures and data files.
---

## [2.0.2] - 2025-07-16

### Fixed
- Fixed an issue where Wild Bushes and custom Sunflowers were not generating in the world on the NeoForge version of the mod.
- **Developer's Note:** You might be thinking, "Didn't you *just* fix a spawning bug?" You're right! As it turns out, the way NeoForge handles adding *entities* to the world is similar to how it handles adding *features* like plants, but yours truly is just now learning this. Lol. Thanks for your patience as I navigate the wonderful quirks of multi-loader development. Incidentally, unlike with the hamster spawning fix, if any of you already spawned in a world on NeoForge, just FYI— this fix will only take place in newly generated chunks.

---

## [2.0.1] - 2025-07-06

### Added
- **Creeper Behavior:** Creepers will now flee from hamsters, similar to their behavior with cats. This should prevent them from detonating near your beloved pets and landscape. Thanks to [mikabean999](https://www.reddit.com/user/mikabean999/) on Reddit for the idea.
- **Cheese Configurability:** Added new configuration options to control the hunger and saturation values restored by eating Cheese, allowing server owners to better balance food.

### Fixed
- Resolved a critical issue where Hamsters would not spawn naturally in the world on the NeoForge version of the mod. This was caused by an incorrect implementation of the biome modification logic for the NeoForge loader. The fix replaces the faulty Java-based event listener with a data-driven biome modifier JSON that correctly hooks into NeoForge's world generation pipeline.
- Fixed a bug that caused the hamster's cleaning sound to loop indefinitely if the hamster was commanded to stand up mid-animation.
- Fixed a bug where wild hamsters would incorrectly perform the cleaning animation while sleeping. This behavior is now correctly restricted to tamed, sitting hamsters.

---

## [2.0.0] - 2025-07-02

# Neoforge support has arrived!

## **Added Architectury Multi-Loader Support:** The entire mod has been refactored from a Fabric-only project to an Architectury project, enabling official support for both Fabric and NeoForge from a common codebase.

### Also Added
- A new configuration option, "Gold 'Mistake' Chance", to control the probability of a hamster mistakenly finding gold instead of diamond.
- A startled jump, complete with a bounce sound effect, that plays when a hamster "mistakenly" finds gold ore.
- A new message that appears when a hamster finds gold, in case that feature might be confusing for new players who expected it to find diamond.
- Two additional sound variants for eating cheese to make the audio feel more natural.
- The currently playing animation name will now display on the Jade debug overlay for easier diagnostics.

### Changed
- **Complete Refactor to Architectury API:** The entire mod has been refactored from a Fabric-only project to a cross-platform Architectury project. This makes the codebase platform-agnostic and ensures future features can be developed for both loaders simultaneously. Key changes include:
  - Replaced all Fabric API registries (for Items, Blocks, Entities, etc.) with Architectury's deferred registration system.
  - Replaced the Fabric Networking API with the Architectury Networking API, centralizing all packet handling into a single `ModPackets` class.
  - Replaced Fabric-specific events (Player Join, Commands) with their cross-platform Architectury equivalents.
  - Replaced the Fabric-only `AttachmentType` system for shoulder riding with a vanilla `DataTracker` system, mimicking the vanilla parrot mechanic for better stability and compatibility.
  - Implemented an `@ExpectPlatform` bridge to handle loader-specific spawn restriction logic, keeping the common codebase clean.
  - Resolved numerous NeoForge-specific loading and registration crashes by implementing native event handlers for renderers, model layers, and screens, ensuring compatibility with the NeoForge lifecycle.
  - Replaced a Fabric-only access widener with a cross-platform Mixin Accessor to ensure custom AI goal logic works on both loaders.
  - Corrected the NeoForge build script to properly include data-generated assets and Mixin configurations, fixing missing textures, translations, and features.
- Adjusted spawn locations for Wild Cucumber Bushes and Wild Green Bean Bushes. Cucumber Bushes (for the essential taming item) are now much more common and appear in a wider variety of temperate biomes. Green Bean Bushes (for the optional buff item) are now less common and are focused in more specific "lush" or "wet" biomes.
- Lavender hamsters now spawn in Mushroom Fields as well as Cherry Groves, making them more discoverable. It just fits. They are almost the color of Mycelium after all.
- **Hamster Model:**
  - The base hamster model has been scaled down 20% for cuteness, and so it better matches the scale of the shoulder model.
  - The shoulder-mounted hamster model has been scaled down 10% (it was already smaller than the base model) so it fits better on the player's shoulder, and raised slightly so it doesn't clip into the shoulder as much, but not too much so it doesn't look like it's floating.
- The volume of the hamster cleaning sound has been doubled. It was actually so quiet it was not even audible with the Sound Physics mod installed.
- The volume of the cheese eating sound effect has been increased by 20%. Hehe.
- **Hamster Animations:**
  - Improved the running and walking animations while I was creating an entirely new “sprinting” animation which will be hopefully released in the next update.

### Fixed
- **Resolved a critical server crash** caused by client-side classes (`Screen`, `SoundInstance`, `MinecraftClient`) being referenced in common code. All client-only logic for the guidebook, sounds, and particles is now correctly handled on the client, allowing the mod to run on dedicated servers.
- Fixed multiple crashes caused by illegally casting to a Mixin class (`PlayerEntityMixin`) instead of its proper accessor interface (`PlayerEntityAccessor`) when interacting with or throwing a hamster.
- Fixed a bug where `HamsterTemptGoal` would incorrectly activate while a hamster was in the "sulking" state.
- Prevented hamsters from starting or continuing cleaning while knocked out. I didn't even realize this bug was there until I added the cleaning sound effect, and then I started hearing it while the hamster was knocked out. Lol.

---

## [1.2.1] - 2025-06-12

### Fixed
- Resolved a critical crash that would occur when exiting a world to the main menu. This was caused by the mod attempting to send network packets after the connection to the server had already closed. Enjoy!

---

## [1.2.0] - 2025-06-11

### Added
- **Jade Integration for Wild Bush Tooltips:** Custom tooltips for Wild Green Bean Bushes and Wild Cucumber Bushes now appear in Jade's overlay if Jade is installed, mirroring their item tooltips.
- **Jade Integration for Hamster Debug Info (Configurable):**
  - Added an advanced debug information overlay for Hamsters when viewed with Jade.
  - Displays detailed AI states (current custom goal, sitting status, navigation, target), sleep sequence phases, love/interaction states, and general info like variant and age.
  - This feature is primarily for debugging and is **disabled by default**.
  - Can be toggled via a new option in the mod's config screen (Mod Menu -> Adorable Hamster Pets -> UI & Quality of Life -> "Enable Jade Hamster Debug Info").
  - Can also be toggled in-game by sneak-right-clicking a tamed hamster while holding the Hamster Guide Book. An action bar message confirms the toggle.
  - This Hamster Debug Info Jade integration is **AWESOME** for myself when bug fixing, but also for anyone reporting bugs (see `README`, "Bug Reporting Etiquette" section).
- **Independent Ore Seeking Feature:**
  - Tamed hamsters, after being on a player's shoulder while a diamond alert was active, can now independently seek out *that* diamond ore upon dismount.
  - Features new AI goal (`HamsterSeekDiamondGoal`) with distinct states: scanning, moving to ore, and waiting if path is blocked.
  - **Whoops! Who Put That There?** (There's a 33% chance a primed hamster targeting diamond might "mistakenly" pathfind to nearby gold ore instead. If this happens the hamster will be shocked and start sulking.)
  - **New Animations:**
    - `anim_hamster_seeking_diamond`: Looping animation for when the hamster is actively moving towards an ore.
    - `anim_hamster_wants_to_seek_diamond`: Looping animation for when the hamster has targeted an ore but its path is blocked.
    - `anim_hamster_sulk` (3s, non-looping) & `anim_hamster_sulking` (looping): Played if the hamster "mistakenly" finds gold.
  - **New Sounds & Effects:**
    - Dust particles (colored like the block the hamster is on) emit from the hamster's nose via animation keyframes while seeking.
    - Upon finding diamond: "Diamond sparkle" sounds play at the ore, special particles (`TRIAL_SPAWNER_DETECTION_OMINOUS` on hamster, `FIREWORKS` above ore) appear, and the hamster plays the begging animation with new "bounce" sound effects triggered by animation keyframes. Aggressive begging sounds also play periodically.
    - Upon "mistakenly" finding gold: A delayed orchestral hit (`alarm_orchestra_hit.ogg`) plays, followed by a delayed "hamster shocked" sound. Smoke particles appear above the gold ore, and black entity effect particles appear on the sulking hamster.
  - **Interaction:** Player right-click clears diamond celebration or sulking states, with new "affection" sounds.
  - **Configuration:** New options in Mod Menu to toggle the feature, its cooldown, and ore scan radius.
  - **Advancement:** New "Canine Aspirations?" advancement for when a hamster first successfully leads to diamond.
- **Jade Debug Overlay Enhancements:** The Jade debug overlay for hamsters now displays new states related to ore seeking (primed status, target ore, cooldown) and the sulking/celebrating diamond states.
- **New Sound Events:** Added `hamster_bounce`, `alarm_orchestra_hit`, `hamster_shocked`, `diamond_sparkle1-3`, and `hamster_affection1-3` sound events and their definitions.
- **Animation Personalities:** Tamed hamsters are now assigned one of three persistent "personalities" at birth, which determines the specific sitting animations they will use for their entire life, making each hamster feel more unique.
- **Configurable Cleaning Frequency:** Added a new option in the config ("Cleaning Frequency") to control how often a sitting hamster will start its cleaning animation.

### Changed
- **Hamster Blinking is Cuter:** Removed the code-based procedural blinking logic for `HamsterEntity`. Eye blinking and closure are now entirely controlled by keyframes within the GeckoLib animations (`anim_hamster.animation.json`), allowing for cuter and more context-aware blinking (e.g., slower blinks when sleepy).
- Updated `README.md` to include instructions for players on how to use and provide the new Jade Hamster Debug Info when reporting bugs.
- **Hamster AI for Following Owner:** Implemented `HamsterFollowOwnerGoal` in order to prevent hamsters from trying to follow their owner while they are celebrating a diamond find or sulking at gold (in addition to existing interruptions like sitting, sleeping, KO).
- **Hamster AI for Looking Around:** `HamsterLookAtEntityGoal` and `HamsterLookAroundGoal` are now disabled when a hamster is knocked out, sitting, or sulking, preventing rotation during this state.
- **Diamond Celebration Behavior:** Hamsters now also use the begging animation when celebrating a diamond find.
- **Begging Animation:** The begging animation has been updated to include keyframe-driven bounce sounds.
- **Dependency Declarations:** Updated `fabric.mod.json` to correctly declare hard dependencies on GeckoLib and owo-lib (now in `depends` section) and list ModMenu and Jade as optional (now in `suggests` section). This improves server compatibility and clarifies requirements for users and modpack creators.
- **Guidebook Update:** Added a new page to the "Hamster Tips" guidebook detailing the "Independent Ore Seeking" feature, including how to prime a hamster for it.
- ### Switched from owo-lib to Fzzy Config, which means lots of awsesome new config features, including change history and the ability to search for specific settings!
- **Footstep Sound System Overhaul:** Hamster footstep sounds now use a hybrid system to improve immersion.
  - When a hamster is on-screen, it uses precise, animation-keyframed sounds that are perfectly synchronized with its footfalls.
  - When a hamster is off-screen (and thus not animating for the client), it uses the traditional vanilla (server-side) movement-based sounds as a fallback. This ensures you can always hear your companions following you.
- **Sound Volume Balancing:**
  - Footstep sounds on gravel are now 40% quieter to better match the volume of sounds on other surfaces like grass and stone.
  - The volume of begging sounds has been reduced.
- **Cleaning Animation Sound:** The cleaning animation now features a continuous, looping scratch sound. Fun fact— it's actually the sound of me scratching my beard 🤭

### Legal
- **License Update & Clarification:** Updated the project license to a split model (see `LICENSE.md`).
  - Creative assets (models, textures, sounds, animations found in `/src/main/resources/`) are now **All Rights Reserved** to better protect the significant artistic effort invested. When "Adorable Hamster Pets" started nearly six months ago as what I thought would be a small weekend project, an MIT license seemed fine. I was so young and innocent of Javascript then. Lol.
  - The Java source code and other non-asset files remain under the **MIT License**, allowing for community learning and code-level contributions.
  - `fabric.mod.json` now points to `LICENSE.md` and specifies "Custom" license type.
  - The `README.md` has been updated with a detailed, user-friendly explanation of these permissions.
  - The `LICENSE` file was renamed to `LICENSE.md` so I could make it more readable.

### Fixed
- **Hamster Guide Book Crafting and NBT Application:**
  - Fixed an issue where the crafting recipe for the Hamster Guide Book (1 Book + 1 Sliced Cucumber) would not appear or unlock correctly.
  - The recipe is now generated via datagen and produces a plain, NBT-less book.
  - A technical advancement now triggers upon crafting this plain book. The function rewarded by this advancement robustly clears any existing guidebooks from the player's inventory and then gives a single, new guidebook pre-filled with all NBT content (pages, title, author), ensuring the player always receives the complete, functional version.
- **Wild Hamster State & Animation Bug on World Load:**
  - Corrected an issue where wild hamsters would incorrectly load with their "Sitting" NBT tag as true, causing them to be stuck in a sitting animation while attempting to wander, and preventing them from sleeping or being tempted correctly.
  - `HamsterEntity` NBT save/load logic now ensures the "Sitting" tag is only saved for tamed, player-commanded sitting, and wild hamsters correctly initialize without a sitting state on load.
- **Hamster Spawning `maxGroupSize` Config Access:** Corrected the code in `ModEntitySpawns.java` to use the proper accessor path for `maxGroupSize` and `spawnWeight` from the owo-lib generated configuration, ensuring these settings are correctly applied during world generation. Due to a confirmed bug with owo-lib, the `maxGroupSize` slider mistakenly displays `0` instead of the default `1`, but this is only visual. Since the mod now uses Fzzy Config, this issue is no longer present.
- **Biome Variant Spawning:** Hamsters now spawn with the correct color variants in all intended biomes. This fixes an issue where hamsters in Stony Shores, Windswept biomes, Jungles, and other previously uncovered areas would incorrectly default to the Orange variant. Black hamsters can now also correctly spawn in the Deep Dark biome.

---

## [1.1.1] - 2025-05-26

### Added
- **Advanced Sleep System for Tamed Hamsters:**
  - Tamed hamsters, when commanded to sit, may now gradually drift off to sleep through a new multi-stage "Path to Slumber" animation sequence.
  - Features new animations: `anim_hamster_drifting_off` (a long, gradual doze), `anim_hamster_settle_sleep1/2/3` (short transitions), and three distinct looping sleep poses (`anim_hamster_sleep_pose1/2/3`).
  - Sleep sequence is influenced by daytime (configurable), nearby threats, and how long they've been sitting.
  - Player interactions (feeding, inventory, etc.) will now wake up a dozing/sleeping tamed hamster.
- **Configurable Sleep Timings:** New options in Mod Menu config to adjust how long tamed hamsters sit before trying to sleep, their threat detection radius for sleep, and whether daytime is required for them to get drowsy.
- **Pink Petal Cycling & Shear Removal:**
  - Right-clicking a tamed hamster with Pink Petals now cycles through three different petal decoration styles.
  - Pink petal decorations can now be removed by right-clicking the hamster with Shears (drops one pink petal).
- **Hamster Water & Fire Avoidance:** Hamsters will now try to pathfind around water, fire, and lava, making them a bit safer. Lol.
- **Shoulder Riding Sounds:**
  - Added new unique sound effects when a hamster mounts the player's shoulder (via cheese interaction).
  - Added a distinct sound effect when a hamster dismounts from the shoulder.
- **New Advancements:**
  - "Petal Pusher": Awarded for decorating a hamster with pink petals. Includes subtle sound/particle effects on first application.
  - "Pocket Paramedic": Awarded when a hamster successfully auto-feeds from its cheek pouch.
  - "Nose for Treasure": Awarded when a shoulder hamster first alerts the player to nearby diamonds.
  - "Impending Doom Squeak": Awarded when a shoulder hamster first alerts the player to a targeting Creeper.
  - "Chipmunk Aspirations": Awarded when a player fills all slots in a hamster's cheek pouch.
- **"Sweet Potato" Easter Egg (Advancement-Based):**
  - Naming a hamster "Sweet Potato" now triggers special effects (sound, particles, message) via a hidden advancement. This is a one-time effect per player. I added this for my wife since the entire mod is based on her real life hamster named Sweet Potato. She doesn't read change logs so she'll never see this. Hehe.

### Changed
- **Hamster Auto-Eating Delay:** Introduced a 2-second delay before a hamster begins to auto-eat from its cheek pouch when injured, giving players a better chance to notice the action and its effects.
- **Hamster Auto-Eating Cooldown:** Increased the cooldown after a successful auto-eat to 3 seconds (60 ticks). It was a bit overpowered.
- **Hamster Melee Attack Particles:** Changed from "poof" particles to "crit" particles, because poof particles already spawn when the attacked entity dies. Let me know If you're reading this and you have ideas for particles I should add to any of the other animations. I'm all ears!
- **Hamster Textures:** Subtle visual enhancement to the area between the hamster's eyes for increased cuteness, especially noticeable during sleep.
- **Configuration Screen Reorganization:** Restructured the Mod Menu config screen with more descriptive top-level sections and logical sub-headers for improved clarity and ease of use. (All your settings are still there, just better organized!)
- **Wild Hamster Sleep Animation:** Wild hamsters now use a new `anim_hamster_wild_settle_sleep` transition animation before entering their looping sleep pose (`anim_hamster_sleep_pose1`).

### Fixed
- **Sliding Sit Bug:** Fixed an issue where tamed hamsters would appear to slide while in their sitting animation if they stood up to defend their owner. Animations now correctly sync with their actual sitting/standing state.
- **Body Rotation While Sitting/Sleeping/KO'd:** Hamsters will no longer rotate their bodies to look at entities while they are in a sitting, sleeping, or knocked-out state.
- **Hamster Targeting:**
  - Tamed hamsters will no longer attack other animals owned by the same player (including horses, wolves, cats, etc.) when commanded by the owner.
  - Tamed hamsters will no longer retaliate against other animals owned by the same player if accidentally hit by them.
- **Shoulder Mounting Sound:** Cheese use sound now plays at the hamster's last location, while the new hamster mount sound plays near the player's ear.

---

## [1.1.0] - 2025-05-19
<!-- Replace YYYY-MM-DD with 1.1.0's release date -->
### Added
- **Advancement Tree:** With distinct branches leading the player to explore different features.
- Custom Advancement Tab ("The Hamster Life"):
  - Guides players through mod features with custom titles, descriptions, and icons.
  - Features a branching structure after initial taming.
  - Includes advancements for obtaining seeds, taming, crafting key items (Sliced Cucumber, Food Mix, Steamed Beans), shouldering, throwing, feeding buffs, and unlocking cheek pouches.
  - Uses custom criteria for specific mod interactions (shouldering, throwing, feeding buffs, pouch unlock, initial guidebook).
  - "Goal" and "Challenge" advancements play distinct sounds on unlock.
- Crafting Recipe for Hamster Guide Book:
  - Players can craft the Hamster Guide Book (1 Vanilla Book + 1 Sliced Cucumber).
  - Crafted book comes pre-filled with all NBT content (pages).
  - A hidden advancement triggers on crafting, playing particle/sound effects.
- Config option `uiTweaks.enableItemTooltips` to toggle custom mod item/block tooltips.
  - When off, tooltips will show item name and "Adorable Hamster Pets" for mod identification.
- Config option `uiTweaks.enableAutoGuidebookDelivery` to toggle automatic guidebook delivery on first join.
  - Thanks to `@MylesGit` on GitHub for suggesting those config ideas, custom advancements, and Guide Book crafting recipe.
- New hamster base color variants: Blue and Lavender.
  - Blue hamsters (with 8 overlay options) spawn rarely in Ice Spikes biomes (70% chance for Blue, 30% for White).
  - Lavender hamsters (with 8 overlay options) spawn rarely in Cherry Grove biomes.
- Four new overlay patterns (overlay5, overlay6, overlay7, overlay8) for all applicable base colors, increasing visual diversity.
- Numerous sound effect variations for hamster actions (idle, hurt, attack, sleep, beg, death, creeper detect, diamond sniff, celebrate).
- Pink Petal cosmetic overlay system:
  - Players can right-click a tamed, owned hamster with `minecraft:pink_petals` to apply one of three random pink petal textures.
  - Right-clicking again with pink petals removes the cosmetic overlay.
  - Applying consumes a petal item; removing does not.
  - Petal state is saved with the hamster and visible on the shoulder.
  - Includes sound and particle effects for application/removal.
- Player-edible Cheese:
  - Cheese is now a food item for players (Nutrition: 8, Saturation: 0.8F).
  - Features a custom eating sound and a faster eating time (20 ticks vs. vanilla 32).
- Cheek Pouch Locking Mechanic:
  - By default, hamster cheek pouches are locked upon taming.
  - Feeding a hamster `HAMSTER_FOOD_MIX` for the first time (resulting in healing/love mode) permanently unlocks its pouches.
  - Plays a sound and spawns particles upon pouch unlock.
  - New config option `features.requireFoodMixToUnlockCheeks` (default: true) allows disabling this lock.
- Display a random, non-repeating message on the action bar when a shoulder hamster dismounts due to sneaking.
  - Configuration option (`features.enableShoulderDismountMessages`) to toggle shoulder dismount messages.

### Changed
- **Hamster Textures:** All hamster textures (including overlays) have been considerably reworked for improved aesthetics and to ensure they are not overly similar to textures from the "Hamsters" mod by Starfish Studios.
- **Hamster Variant System:** Breeding logic updated: If both parents have an overlay, baby must have an overlay, preferably different from parents. If one/neither parent has an overlay, baby can have an overlay (different from parents if applicable) or no overlay.
- **Shoulder Summoning:** Hamsters are now summoned to the shoulder by right-clicking a tamed, owned hamster while holding `ModItems.CHEESE` (instead of right-clicking air with cheese).
- **Hamster Tempting:** Hamsters are now also tempted by (and will beg for) `ModItems.CHEESE` and `ModItems.STEAMED_GREEN_BEANS`, in addition to `ModItems.SLICED_CUCUMBER`.
  - However, `ModItems.SLICED_CUCUMBER` is still the only thing that can tame a hamster.
- **Spawn Egg Item Model:** Now uses data generation (`Models.GENERATED`) for its model, pointing to a custom sprite texture `adorablehamsterpets:item/hamster_spawn_egg` to mesh better with the new spawn egg textures seen in Snapshot 25w08a. (Future proofing.)
- **Item/Creative Tab Icons:** Both the "Adorable Hamster Pets" creative tab and the root "The Hamster Life" advancement tab now use the (custom textured) `HAMSTER_SPAWN_EGG` as their icon.
- **Hamster Spawning:** Removed light level check from spawn restrictions to allow hamsters to spawn in dark areas like caves, provided the block below is valid.
- **Guidebook Content:** Significantly updated and expanded to reflect new features, revised mechanics, and ensure brand voice consistency. Page order adjusted.
- **Guidebook Delivery:** Initial delivery on first join now uses a persistent "flag" advancement (`technical/has_received_initial_guidebook`) to ensure it's truly one-time, respecting the config toggle. The advancement tab (`husbandry/root`) now unlocks immediately for all players via a `minecraft:location` trigger.

### Fixed
- **Melee Attack Particles:** Implemented Geckolib creator, Tslat's suggested fix; particles now spawn correctly at the attacking hamster's foot for all attacks, including the first, and in multi-entity scenarios.
- **Recipe Book Visibility:** Corrected an issue where the "Hamster Food Mix" recipe might not unlock as expected; ensured its advancement criterion correctly requires only `ModItems.SUNFLOWER_SEEDS`.
- Corrected various minor code errors and improved config access patterns.

### Removed
- Numerous hamster sound effect variations used for testing which were not intended to be present in the released version of the mod.
- Shoulder-mounted hamsters no longer dismount when the player takes damage.

---

## [1.0.1] - 2025-05-10
<!-- Replace YYYY-MM-DD with 1.0.1's release date -->

### Changed
- (Internal) Reorganized code structure and updated comments for `HamsterFleeGoal.java`, `HamsterSleepGoal.java`, `HamsterTemptGoal.java`, `HamsterShoulderFeatureRenderer.java`, and `PlayerEntityMixin.java` for improved readability.
- (Internal) Tweaked the "begging" animation to slightly shift the hamster model forward for better visual positioning (`anim_hamster.animation.json`).

### Fixed
- Resolved issue where sitting hamsters could still be tempted by items, causing them to move while sat, which was hilarious. (`HamsterTemptGoal`).
- Corrected wild hamster sleeping behavior: they now consistently wake up when a player approaches, regardless of the player's sneaking status or held item (`HamsterSleepGoal`).
- Adjusted baby hamster rendering (`HamsterModel.java`, `HamsterRenderer.java`):
  - Corrected model scaling logic to properly apply base scales for baby/adult states while allowing JSON animations (e.g., breathing) to function proportionally.
  - Implemented differential scaling for baby hamsters, resulting in a relatively larger head compared to their body.

### Documentation
- Updated `README.md` and item tooltip for the guide book to remove references to an in-book command for re-obtaining it (the book was spawning in without any content and the command to generate its content was way too long for any sane person to type.)

---

## [1.0.0] - 2025-05-04
<!-- Replace YYYY-MM-DD with 1.0.0's release date -->

### Added
- First public version of Adorable Hamster Pets. Hello world!
