# LITEMATICA FILE FORMAT GUIDE - MINECRAFT JAVA 26.3 (WILDERNESS BOUND)

## Complete Specification for .litematic Files in Minecraft 26.3

---

## 📋 Overview

**Minecraft Java 26.3** (Wilderness Bound) was released on **September 15, 2026**. This version introduced:
- New **dappled forest biome** with poplar wood
- **Red shrubs** and **shelf mushrooms**
- **Wool stairs and slabs** (all 16 colors)
- **Concrete stairs and slabs**
- **Straw beds** and **cushions**
- **Abandoned camps** structure
- New **/compute** and **/posteffect** commands
- **Data Pack Format**: 121.0
- **Resource Pack Format**: 97.1
- **Protocol Version**: 777
- **Data Version**: 5023

The `.litematic` file format remains compatible with **Litematica 0.29.0+** for Fabric.

---

## 🏗️ File Structure for Minecraft 26.3

### Physical Format
- **File Extension**: `.litematic`
- **Compression**: Gzip-compressed NBT
- **Encoding**: Big-endian NBT (standard Minecraft format)
- **Minecraft Data Version**: **5023** (for 26.3)

### Logical Structure
```
.litematic file
└── NBT Compound Root
    ├── Metadata (Compound)
    │   ├── Schematic information
    │   ├── Version data (Litematica + Minecraft 26.3)
    │   └── Timestamps
    └── Regions (List of Compounds)
        └── Region N
            ├── Position (List of Ints) [X, Y, Z]
            ├── Size (List of Ints) [Width, Height, Length]
            ├── BlockStatePalette (List of Strings)
            │   └── Block states with 26.3 properties
            ├── BlockData (Byte Array)
            │   └── Bit-packed indices into palette
            ├── Entities (List of Compounds)
            ├── TileEntities (List of Compounds)
            ├── PendingBlockTicks (List)
            └── PendingFluidTicks (List)
```

---

## 📊 Metadata Structure for 26.3

### Root Level Metadata

```nbt
{
    "Metadata": {
        // User-defined information
        "Name": "Ancient Cherry Blossom World Tree",
        "Description": "Mega-build for Minecraft Java 26.3",
        "Author": "Vibe Code",
        "Image": "Base64 preview image",  // Optional
        
        // Automatic timestamps (Unix milliseconds)
        "TimeCreated": 1726400000000,  // Example: Sept 15, 2026
        "TimeModified": 1726400000000,
        
        // Version information for 26.3
        "LitematicaVersion": "0.29.0",  // Latest for 26.3
        "MinecraftDataVersion": 5023,   // REQUIRED for 26.3
        
        // Calculated enclosure data
        "Enclosure": {
            "MinX": -55,
            "MinY": 25,
            "MinZ": -50,
            "MaxX": 55,
            "MaxY": 115,
            "MaxZ": 50,
            "Width": 110,
            "Height": 90,
            "Length": 100
        },
        
        // Statistics
        "TotalBlocks": 50000,
        "TotalVolume": 990000,
        "Software": "Litematica 0.29.0"
    }
}
```

### Key Version Numbers for 26.3

| Version Type | Number | Purpose |
|--------------|--------|---------|
| **Data Version** | **5023** | Block states, IDs, NBT structure |
| Resource Pack Format | 97.1 | Texture and model formats |
| Data Pack Format | **121.0** | Advancements, recipes, functions |
| Protocol Version | 777 | Network communication |
| Minimum Java | **Java SE 25** | Required to run |

---

## 🗺️ Region Structure

### Region Overview
Each `.litematic` file can contain multiple regions. For the Cherry Blossom Tree mega-build, we use **9 separate regions** (one per construction stage).

### Region Compound for 26.3

