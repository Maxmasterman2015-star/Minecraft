# Litematica Schematics for Ancient Cherry Blossom World Tree

## Overview

This directory contains **Litematica .litematic schematic files** for building the **Ancient Cherry Blossom World Tree** mega-build in **Minecraft Java 26.3 (Wilderness Bound)**.

All files use:
- **Data Version: 5023** (Minecraft 26.3)
- **Format: .litematic** (Gzip-compressed NBT)
- **Block State Format: id/properties** (26.3 standard)
- **Compatible with Litematica 0.29.1**

## Generated Files

| File | Dimensions | Size | Description |
|------|------------|------|-------------|
| `Stage_1_Terrain_Foundation.litematic` | 110 × 35 × 100 | 76 KB | Island terrain with cliffs, terraces, waterfalls |
| `Stage_2_Trunk_and_Roots.litematic` | 34 × 35 × 34 | 3 KB | Central trunk with 8 major roots |
| `Stage_3_Primary_Branches.litematic` | 100 × 60 × 100 | 3 KB | 7 primary branches radiating from trunk |
| `Stage_4_Secondary_Branches.litematic` | 100 × 40 × 100 | 2 KB | Secondary branches filling the network |
| `Stage_5_Blossom_Canopy.litematic` | 95 × 40 × 85 | 20 KB | 15 major blossom clusters |
| `Stage_6_Island_Details.litematic` | 110 × 35 × 100 | 11 KB | Waterfalls, cliffs, floating rocks |
| `Stage_7_Architecture.litematic` | 110 × 30 × 100 | 2 KB | Shrines, pagodas, bridges |
| `Stage_8_Lighting.litematic` | 110 × 90 × 100 | 5 KB | Lanterns, chains, glowstone, campfires |
| `Stage_9_Final_Detailing.litematic` | 110 × 35 × 100 | 2 KB | Vegetation and final details |
| `COMBINED_Complete_Build.litematic` | 110 × 90 × 100 | 37 KB | All 9 stages merged together |

**Total: 10 files, ~161 KB**

## Requirements

### Minecraft Version
- **Minecraft Java 26.3 (Wilderness Bound)** - Released September 15, 2026
- Minimum Java version: **Java SE 25**

