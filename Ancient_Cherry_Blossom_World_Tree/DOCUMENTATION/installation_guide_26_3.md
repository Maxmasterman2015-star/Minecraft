# LITEMATICA INSTALLATION GUIDE - MINECRAFT JAVA 26.3

## Complete Setup for Ancient Cherry Blossom World Tree Mega-Build

---

## 📋 Prerequisites

### System Requirements
- **Operating System**: Windows 10/11, macOS, or Linux
- **Java**: **Java SE 25 or newer** (REQUIRED for Minecraft 26.3)
- **Minecraft**: Java Edition 26.3 (Wilderness Bound)
- **Hardware**: 
  - Minimum 8GB RAM (16GB recommended for large schematics)
  - Modern CPU (Intel i5 / Ryzen 5 or better)
  - Dedicated GPU recommended for smooth rendering

---

## 🚀 Step 1: Install Java SE 25

### Check Current Java Version
Open Command Prompt (Windows) or Terminal (Mac/Linux) and run:
```bash
java -version
```

If you see version **25 or higher**, you're good to go. Otherwise, install Java 25.

### Download Java SE 25
1. Go to [Oracle Java Downloads](https://www.oracle.com/java/technologies/javase/jdk25-archive-downloads.html)
2. Or use [Adoptium Temurin](https://adoptium.net/temurin/releases/?version=25) (recommended)
3. Download the appropriate version for your OS

### Install Java
- **Windows**: Run the installer, follow prompts
- **macOS**: Run the .pkg installer
- **Linux**: Use your package manager or install from .tar.gz

### Verify Installation
```bash
java -version
# Should show: openjdk version "25" or similar
```

---

## 🎮 Step 2: Install Minecraft Java 26.3

### Method 1: Minecraft Launcher
1. Open **Minecraft Launcher**
2. Go to **Installations** tab
3. Click **New Installation**
4. Select **26.3** from the version list
5. Name it "26.3 Fabric" or similar
6. Click **Create**

### Method 2: Manual Download
1. Download **26.3 server.jar** from [Minecraft.net](https://www.minecraft.net/en-us/download/server)
2. Or get client files from [piston-data](https://piston-data.mojang.com/v1/objects/33680f5f2ac32864d6d7cf5e56a705fdb3e05f4c/server.jar)

### Verify Installation
1. Launch Minecraft 26.3 vanilla
2. Confirm version in title screen: **Minecraft 26.3**
3. Check for new features: Poplar wood, wool stairs, etc.

---

## 🧩 Step 3: Install Fabric Loader for 26.3

### Download Fabric
1. Go to [FabricMC.net](https://fabricmc.net/use/)
2. Select **Minecraft 26.3** from dropdown
3. Click **Download Installer**
4. Run the installer

### Install Fabric
1. Run the Fabric installer
2. Select **26.3** as Minecraft version
3. Check **Create new installation**
4. Name it "26.3 Fabric"
5. Click **Install**

### Verify Fabric
1. In Minecraft Launcher, select **26.3 Fabric** profile
2. Click **Play**
3. Check title screen shows **Fabric** in bottom right

---

## 📦 Step 4: Install Required Mods

### Mod List for 26.3

| Mod | Version | Required | Download |
|-----|---------|----------|----------|
| **Fabric API** | Latest for 26.3 | ✅ Yes | [Modrinth](https://modrinth.com/mod/fabric-api) |
| **MaLiLib** | Latest for 26.3 | ✅ Yes | [Modrinth](https://modrinth.com/mod/malilib) |
| **Litematica** | **0.29.0** | ✅ Yes | [Modrinth](https://modrinth.com/mod/litematica/version/0.29.0) |

### Installation Steps

#### Fabric API
1. Download **Fabric API** for 26.3 from Modrinth
2. Place `.jar` file in:
   - Windows: `%appdata%\.minecraft\mods\`
   - macOS: `~/Library/Application Support/minecraft/mods/`
   - Linux: `~/.minecraft/mods/`

#### MaLiLib
1. Download **MaLiLib** for 26.3
2. Place `.jar` file in the same `mods` folder

#### Litematica 0.29.0
1. Download **Litematica 0.29.0** (the version for 26.3)
2. Place `.jar` file in `mods` folder

### Folder Structure
```
.minecraft/
├── mods/
│   ├── fabric-api-0.x.x+1.26.3.jar
│   ├── malilib-0.x.x+1.26.3.jar
│   └── litematica-0.29.0+1.26.3.jar
├── schematics/
│   └── (your .litematic files go here)
└── ...
```

---

## 📁 Step 5: Create Schematics Folder

1. Navigate to your Minecraft folder
2. Create a folder named **schematics** (if it doesn't exist)
   - Windows: `%appdata%\.minecraft\schematics\`
   - macOS: `~/Library/Application Support/minecraft/schematics/`
   - Linux: `~/.minecraft/schematics/`

3. Copy all `.litematic` files from this project into the schematics folder

---

## ✅ Step 6: Verify Installation

### Launch Minecraft
1. Open Minecraft Launcher
2. Select **26.3 Fabric** profile
3. Click **Play**

### Check Mods Loaded
1. From main menu, click **Mods** button
2. Verify you see:
   - ✅ Fabric API
   - ✅ MaLiLib
   - ✅ Litematica

### Test Litematica
1. Press **M** key (default hotkey)
2. Litematica menu should appear
3. You should see your schematics listed

---

## 🎯 Step 7: Load and Use Schematics

### Loading a Schematic
1. Press **M** to open Litematica menu
2. Navigate to **Schematics** tab
3. Find your schematic (e.g., `stage_01_terrain.litematic`)
4. Click to **load** it

### Positioning the Schematic
1. Hold a **stick** (default tool item)
2. Right-click to **place** the schematic in the world
3. Use **M + G** to toggle schematic rendering on/off
4. Use **M + R** to rotate the schematic

### Building
1. Stand inside the schematic outline
2. Place blocks where you see the ghost blocks
3. Use **M + L** to show material list
4. Use **M + K** to toggle easy place mode

---

## 🎛️ Litematica Controls (Default)

### Main Controls
| Key | Action |
|-----|--------|
| **M** | Open Litematica menu |
| **M + G** | Toggle schematic rendering |
| **M + L** | Show material list |
| **M + K** | Toggle easy place mode |
| **M + R** | Rotate schematic |
| **M + F** | Toggle full block mode |
| **M + S** | Save current selection |
| **Ctrl + Alt + S** | Save schematic (area mode) |

### Area Selection
| Key | Action |
|-----|--------|
| **M + B** | Start area selection |
| **M + N** | New sub-region |
| **M + D** | Delete sub-region |
| **M + C** | Copy sub-region |

### Building Tools
| Key | Action |
|-----|--------|
| **M + T** | Cycle through tool modes |
| **M + Y** | Toggle layer mode |
| **M + U** | Toggle underground mode |
| **M + H** | Toggle hide mode |

---

## 📋 Step 8: Build the Cherry Blossom Tree

### Recommended Build Order

1. **Stage 1: Terrain Foundation** (`stage_01_terrain.litematic`)
   - Load and build the island base
   - Establish all three terrain levels
   - Create cliff faces and waterfall sources

2. **Stage 2: Trunk and Roots** (`stage_02_trunk_roots.litematic`)
   - Build central trunk from base up
   - Extend all 8 major roots
   - Verify trunk twist and gnarled details

3. **Stage 3: Primary Branches** (`stage_03_primary_branches.litematic`)
   - Add 7 major branches
   - Ensure proper angles and curves
   - Check balance from all four sides

4. **Stage 4: Secondary Branches** (`stage_04_secondary_branches.litematic`)
   - Fill out branch network
   - Add supports where needed

5. **Stage 5: Blossom Canopy** (`stage_05_canopy.litematic`)
   - Build 15 major blossom clusters
   - Check spacing and height
   - Verify color distribution

6. **Stage 6: Island Details** (`stage_06_island_details.litematic`)
   - Finish waterfalls
   - Add floating rocks
   - Create cliff details

7. **Stage 7: Architecture** (`stage_07_architecture.litematic`)
   - Build central shrine
   - Add pagodas and pavilions
   - Construct all bridges

8. **Stage 8: Lighting** (`stage_08_lighting.litematic`)
   - Add all lanterns
   - Hang chains from branches
   - Place glowstone and shroomlights

9. **Stage 9: Final Detailing** (`stage_09_final_detailing.litematic`)
   - Add moss and vegetation
   - Scatter pink petals
   - Final touch-ups

### Building Tips

1. **Use Layer Mode** (M + Y)
   - Build one Y-level at a time
   - Prevents floating blocks
   - Easier to follow structure

2. **Check Block States**
   - Stairs must face correct direction
   - Logs must have correct axis
   - Fences must connect properly

3. **Material List** (M + L)
   - Track required blocks
   - Plan resource gathering
   - Avoid running out mid-build

4. **Save Progress**
   - Regularly save your world
   - Consider using WorldEdit to backup sections

---

## 🔧 Troubleshooting

### Common Issues and Solutions

#### Issue: Litematica doesn't load
**Solution**:
- Verify Fabric is installed correctly
- Check all mod versions are for 26.3
- Ensure mods are in the correct folder
- Try reinstalling all mods

#### Issue: Schematic not appearing
**Solution**:
- Check file is in `.minecraft/schematics/`
- Verify file extension is `.litematic` (not `.litematic.txt`)
- Ensure you're holding a stick (tool item)
- Try reloading with **M + R**

#### Issue: "Unknown block" errors
**Solution**:
- Schematic was created for a different version
- Update Litematica to 0.29.0
- Check data version is 5023
- Some blocks may not exist in 26.3

#### Issue: Performance problems
**Solution**:
- Allocate more RAM to Minecraft (4-8GB)
- Reduce render distance
- Close other programs
- Split large schematics into smaller ones

#### Issue: Blocks appear wrong
**Solution**:
- Check block state strings in schematic
- Verify you're using correct Minecraft version
- Some blocks may have changed properties

### Verify Data Version
1. Open a schematic file with NBT editor
2. Check `MinecraftDataVersion` is **5023**
3. If not, the schematic needs to be updated

---

## 📊 Performance Optimization

### For Large Schematics (50,000+ blocks)

1. **Increase RAM Allocation**
   - In Minecraft Launcher:
     - Edit profile
     - More options
     - JVM Arguments: `-Xmx8G -Xms4G` (adjust as needed)

2. **Use Litematica Settings**
   - Press **M + O** for options
   - Reduce render distance for schematics
   - Disable unnecessary features

3. **Split Large Builds**
   - Build in stages (as provided)
   - Unload schematics when not in use
   - Only load 1-2 schematics at a time

4. **Graphics Settings**
   - Reduce graphics quality
   - Lower render distance
   - Use Optifine/Sodium for better performance

---

## 🎨 Optional Enhancements

### Resource Packs
For better visuals with 26.3 blocks:
- **Poplar Wood Pack**: Enhances new wood textures
- **Cherry Blossom Addon**: More pink variants
- **Vanilla Tweaks**: Better stairs and slabs

### Shaders (Compatible with 26.3)
- **BSL Shaders**
- **SEUS Renewed**
- **Complementary Shaders**
- **Sildur's Vibrant Shaders**

*Note: Some shader features may not work perfectly with Litematica rendering*

### Other Useful Mods
| Mod | Purpose | Download |
|-----|---------|----------|
| **MiniHUD** | Coordinates, light level | [Modrinth](https://modrinth.com/mod/minihud) |
| **WorldEdit** | Advanced building | [Modrinth](https://modrinth.com/mod/worldedit) |
| **Inventory Tweaks** | Better inventory | [Modrinth](https://modrinth.com/mod/inventory-tweaks) |
| **Sodium** | Performance boost | [Modrinth](https://modrinth.com/mod/sodium) |
| **Iris** | Shader support | [Modrinth](https://modrinth.com/mod/iris) |

---

## 📚 Version Compatibility Chart

| Minecraft | Fabric | MaLiLib | Litematica | Java |
|-----------|--------|---------|-----------|------|
| 26.3 | Latest | Latest | **0.29.0** | 25+ |
| 26.2 | Latest | Latest | 0.28.x | 25+ |
| 26.1 | Latest | Latest | 0.27.x | 25+ |

---

## 🔗 Important Links

- [Minecraft 26.3 Official Page](https://www.minecraft.net/en-us/article/minecraft-java-edition-26-3)
- [Minecraft Wiki 26.3](https://minecraft.wiki/w/Java_Edition_26.3)
- [FabricMC](https://fabricmc.net/)
- [Modrinth](https://modrinth.com/)
- [Litematica Modrinth](https://modrinth.com/mod/litematica)
- [MaLiLib Modrinth](https://modrinth.com/mod/malilib)
- [Fabric API Modrinth](https://modrinth.com/mod/fabric-api)

---

## ✅ Final Checklist

Before starting the build, verify:

- [ ] Java SE 25 or newer installed
- [ ] Minecraft 26.3 installed
- [ ] Fabric Loader installed
- [ ] Fabric API installed
- [ ] MaLiLib installed
- [ ] Litematica 0.29.0 installed
- [ ] All `.litematic` files in schematics folder
- [ ] Minecraft launches with all mods loaded
- [ ] Litematica menu opens with M key
- [ ] Schematics appear in Litematica list
- [ ] Schematic renders correctly in world

---

**Document Version**: 1.0.0  
**Last Updated**: 2026  
**Minecraft Version**: **26.3 (Wilderness Bound)**  
**Litematica Version**: **0.29.0**  
**Data Version**: **5023**