```nbt
{
    "Regions": [
        {
            "Name": "stage_01_terrain",
            "Position": [0, 25, 0],      // Origin relative to schematic
            "Size": [110, 35, 100],     // [Width, Height, Length]
            
            // Block State Palette with 26.3 blocks
            "BlockStatePalette": [
                "minecraft:air",
                "minecraft:grass_block",
                "minecraft:stone",
                "minecraft:dappled_forest_grass",  // NEW in 26.3
                "minecraft:poplar_log[axis=y]",    // NEW in 26.3
                // ... all other block states
            ],
            
            // Bit-packed block indices
            "BlockData": [Byte...],
            
            "Entities": [],
            "TileEntities": [],
            "PendingBlockTicks": [],
            "PendingFluidTicks": []
        }
    ]
}
```

---

## 🎨 Block State Palette for 26.3

### New Blocks in 26.3 Available for Use

#### Poplar Wood Set (NEW)
```
"minecraft:poplar_log[axis=x]"
"minecraft:poplar_log[axis=y]"
"minecraft:poplar_log[axis=z]"
"minecraft:stripped_poplar_log[axis=x]"
"minecraft:stripped_poplar_log[axis=y]"
"minecraft:stripped_poplar_log[axis=z]"
"minecraft:poplar_wood"
"minecraft:stripped_poplar_wood"
"minecraft:poplar_planks"
"minecraft:poplar_stairs[facing=north,half=bottom]"
"minecraft:poplar_stairs[facing=south,half=bottom]"
// ... all 4 directions and both halves
"minecraft:poplar_slab[type=bottom]"
"minecraft:poplar_slab[type=top]"
"minecraft:poplar_slab[type=double]"
"minecraft:poplar_fence"
"minecraft:poplar_fence_gate"
"minecraft:poplar_door[facing=north,half=lower,open=false]"
"minecraft:poplar_trapdoor[facing=north,half=bottom,open=false]"
"minecraft:poplar_button[facing=ceiling,powered=false]"
"minecraft:poplar_pressure_plate[powered=false]"
"minecraft:poplar_sign[rotation=0]"
"minecraft:poplar_hanging_sign[rotation=0,attached=false]"
```

#### Poplar Leaves (3 Colors - NEW)
```
"minecraft:poplar_leaves[color=red,persistent=false]"
"minecraft:poplar_leaves[color=orange,persistent=false]"
"minecraft:poplar_leaves[color=yellow,persistent=false]"
"minecraft:poplar_leaves[color=red,persistent=true]"
"minecraft:poplar_leaves[color=orange,persistent=true]"
"minecraft:poplar_leaves[color=yellow,persistent=true]"
```

#### Red Shrub (NEW)
```
"minecraft:red_shrub[age=0]"
"minecraft:red_shrub[age=1]"
"minecraft:red_shrub[age=2]"
```

#### Shelf Mushroom (2 Sizes - NEW)
```
"minecraft:shelf_mushroom[size=small,axis=y]"
"minecraft:shelf_mushroom[size=large,axis=y]"
"minecraft:shelf_mushroom[size=small,axis=x]"
"minecraft:shelf_mushroom[size=large,axis=x]"
"minecraft:shelf_mushroom[size=small,axis=z]"
"minecraft:shelf_mushroom[size=large,axis=z]"
```

#### Wool Stairs and Slabs (16 Colors - NEW)
```
// White wool stairs
"minecraft:white_wool_stairs[facing=north,half=bottom]"
"minecraft:white_wool_stairs[facing=north,half=top]"
// ... all 4 directions

// Pink wool stairs (useful for cherry blossom theme)
"minecraft:pink_wool_stairs[facing=north,half=bottom]"
"minecraft:pink_wool_stairs[facing=north,half=top]"
// ... all 4 directions

// All colors: white, orange, magenta, light_blue, yellow, lime, pink, gray, light_gray, cyan, purple, blue, brown, green, red, black

// Wool slabs
"minecraft:white_wool_slab[type=bottom]"
"minecraft:white_wool_slab[type=top]"
"minecraft:white_wool_slab[type=double]"
// ... all 16 colors
```