### Mod Requirements
1. **Fabric Loader 0.19.5+** - [Download from fabricmc.net](https://fabricmc.net/)
2. **MaLiLib** - Required dependency for Litematica
3. **Litematica 0.29.1** - [Download from Modrinth](https://modrinth.com/mod/litematica/version/0.29.1)

## Installation Guide

### Step 1: Install Minecraft 26.3

1. Open the Minecraft Launcher
2. Select "Installations" tab
3. Click "New Installation"
4. Select version **26.3 (Wilderness Bound)**
5. Click "Create"
6. Launch the game once to download the version

### Step 2: Install Fabric Loader

1. Download **Fabric Loader 0.19.5+** from [fabricmc.net](https://fabricmc.net/)
2. Run the installer
3. Select Minecraft **26.3**
4. Click "Install"
5. Create a new Fabric profile in the launcher

### Step 3: Install Mods

1. Download these mods:
   - [MaLiLib](https://modrinth.com/mod/malilib) (latest for 26.3)
   - [Litematica 0.29.1](https://modrinth.com/mod/litematica/version/0.29.1) (or latest 26.3 version)

2. Place the .jar files in the `mods` folder:
   - Windows: `%appdata%\.minecraft\mods\`
   - Mac: `~/Library/Application Support/minecraft/mods/`
   - Linux: `~/.minecraft/mods/`

3. Launch Minecraft with the Fabric profile

### Step 4: Install Schematics

1. Create the schematics directory:
   - Windows: `%appdata%\.minecraft\litematica\schematics\`
   - Mac: `~/Library/Application Support/minecraft/litematica/schematics/`
   - Linux: `~/.minecraft/litematica/schematics/`

2. Copy all `.litematic` files from this directory into the schematics folder

3. Alternatively, you can place them in a subdirectory (e.g., `schematics/cherry_tree/`) and Litematica will still find them

## Using Litematica

### Controls (Default)
- **M** - Open/Close Litematica menu
- **Left Alt + M** - Toggle placement mode
- **Left Ctrl + M** - Toggle render mode
- **Mouse Wheel** - Cycle through loaded schematics
- **Left Click** - Place block
- **Right Click** - Remove block
- **Middle Click** - Move schematic

### Loading a Schematic

1. Press **M** to open Litematica
2. Click **"Load"** or **"Browse"**
3. Navigate to the schematic file
4. Click **"Load"**
5. The schematic will appear in your world

### Building

1. **Position the schematic**: Use middle-click and drag to move it
2. **Rotate if needed**: Use the rotation controls in the Litematica menu
3. **Enable placement mode**: Press **Left Alt + M** or click the placement button
4. **Build**: Left-click to place blocks, right-click to remove

### Build Order

Build the stages in this order:

1. **Stage 1: Terrain Foundation** - Creates the island base with cliffs, terraces, waterfalls
2. **Stage 2: Trunk and Roots** - Builds the central tree trunk with 8 major roots
3. **Stage 3: Primary Branches** - Adds 7 primary branches radiating from trunk
4. **Stage 4: Secondary Branches** - Fills out the branch network between primary branches
5. **Stage 5: Blossom Canopy** - Creates 15 major cherry blossom clusters
6. **Stage 6: Island Details** - Adds waterfalls, cliffs, floating rocks
7. **Stage 7: Architecture** - Adds shrines, pagodas, bridges, viewing platforms
8. **Stage 8: Lighting** - Adds lanterns, chains, glowstone, campfires
9. **Stage 9: Final Detailing** - Adds vegetation, petals, final touches

Each stage must be verified before moving to the next!

### Tips

- **Check each stage before moving to the next** - Verify the structure looks correct
- **Use the COMBINED_Complete_Build.litematic** file for a single placement of the entire build
- Each stage file can be loaded individually for step-by-step construction
- **Use render mode** (Left Ctrl + M) to see the schematic without placing blocks
- **Adjust position carefully** - Make sure each stage aligns with the previous one
- **Use creative mode** for easier building
- **Save frequently** - Litematica auto-saves your position

## Block State Format

All schematics use the **id/properties** format required by Minecraft 26.3:

```nbt
{
  "id": "minecraft:block_name",
  "properties": {
    "property_name": "value"
  }
}
```

Examples:
- Dark Oak Log (Y-axis): `{"id": "minecraft:dark_oak_log", "properties": {"axis": "y"}}`
- Dark Oak Stairs (North): `{"id": "minecraft:dark_oak_stairs", "properties": {"facing": "north", "half": "bottom"}}`
- Water: `{"id": "minecraft:water", "properties": {"level": "0"}}`

## Troubleshooting

### "Incompatible mod" error
- Make sure all mods are for **Minecraft 26.3**
- Check Fabric Loader version is **0.19.5+**
- Verify MaLiLib and Litematica versions match

### Schematic not loading
- Check the file is in the correct directory
- Verify the file extension is `.litematic` (not `.litematic.gz`)
- Try re-downloading the file

### Blocks appearing wrong
- Make sure you're using **Minecraft 26.3**
- Some blocks (poplar, dappled forest grass, etc.) are new in 26.3
- If blocks are missing, you may need a resource pack

### Performance issues
- Large schematics can cause lag
- Try reducing render distance
- Use "Simple" render mode in Litematica settings
- Allocate more RAM to Minecraft

## File Format Details

### Structure

```nbt
{
  "Metadata": {
    "Name": "Schematic Name",
    "Author": "Creator",
    "Description": "Description",
    "TimeCreated": 1234567890000,
    "TimeModified": 1234567890000,
    "MinecraftDataVersion": 5023,
    "LitematicaVersion": 6
  },
  "EnclosingSize": [width, height, depth],
  "Regions": [
    {
      "Name": "Region Name",
      "Position": [x, y, z],
      "Size": [width, height, depth],
      "BlockStatePalette": [
        {"id": "minecraft:air"},
        {"id": "minecraft:stone"},
        ...
      ],
      "BlockData": [0, 1, 2, ...],  // Indices into palette
      "Entities": [],
      "TileEntities": []
    }
  ]
}
```

### Coordinate System

- **Origin**: World coordinates (0, 0, 0) is at the schematic position
- **X**: East (positive) / West (negative)
- **Y**: Up (positive) / Down (negative)
- **Z**: South (positive) / North (negative)

## Version Information

- **Minecraft Version**: 26.3 (Wilderness Bound)
- **Data Version**: 5023
- **Protocol Version**: 777
- **Resource Pack Format**: 97.1
- **Data Pack Format**: 121.0
- **Minimum Java**: Java SE 25

## New Blocks in 26.3

These blocks are used in the schematics and are new to Minecraft 26.3:

- **Poplar Log/Planks/Wood** - New wood type from Dappled Forest biome
- **Poplar Leaves** - New leaf type
- **Dappled Forest Grass** - New grass variant
- **Red Shrub** - New decorative plant
- **Shelf Mushroom** - New mushroom type
- **Wool Stairs and Slabs** - Now craftable
- **Concrete Stairs and Slabs** - Now craftable

## Credits

- **Minecraft**: Mojang Studios
- **Litematica**: masa (original), sakura-ryoko (26.3 maintenance)
- **Fabric**: FabricMC team
- **This Build**: CherryBlossomBuilder

## License

These schematic files are provided as-is for personal use in Minecraft. You may:
- Use them in your own worlds
- Modify them as needed
- Share them with others

You may not:
- Sell these files
- Claim them as your own creation
- Use them in commercial projects without permission

## Support

For issues or questions:
- Check the [Litematica Wiki](https://github.com/masady/litematica/wiki)
- Ask on the [Litematica Discord](https://discord.gg/)
- Report issues with the schematic files in this repository

---

**Generated**: October 2026  
**Minecraft Version**: 26.3 Wilderness Bound  
**Litematica Version**: 0.29.1  
