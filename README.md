# Manwick Development Tools

Custom development tools and utilities for Manwick tactical shooter development.

## Overview

This repository contains specialized tools created to streamline Manwick development, including map editors, asset processors, build automation, and testing utilities.

## Tools Collection

### Map Development
- **[Map Editor](MapEditor/)** - Visual map creation and editing tool
- **[Tile Generator](TileGenerator/)** - Generate tile sets for maps
- **[Collision Generator](CollisionGenerator/)** - Automatic collision mesh generation
- **[Spawn Point Editor](SpawnPointEditor/)** - Configure spawn points and objectives

### Asset Processing
- **[Texture Packer](AssetProcessing/TexturePacker/)** - Pack sprites into atlases
- **[Audio Converter](AssetProcessing/AudioConverter/)** - Convert and optimize audio files
- **[Animation Builder](AssetProcessing/AnimationBuilder/)** - Create sprite animations
- **[Asset Validator](AssetProcessing/AssetValidator/)** - Validate asset formats and sizes

### Build Automation
- **[Build Scripts](BuildAutomation/Scripts/)** - Automated build processes
- **[Platform Packager](BuildAutomation/Packager/)** - Package for different platforms
- **[Version Manager](BuildAutomation/VersionManager/)** - Manage version numbers
- **[Release Publisher](BuildAutomation/ReleasePublisher/)** - Automated releases

### Testing & Quality Assurance
- **[Performance Profiler](Testing/Profiler/)** - Game performance analysis
- **[Memory Tracker](Testing/MemoryTracker/)** - Memory usage monitoring
- **[Network Tester](Testing/NetworkTester/)** - Multiplayer testing tools
- **[Automated Tester](Testing/AutomatedTester/)** - Automated gameplay testing

### Development Utilities
- **[Code Generator](Utilities/CodeGenerator/)** - Generate boilerplate code
- **[Config Manager](Utilities/ConfigManager/)** - Manage development configurations
- **[Log Analyzer](Utilities/LogAnalyzer/)** - Analyze game logs and crash reports
- **[Documentation Generator](Utilities/DocGenerator/)** - Generate API documentation

## Tool Categories

### Core Development Tools
These tools are essential for daily development work:

```
MapEditor/          # Visual map creation
AssetProcessing/    # Asset pipeline tools
BuildAutomation/    # Build and release tools
Testing/            # Quality assurance tools
```

### Utility Scripts
Helper scripts for common development tasks:

```
Scripts/
├── setup_dev_env.sh      # Development environment setup
├── asset_batch_process.py # Batch process assets
├── generate_builds.sh     # Generate all platform builds
├── run_tests.py          # Execute test suite
└── deploy_release.sh     # Deploy new release
```

## Installation & Setup

### Prerequisites
- Python 3.8+
- Node.js 16+
- Java JDK 21
- LibGDX development environment

### Quick Setup
```bash
git clone https://github.com/manwic/manwick-tools.git
cd manwick-tools
./setup.sh
```

### Manual Setup
```bash
# Install Python dependencies
pip install -r requirements.txt

# Install Node.js dependencies
npm install

# Configure tool paths
cp config/config.example.json config/config.json
# Edit config.json with your paths
```

## Usage Examples

### Map Editor
```bash
# Launch map editor
./MapEditor/map_editor.py

# Convert map to game format
./MapEditor/export_map.py --input factory_floor.map --output factory_floor.tmx
```

### Asset Processing
```bash
# Pack textures into atlas
./AssetProcessing/TexturePacker/pack_textures.py --input textures/ --output atlas.png

# Convert audio files
./AssetProcessing/AudioConverter/convert_audio.py --input audio_src/ --output audio/
```

### Build Automation
```bash
# Build all platforms
./BuildAutomation/Scripts/build_all.sh

# Create release package
./BuildAutomation/Packager/package_release.py --version 1.0.0
```

## Tool Development

### Creating New Tools
1. **Choose appropriate category** (MapEditor, AssetProcessing, etc.)
2. **Follow naming conventions** (PascalCase for directories, snake_case for scripts)
3. **Include comprehensive README** in tool directory
4. **Add configuration options** in config/tools.json
5. **Write tests** in tests/ directory

### Tool Structure Template
```
NewTool/
├── README.md              # Tool documentation
├── requirements.txt       # Dependencies
├── config/               # Configuration files
├── src/                  # Source code
├── tests/                # Unit tests
├── examples/             # Usage examples
└── docs/                 # Additional documentation
```

### Contributing Guidelines
- **Follow Python PEP 8** style guide
- **Include docstrings** for all functions
- **Write unit tests** for new functionality
- **Update documentation** when adding features
- **Test on multiple platforms** before submitting

## Tool Documentation

### Map Editor
**Purpose**: Create and edit game maps visually
**Input**: Image files, tile sets
**Output**: Game-ready map files
**Usage**: `./MapEditor/map_editor.py --new factory_map`

### Texture Packer
**Purpose**: Combine multiple textures into atlases
**Input**: Individual texture files
**Output**: Packed texture atlas + metadata
**Usage**: `./AssetProcessing/TexturePacker/pack.py --input textures/`

### Build Scripts
**Purpose**: Automate build process for all platforms
**Input**: Source code and assets
**Output**: Platform-specific builds
**Usage**: `./BuildAutomation/Scripts/build_all.sh --release`

## Configuration

### Global Configuration
Edit `config/config.json`:
```json
{
  "game_directory": "/path/to/manwick",
  "asset_directory": "/path/to/assets", 
  "build_directory": "/path/to/builds",
  "tools": {
    "map_editor": {
      "grid_size": 32,
      "default_tileset": "factory_tiles.png"
    }
  }
}
```

### Tool-Specific Configuration
Each tool has its own configuration in `config/tools/`:
- `map_editor.json` - Map editor settings
- `asset_processor.json` - Asset processing options
- `build_automation.json` - Build configuration

## Integration with Main Project

### Automatic Integration
Tools automatically detect the main Manwick project:
```bash
# Tools will automatically find project if in parent directory
manwick/              # Main game
manwick-tools/        # This repository
manwick-docs/         # Documentation
```

### Manual Configuration
If tools can't auto-detect, configure paths in `config/config.json`:
```json
{
  "manwick_project_path": "/full/path/to/manwick",
  "output_directory": "/full/path/to/manwick/assets"
}
```

## Platform Support

### Supported Platforms
- **Windows** (Primary development platform)
- **macOS** (Full support)
- **Linux** (Full support)

### Platform-Specific Tools
- **Windows**: .bat scripts for Windows-specific builds
- **macOS**: .app bundle creation tools
- **Linux**: AppImage and .deb package creation

## Troubleshooting

### Common Issues
1. **Tool not found**: Ensure tools directory is in PATH
2. **Permission denied**: Run `chmod +x` on script files
3. **Configuration errors**: Validate JSON configuration files
4. **Missing dependencies**: Run `pip install -r requirements.txt`

### Getting Help
- **Documentation**: Check tool-specific README files
- **Issues**: Report bugs on [GitHub Issues](https://github.com/manwic/manwick-tools/issues)
- **Community**: Join [Discord community](https://discord.gg/manwick)

---

**Manwick Development Team** | [Main Repository](https://github.com/manwic/manwick) | [Documentation](https://github.com/manwic/manwick-docs)