#### Concrete Stairs and Slabs (NEW)
```
"minecraft:white_concrete_stairs[facing=north,half=bottom]"
"minecraft:white_concrete_stairs[facing=north,half=top]"
// ... all 16 colors, all directions

"minecraft:white_concrete_slab[type=bottom]"
"minecraft:white_concrete_slab[type=top]"
"minecraft:white_concrete_slab[type=double]"
// ... all 16 colors
```

#### Straw Bed (NEW)
```
"minecraft:straw_bed[facing=north,part=head]"
"minecraft:straw_bed[facing=north,part=foot]"
"minecraft:straw_bed[facing=south,part=head]"
"minecraft:straw_bed[facing=south,part=foot]"
"minecraft:straw_bed[facing=east,part=head]"
"minecraft:straw_bed[facing=east,part=foot]"
"minecraft:straw_bed[facing=west,part=head]"
"minecraft:straw_bed[facing=west,part=foot]"
```

#### Cushion (NEW - Entity, not block)
Cushions are entities, not blocks. They would be stored in the `Entities` list:
```nbt
"Entities": [
    {
        "Id": "minecraft:cushion",
        "Pos": [0.5, 61.0, -7.5],
        "BlockPos": [0, 61, -7],
        "Color": "pink"  // or any of 16 colors
    }
]
```

---

## 🌳 Cherry Blossom Tree Block Palette (26.3 Compatible)

### Trunk & Roots Blocks

```nbt
// Existing blocks (still available in 26.3)
"minecraft:dark_oak_log[axis=x]"
"minecraft:dark_oak_log[axis=y]"
"minecraft:dark_oak_log[axis=z]"
"minecraft:stripped_dark_oak_log[axis=x]"
"minecraft:stripped_dark_oak_log[axis=y]"
"minecraft:stripped_dark_oak_log[axis=z]"
"minecraft:spruce_log[axis=x]"
"minecraft:spruce_log[axis=y]"
"minecraft:spruce_log[axis=z]"
"minecraft:deepslate"
"minecraft:mud_bricks"
"minecraft:mangrove_roots[axis=x]"
"minecraft:mangrove_roots[axis=y]"
"minecraft:mangrove_roots[axis=z]"

// Stairs and slabs
"minecraft:dark_oak_stairs[facing=north,half=bottom]"
"minecraft:dark_oak_stairs[facing=south,half=bottom]"
"minecraft:dark_oak_stairs[facing=east,half=bottom]"
"minecraft:dark_oak_stairs[facing=west,half=bottom]"
"minecraft:dark_oak_stairs[facing=north,half=top]"
"minecraft:dark_oak_stairs[facing=south,half=top]"
"minecraft:dark_oak_stairs[facing=east,half=top]"
"minecraft:dark_oak_stairs[facing=west,half=top]"

"minecraft:dark_oak_slab[type=bottom]"
"minecraft:dark_oak_slab[type=top]"
"minecraft:dark_oak_slab[type=double]"
```

### Canopy Blocks (Cherry Blossom)

```nbt
// Cherry leaves (existing)
"minecraft:cherry_leaves[persistent=false]"
"minecraft:cherry_leaves[persistent=true]"

// Pink wool variants
"minecraft:pink_wool"
"minecraft:white_wool"
"minecraft:magenta_wool"

// Terracotta variants
"minecraft:pink_terracotta"
"minecraft:magenta_terracotta"
"minecraft:white_terracotta"

// Concrete variants
"minecraft:pink_concrete"
"minecraft:magenta_concrete"
"minecraft:white_concrete"

// NEW in 26.3: Wool stairs and slabs for canopy details
"minecraft:pink_wool_stairs[facing=north,half=bottom]"
"minecraft:pink_wool_stairs[facing=south,half=bottom]"
"minecraft:pink_wool_slab[type=bottom]"
"minecraft:pink_wool_slab[type=top]"

// NEW: Concrete stairs and slabs
"minecraft:pink_concrete_stairs[facing=north,half=bottom]"
"minecraft:pink_concrete_slab[type=bottom]"
```

