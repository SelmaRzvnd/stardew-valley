# Stardew Valley — Advanced Programming Project

A multiplayer farming simulation game inspired by Stardew Valley, built in Java using the MVC architecture pattern. Developed as a group project.

---

## Overview

A full-featured 2D farming simulation where players manage their own farm, grow crops, raise animals, fish, craft items, cook food, trade with other players and NPCs, and build friendships — all within a shared multiplayer world rendered through a custom graphical interface.

---

## Tech Stack

- **Language:** Java
- **IDE:** IntelliJ IDEA
- **Build Tool:** Apache Maven
- **Architecture:** MVC (Model-View-Controller)
- **Data Persistence:** JSON (Gson / YaGson)
- **Version Control:** Git / GitHub

---

## Features

### Authentication & User Management
- Registration with strong password validation, email verification, and security questions
- Password recovery via security questions
- Random secure password generation
- Stay logged-in across sessions
- Full profile management: username, nickname, email, password
- SHA-256 password hashing
- Per-user stats: highest money earned in a single game, total games played

### Multiplayer & Game Sessions
- Create a game with up multiple players
- Turn-based multiplayer: each full round of turns advances in-game time by one hour
- Save and load game state with full persistence
- Force-terminate a running game via majority vote
- Per-player map selection at game start

### World & Map
- Each player has their own farm with fixed landmarks: cottage, greenhouse, lake, mine/quarry
- A shared overworld connects all farms with an NPC village at the center
- Procedurally scattered trees, rocks, and forageable items at game start
- Energy-based pathfinding (shortest path) for player movement
- Players can only enter their own farm or shared areas
- Interactive minimap showing player positions, buildings, and NPC locations

### Time, Seasons & Weather
- In-game clock starting at 9:00 AM, advancing each round
- Four seasons — Spring, Summer, Fall, Winter — each lasting 28 days
- Daily weather: Sunny, Rainy, Stormy, Snowy, each with unique gameplay effects
- Rainy days automatically water crops; stormy days randomly strike crops and trees with lightning
- Snowy days double tool energy consumption
- Day/night cycle with screen darkening after 6 PM
- Visual weather effects: rain, snow, and thunderstorm flash animations

### Farming
- Full crop lifecycle: tilling, planting, watering, fertilizing, and harvesting
- Crops have multiple growth stages, optional regrowth cycles, quality tiers, and seasonal restrictions
- Giant crops: plant 4 of the same type in a 2×2 grid to grow a mega-harvest crop
- Mixed seeds: random crop from the current season's pool
- Trees produce fruit periodically, drop seeds when chopped, and char when struck by lightning
- Nightly crow attacks can destroy crops; scarecrows provide protection
- Forageable items naturally appear across the map each day
- Greenhouse allows year-round farming, immune to weather and crow attacks

### Tools & Equipment
- Hoe, Pickaxe, Axe, Watering Can, Fishing Rod, Scythe, Milk Pail, Shears
- Four upgrade tiers per tool: Copper → Iron → Gold → Iridium
- Upgrades purchased at the Blacksmith
- Tool energy cost decreases with corresponding skill level
- Trash cans return a percentage of an item's sell value on disposal, upgradeable for higher returns
- Backpacks expand inventory capacity: 12 → 24 → unlimited slots

### Energy & Skills
- Each player has 200 energy per day, consumed by actions and movement
- Fainting when energy hits zero: remaining turns are skipped, wake the next morning with 75% energy
- Four skill trees: Farming, Mining, Foraging, Fishing — each up to level 4
- Skill progression unlocks crafting recipes and reduces associated tool energy costs
- Skills panel with hover tooltips for each skill's current bonuses

### Crafting & Cooking
- In-home crafting system for tools, buildings, and farm equipment
- Recipes unlocked through shops, NPC interactions, or skill milestones
- Cooking system with a dedicated in-home refrigerator for ingredient storage
- Food grants energy and temporary buffs to skills or maximum energy cap
- Only the most recently eaten food's buff is active at any time

### Animal Husbandry
- Build barns and coops at chosen map locations
- Animals available: chickens, ducks, rabbits, cows, goats, sheep, pigs
- Friendship system affected by petting, feeding, outdoor access, and neglect
- Produce quality and secondary product availability scale with friendship level
- Sell animals at a price based on current friendship
- Milk pail for dairy animals, shears for sheep; pig products collected outdoors

### Fishing
- Fish near lakes, rivers, and the sea using different rod types
- Quantity and quality of catch scale with fishing skill and weather conditions
- Legendary fish become available at max fishing skill
- Interactive fishing mini-game: control a green tracking bar to keep the fish in range, fill a catch meter to land it or lose it
- Perfect catch (fish never leaves the bar) upgrades fish quality by one tier
- Five fish movement types: Mixed, Smooth, Sinker, Floater, Dart

### Processing Machines
- Artisan machines: Keg, Furnace, Fish Smoker, Bee House, and more
- Place machines anywhere on your farm; insert ingredients to begin processing
- Progress timer displayed above each active machine
- Right-click context menu: view recipe, cancel process, collect output, or instant-finish (cheat)

### Trading & Shops
- Seven shops in the NPC village: Blacksmith, JojaMart, Pierre's General Store, Carpenter's Shop, Fish Shop, Marnie's Ranch, Stardrop Saloon
- Each shop has its own hours, NPC owner, and inventory
- Daily purchase limits shared across all players in a session
- Shipping bins placed on the farm: items sold overnight with money arriving next morning
- Quality-based sell price multipliers: Regular → Silver → Gold → Iridium (1× to 2×)

### Player Interactions
- Friendship levels (0–4) between players, progressing through XP earned via interaction
- Chat, gift-giving, hugging, and item trading between nearby players
- Gifting a flower is required to advance to friendship level 3
- Marriage system: propose with a ring → shared farm, shared wallet, daily energy bonus from proximity
- Player-to-player trade system: offer or request items/gold, accept or reject, with full trade history
- Gift history with a rating system (1–5) affecting both players' friendship scores

### NPCs
- Five main NPCs: Sebastian, Abigail, Harvey, Leah, Robin
- Each NPC has unique dialogue that shifts based on season, weather, time of day, and friendship level
- Gift system: sending a favourite item grants bonus friendship points
- Three quests per NPC, unlocking progressively with friendship and time milestones
- Quest rewards: gold, items, recipes, and friendship boosts
- Quests can only be completed once per player; first to finish claims the reward

### Graphical Interface
- Animated character sprites with directional movement and walk cycles
- Real-time HUD: clock, date, season, weather icon, energy bar, money, and inventory hotbar
- Full inventory screen with scrollable item grid, skills panel, social tab, and minimap tab
- In-game terminal overlay for entering cheat codes via keyboard shortcut
- Crafting menu, cooking menu, tool selector, journal, and screenshot mode all accessible via hotkeys
- NPC dialogue bubbles and right-click context menus on characters and machines
- Visual feedback for animal petting, gift sending, marriage proposals, and player hugs
- Shop menus with filter toggles (all items / in-stock only), grayed-out unavailable items
- Machine progress bars and context menus with live status
- Game assets sourced from the Stardew Valley community asset pack

### Cheat Codes
- Advance time or date, set weather, set energy, add items to inventory, set friendship levels, trigger lightning at a specific tile, and more
- All cheat commands accessible through the in-game terminal overlay

---

## How to Run

```bash
Open in IntelliJ IDEA and run `GameServer.java` and then 'Lwjgl3Launcher.java' directly.

---
