# Custom Entity & Humanoid Framework (Luau)

A highly optimized, custom NPC architecture built for an MMORPG environment in Roblox Studio. This framework completely bypasses the native, memory-heavy Humanoid systems to achieve massive scalability and server-side authority.

## 🚀 Performance Showcase
**[Insert Link to GIF/Video of 10k+ AI Stress Test Here]**
*Stress testing the framework: Successfully handling 10,000+ active AI entities simultaneously with stable server compute times and zero frame degradation.*

## ⚙️ Core Architecture & Optimizations

This framework was built from the ground up to solve the native engine limitations of handling large volumes of active entities. 

* **Spatial Partitioning (Linked List Grid):** Implemented a custom 2D grid system to manage entity locations. This reduces the $O(N^2)$ distance-checking problem for aggro and sleep states by ensuring entities only query their immediate neighboring cells.
* **Byte-Level Networking:** Utilizes `buffer` creation to serialize and compress entity data (ID, X, Y, Z positions) before transmission. This significantly reduces server-to-client network packet size compared to sending standard tables or objects.
* **Custom Physics & Raycasting:** Replaced expensive native physics calculations with custom CFrame math, Blockcasting, and basic velocity management, heavily reducing server memory leaks and thread exhaustion.
* **Bitwise State Management:** Manages AI states (`Idle`, `Grounded`, `Sleeping`, `Aggro`, etc.) using bit32 operations (`bit32.bor`, `bit32.band`), ensuring a microscopic memory footprint per entity.
* **Dynamic Sleep/Awake Culling:** Entities dynamically enter a "Sleeping" state and are removed from the active update loop when no players are within their partitioned render distance, saving massive compute cycles.

## 📂 Code Structure

* **`Main.server.lua`:** The heartbeat loop that iterates through active entities and handles the buffered network replication to clients at a controlled rate (10Hz).
* **`AIBase.lua`:** The core metamethod class defining all base entity logic, physics updates, flag management, and health/damage processing.
* **`AggroAI.lua` / `Slime.lua`:** Example inheritance classes demonstrating how to extend the base entity to create specific enemy types with unique behaviors (e.g., target finding, custom attack physics).
* **`LinkedListGrid.lua`:** The spatial partitioning module handling the allocation and querying of entities within the map matrix.

## 🛠️ Tech Stack
* **Language:** Luau (Roblox Lua)
* **Paradigms:** Object-Oriented Programming (OOP), Client-Server Model
* **Tools:** Roblox Studio, MicroProfiler (for optimization validation)