### Terrain Blocks

```nbtn// Standard terrain
"minecraft:grass_block"
"minecraft:stone"
"minecraft:andesite"
"minecraft:diorite"
"minecraft:granite"
"minecraft:moss_block"
"minecraft:mossy_cobblestone"
"minecraft:coarse_dirt"
"minecraft:rooted_dirt"
"minecraft:deepslate"
"minecraft:deepslate_bricks"
"minecraft:tuff"
"minecraft:gravel"
"minecraft:sand"

// NEW in 26.3: Dappled forest blocks
"minecraft:dappled_forest_grass"  // Special grass variant
// Note: Poplar wood can also be used for terrain details

// Stairs and slabs
"minecraft:stone_brick_stairs[facing=north,half=bottom]"
"minecraft:stone_brick_slab[type=bottom]"
"minecraft:mossy_stone_brick_stairs[facing=north,half=bottom]"
```

### Architecture Blocks

```nbt
// Wood
"minecraft:dark_oak_planks"
"minecraft:spruce_planks"
"minecraft:cherry_planks"  // Existing from 1.20
"minecraft:poplar_planks"  // NEW in 26.3

// Stairs and slabs
"minecraft:dark_oak_stairs[facing=north,half=bottom]"
"minecraft:spruce_stairs[facing=north,half=bottom]"
"minecraft:cherry_stairs[facing=north,half=bottom]"
"minecraft:poplar_stairs[facing=north,half=bottom]"  // NEW

"minecraft:dark_oak_slab[type=bottom]"
"minecraft:spruce_slab[type=bottom]"
"minecraft:cherry_slab[type=bottom]"
"minecraft:poplar_slab[type=bottom]"  // NEW

// Stone
"minecraft:stone_bricks"
"minecraft:mossy_stone_bricks"
"minecraft:polished_andesite"
"minecraft:deepslate_tiles"

// Fences and walls
"minecraft:dark_oak_fence"
"minecraft:spruce_fence"
"minecraft:cherry_fence"
"minecraft:poplar_fence"  // NEW

// Trapdoors
"minecraft:dark_oak_trapdoor[facing=north,half=bottom,open=false]"
"minecraft:spruce_trapdoor[facing=north,half=bottom,open=false]"
```

### Lighting Blocks

```nbt
// Lanterns
"minecraft:lantern[hanging=true]"
"minecraft:lantern[hanging=false]"
"minecraft:soul_lantern[hanging=true]"
"minecraft:soul_lantern[hanging=false]"

// Chains
"minecraft:chain[axis=x]"
"minecraft:chain[axis=y]"
"minecraft:chain[axis=z]"

// Light sources
"minecraft:glowstone"
"minecraft:shroomlight"
"minecraft:sea_lantern"

// Campfires
"minecraft:campfire[facing=north,lit=true]"
"minecraft:campfire[facing=north,lit=false]"

// NEW in 26.3: Glow lichen variants
"minecraft:glow_lichen"
```

### Vegetation Blocks

```nbt
// Flowers
"minecraft:pink_tulip"
"minecraft:peony"
"minecraft:azalea"
"minecraft:flowering_azalea"

// NEW in 26.3
"minecraft:red_shrub[age=0]"
"minecraft:red_shrub[age=1]"
"minecraft:red_shrub[age=2]"
"minecraft:shelf_mushroom[size=small,axis=y]"
"minecraft:shelf_mushroom[size=large,axis=y]"

// Existing
"minecraft:moss_carpet"
"minecraft:fern"
"minecraft:tall_grass[half=lower]"
"minecraft:tall_grass[half=upper]"
"minecraft:bamboo"

// Cherry saplings
"minecraft:cherry_sapling"
```

### Water Blocks

```nbt
"minecraft:water[level=0]"
"minecraft:water[level=1]"
// ... up to level=15
```

---

## 💾 Block Data Encoding

### Encoding Scheme (Same as previous versions)

#### For Palettes ≤ 256 States
- **Bits per Index**: 8 bits (1 byte)
- **Storage**: 1 byte per block
- **Max Palette Size**: 256 entries

#### For Palettes > 256 States (Recommended for mega-builds)
- **Bits per Index**: 16 bits (2 bytes)
- **Storage**: 2 bytes per block
- **Max Palette Size**: 65,536 entries
- **Recommended for Cherry Blossom Tree**: ~300-400 unique block states

### Bit-Packing Calculation

For the Cherry Blossom Tree:
- **Estimated Unique Block States**: ~350
- **Bits Needed**: ceil(log2(350)) = 9 bits
- **Storage per Block**: 2 bytes (16 bits)
- **Total Blocks**: ~50,000
- **BlockData Size**: 50,000 × 2 = 100,000 bytes ≈ 100 KB

---

## 🎯 Coordinate Systems

### Schematic Coordinates
- **Origin**: Typically the lowest northwest corner
- **Axes**:
  - **X**: East (positive) / West (negative)
  - **Y**: Up (positive) / Down (negative)
  - **Z**: South (positive) / North (negative)

### Region Coordinates
Each region has:
1. **Position**: `[X, Y, Z]` - origin relative to schematic origin
2. **Size**: `[Width, Height, Length]` - dimensions
3. **Internal Coordinates**: 0 to Width-1, 0 to Height-1, 0 to Length-1

### Example for Cherry Blossom Tree

```nbt
// Stage 1: Terrain Foundation
{
    "Name": "stage_01_terrain",
    "Position": [0, 25, 0],
    "Size": [110, 35, 100]
    // Covers X:0-109, Y:25-59, Z:0-99
}

// Stage 2: Trunk and Roots
{
    "Name": "stage_02_trunk_roots",
    "Position": [-8, 60, -8],
    "Size": [17, 35, 17]
    // Covers X:-8 to +8, Y:60-94, Z:-8 to +8
}

// Stage 5: Canopy
{
    "Name": "stage_05_canopy",
    "Position": [-47, 65, -42],
    "Size": [95, 30, 85]
    // Covers the entire canopy area
}
```

---

## 🏷️ Block State String Format (26.3)

### Standard Format
```
namespace:id[property1=value1,property2=value2,...]
```

### New Properties in 26.3

#### Poplar Leaves
```
"minecraft:poplar_leaves[color=red,persistent=false]"
// color: red, orange, yellow
// persistent: true, false
```

#### Shelf Mushroom
```
"minecraft:shelf_mushroom[size=small,axis=y]"
// size: small, large
// axis: x, y, z
```

#### Red Shrub
```
"minecraft:red_shrub[age=0]"
// age: 0, 1, 2
```

#### Wool Stairs
```
"minecraft:pink_wool_stairs[facing=north,half=bottom]"
// facing: north, south, east, west
// half: bottom, top
```

#### Concrete Stairs
```
"minecraft:pink_concrete_stairs[facing=north,half=bottom]"
```

#### Straw Bed
```
"minecraft:straw_bed[facing=north,part=head]"
// facing: north, south, east, west
// part: head, foot
```

---

## 🧱 Tile Entities in 26.3

### New Tile Entities

#### Poplar Sign
```nbt
{
    "Id": "minecraft:poplar_sign",
    "Pos": [0, 61, -10],
    "x": 0,
    "y": 61,
    "z": -10,
    "Text1": '{"text":"Ancient Cherry Tree"}',
    "Text2": '{"text":"Built by Vibe Code"}',
    "Text3": '{"text":""}',
    "Text4": '{"text":""}',
    "Color": "pink",
    "GlowingText": false
}
```

#### Poplar Hanging Sign
```nbt
{
    "Id": "minecraft:poplar_hanging_sign",
    "Pos": [5, 65, 0],
    "x": 5,
    "y": 65,
    "z": 0,
    "Text1": '{"text":"Welcome"}',
    "Rotation": 0,
    "Attached": false,
    "Color": "pink",
    "GlowingText": false
}
```

### Existing Tile Entities (Still Valid)
- Chests
- Furnaces
- Campfires
- Bells
- Barrels
- etc.

---

## 👻 Entities in 26.3

### New Entities

#### Cushion Entity
```nbt
{
    "Id": "minecraft:cushion",
    "Pos": [0.5, 61.0, -7.5],
    "BlockPos": [0, 61, -7],
    "Color": "pink"  // 16 color variants
}
```

#### Poplar Boat
```nbt
{
    "Id": "minecraft:poplar_boat",
    "Pos": [10.5, 60.5, 10.5],
    "Rotation": [90.0, 0.0],
    "Motion": [0.0, 0.0, 0.0]
}
```

#### Poplar Boat with Chest
```nbt
{
    "Id": "minecraft:poplar_chest_boat",
    "Pos": [15.5, 60.5, 15.5],
    "Rotation": [0.0, 0.0],
    "Items": []
}
```

---

## 📦 Complete Example for 26.3

Here's a simplified example using new 26.3 blocks:

```nbt
{
    "Metadata": {
        "Name": "Cherry Tree with Poplar Accents",
        "Description": "Test file using Minecraft 26.3 blocks",
        "Author": "Vibe Code",
        "TimeCreated": 1726400000000,
        "TimeModified": 1726400000000,
        "LitematicaVersion": "0.29.0",
        "MinecraftDataVersion": 5023,  // REQUIRED for 26.3
        "Enclosure": {
            "MinX": -1,
            "MinY": 60,
            "MinZ": -1,
            "MaxX": 1,
            "MaxY": 62,
            "MaxZ": 1,
            "Width": 3,
            "Height": 3,
            "Length": 3
        },
        "TotalBlocks": 5,
        "TotalVolume": 27,
        "Software": "Litematica 0.29.0"
    },
    "Regions": [
        {
            "Name": "test_region",
            "Position": [-1, 60, -1],
            "Size": [3, 3, 3],
            "BlockStatePalette": [
                "minecraft:air",
                "minecraft:dark_oak_log[axis=y]",
                "minecraft:cherry_leaves[persistent=true]",
                "minecraft:poplar_planks",  // NEW in 26.3
                "minecraft:pink_wool_stairs[facing=north,half=bottom]"  // NEW in 26.3
            ],
            "BlockData": [
                // 3x3x3 = 27 blocks
                // Layer 1 (Y=60):
                0, 0, 0,
                0, 1, 0,  // Center: dark_oak_log
                0, 0, 0,
                
                // Layer 2 (Y=61):
                0, 0, 0,
                0, 2, 0,  // Center: cherry_leaves
                0, 0, 0,
                
                // Layer 3 (Y=62):
                0, 0, 0,
                0, 4, 0,  // Center: pink_wool_stairs
                0, 0, 0
            ],
            "Entities": [],
            "TileEntities": [],
            "PendingBlockTicks": [],
            "PendingFluidTicks": []
        }
    ]
}
```

---

## 🔧 Creating .litematic Files for 26.3

### Method 1: In-Game with Litematica 0.29.0
1. **Install Fabric Loader** for Minecraft 26.3
2. **Install MaLiLib** (required dependency)
3. **Install Litematica 0.29.0** (latest for 26.3)
4. Build your structure in creative mode
5. Select area with Litematica's area selection tool
6. Press **Ctrl+Alt+S** to save schematic
7. File saved to `.minecraft/schematics/`

### Method 2: Programmatic with Litemapy

```python
from litemapy import Schematic, Region, BlockState

# Create schematic for 26.3
schematic = Schematic()
schematic.metadata.name = "Cherry Tree Stage 1"
schematic.metadata.author = "Vibe Code"
schematic.metadata.description = "Terrain Foundation for 26.3"
schematic.metadata.minecraft_data_version = 5023  # REQUIRED for 26.3
schematic.metadata.litematica_version = "0.29.0"

# Create region
region = Region((0, 25, 0), (110, 35, 100))

# Add blocks including 26.3 blocks
region.set_block((0, 60, 0), BlockState("minecraft:dark_oak_log[axis=y]"))
region.set_block((5, 65, 0), BlockState("minecraft:poplar_planks"))  # NEW
region.set_block((10, 62, 0), BlockState("minecraft:pink_wool_stairs[facing=north,half=bottom]"))  # NEW

# Add to schematic
schematic.add_region(region)

# Save
schematic.save("stage_01_terrain_26_3.litematic")
```

### Method 3: Manual NBT Creation
1. Create NBT structure with correct data version (5023)
2. Include all block states with proper properties
3. Compress with gzip
4. Save with `.litematic` extension

---

## 📥 Loading .litematic Files in 26.3

### Installation
1. **Minecraft Java 26.3** installed
2. **Java SE 25** or newer (required for 26.3)
3. **Fabric Loader** for 26.3
4. **Fabric API**
5. **MaLiLib** (required)
6. **Litematica 0.29.0**

### Steps
1. Place `.litematic` file in `.minecraft/schematics/`
2. Launch Minecraft 26.3 with Fabric profile
3. Press **M** to open Litematica menu
4. Select schematic from list
5. Position with tool item (default: stick)
6. Toggle rendering with **M + G**

---

## 🎯 Best Practices for 26.3

### Block Selection
1. **Use Poplar Wood**: For new builds, consider using poplar wood for variation
2. **Wool Stairs**: Use pink wool stairs for canopy details
3. **Compatibility**: All old blocks still work in 26.3
4. **New Features**: Take advantage of shelf mushrooms and red shrubs for decoration

### Performance
1. **Region Size**: Keep individual regions under 100×100×100
2. **Palette Size**: Optimize block state palette (300-400 entries typical)
3. **File Size**: Large schematics can be 10-50 MB

### Version Compatibility
- **Litematica 0.29.0**: Fully supports 26.3
- **Data Version**: Must be 5023 for 26.3 schematics
- **Backward Compatibility**: 26.3 can load older schematics (with warnings)

---

## 🔍 Troubleshooting for 26.3

### Common Issues

**Issue: "Unknown block" errors**
- Ensure data version is set to **5023**
- Check block state strings for 26.3 compatibility
- Verify all blocks exist in 26.3

**Issue: Schematic doesn't load**
- Check Litematica version (must be 0.29.0+)
- Verify Minecraft version is exactly 26.3
- Ensure file is in correct folder
- Check for corruption

**Issue: Missing new blocks**
- Update resource packs if using custom textures
- Ensure game is fully updated to 26.3

**Issue: Performance problems**
- Reduce number of loaded schematics
- Split large builds into smaller regions
- Use simpler block states where possible

---

## 📚 References for 26.3

- [Minecraft Java 26.3 Wiki](https://minecraft.wiki/w/Java_Edition_26.3)
- [Litematica Modrinth](https://modrinth.com/mod/litematica/version/0.29.0)
- [Litemapy Documentation](https://litemapy.readthedocs.io/)
- [Minecraft Data Versions](https://minecraft.wiki/w/Data_version)
- [FabricMC](https://fabricmc.net/)

---

## 📊 Version Summary

| Component | Version for 26.3 |
|-----------|------------------|
| Minecraft Java | 26.3 |
| Data Version | **5023** |
| Resource Pack Format | 97.1 |
| Data Pack Format | **121.0** |
| Protocol Version | 777 |
| Litematica | 0.29.0+ |
| MaLiLib | Latest for 26.3 |
| Fabric Loader | Latest for 26.3 |
| Java SE | 25+ |

---

**Document Version**: 1.0.0  
**Last Updated**: 2026  
**Minecraft Version**: **26.3 (Wilderness Bound)**  
**Data Version**: **5023**  
**Litematica Version**: **0.29.0+**
