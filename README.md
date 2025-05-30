# Piper TTS - ARM64 Static Binaries for Apple Silicon

<div align="center">

[![ARM64](https://img.shields.io/badge/ARM64-Apple%20Silicon-green?style=for-the-badge&logo=apple)](https://github.com/yourusername/piper-arm64)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)
[![GitHub Release](https://img.shields.io/github/v/release/yourusername/piper-arm64?style=for-the-badge)](https://github.com/yourusername/piper-arm64/releases)

**High-quality, fast text-to-speech for Apple Silicon Macs**

[Download](#download) • [Quick Start](#quick-start) • [Build Methods](#build-methods) • [⭐ Star Repository](#support-this-project) • [Support](#support-this-project)

</div>

---

## About

Piper is a fast, local neural text-to-speech system that produces high-quality synthetic speech. This repository provides pre-built ARM64 static binaries specifically optimized for Apple Silicon Macs (M1/M2/M3/M4 chips).

### Key Features

- **Native ARM64 Performance** - Fully optimized for Apple Silicon architecture
- **Self-Contained Executable** - No Python installation or dependencies required
- **High-Quality Voice Synthesis** - Neural network-based text-to-speech
- **Lightweight & Fast** - Minimal system resources required
- **Command-Line Interface** - Simple integration into scripts and workflows

## Download

### Latest Release

Download the latest pre-built binaries from the [Releases](https://github.com/yourusername/piper-arm64/releases) page.

Available downloads:
- `piper-arm-bundle.tar.gz` - Complete bundle with voice models (Terminal Method build)
- `piper-arm-alternative-bundle.tar.gz` - Alternative build with community wheels
- Standalone executables for both build methods

### System Requirements

- macOS 11.0 (Big Sur) or later
- Apple Silicon Mac (M1/M2/M3/M4)
- ~50MB free disk space for the complete bundle

## Quick Start

### Installation

1. Download the bundle from the releases page
2. Extract the archive:
   ```bash
   tar -xzf piper-arm-bundle.tar.gz
   ```
3. Navigate to the extracted folder:
   ```bash
   cd piper
   ```

### Basic Usage

Generate speech from text:
```bash
echo "Hello, this is Piper TTS running on Apple Silicon!" | ./bin/piper --model voices/en_US-lessac-medium.onnx --output_file output.wav
```

Generate speech from a text file:
```bash
cat your_text.txt | ./bin/piper --model voices/en_US-lessac-medium.onnx --output_file speech.wav
```

### Command Line Options

```bash
./bin/piper --model <path_to_model> --output_file <output.wav>
```

- `--model` - Path to the voice model (.onnx file)
- `--output_file` - Output WAV file path

## Build Methods

This project provides two different build approaches, each with specific advantages:

### Method 1: Terminal Method (Recommended)
- **Build File**: Uses the first GitHub Actions workflow
- **Approach**: Installs piper-tts with `--no-deps` flag and manually installs dependencies
- **Advantages**: More reliable dependency resolution
- **Output**: `piper-arm-bundle.tar.gz`

### Method 2: Community Wheels Method
- **Build File**: Uses the alternative GitHub Actions workflow
- **Approach**: Leverages community wheels and includes system dependencies (espeak-ng)
- **Advantages**: Better compatibility with community packages
- **Output**: `piper-arm-alternative-bundle.tar.gz`

Both methods produce fully functional ARM64 binaries. Choose the one that works best for your use case.

## Voice Models

The binaries come with the `en_US-lessac-medium` voice model included. Additional voice models can be downloaded from the [Piper Voices repository](https://huggingface.co/rhasspy/piper-voices).

### Adding New Voices

1. Download voice files (.onnx and .onnx.json) from the Piper Voices collection
2. Place them in the `voices/` directory
3. Use the new model with the `--model` parameter

## Development

### Building from Source

The build process is automated using GitHub Actions. The workflows handle:

- Setting up Python 3.12 environment
- Installing dependencies with ARM64 compatibility
- Downloading voice models
- Creating PyInstaller executables
- Packaging final bundles

To trigger a build:
1. Fork this repository
2. Go to Actions tab
3. Run "Build ARM Binary for Testing (Terminal Method)" or "Build ARM Binary (Alternative Method)"

### Technical Details

- **Python Version**: 3.12
- **Build Tool**: PyInstaller with `--onefile` flag
- **Dependencies**: numpy, onnxruntime, piper-tts
- **Voice Model**: Lessac medium quality English (US)

## Troubleshooting

### Common Issues

**Binary won't run**: Ensure you're on an Apple Silicon Mac and have the necessary permissions:
```bash
chmod +x ./bin/piper
```

**Model not found**: Verify the model path is correct and the .onnx file exists in the voices directory.

**Audio output issues**: Check that the output directory is writable and you have sufficient disk space.

## Contributing

Contributions are welcome! Please feel free to:
- Report bugs and issues
- Suggest new features
- Submit pull requests
- Improve documentation

**⭐ Love this project? Give it a star on GitHub!** Your star helps others discover these ARM64 builds and motivates continued development.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

The Piper TTS engine is developed by Rhasspy and is also under the MIT License.

## Support This Project

If you find this project helpful, consider supporting its development:

<div align="center">

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://www.buymeacoffee.com/yourusername)
[![Star on GitHub](https://img.shields.io/badge/⭐%20Star%20on%20GitHub-black?style=for-the-badge&logo=github)](https://github.com/yourusername/piper-arm64)

Your support helps maintain and improve these ARM64 builds for the community. Consider starring the repository to show your appreciation!

</div>

---

## Acknowledgments

- [Piper TTS](https://github.com/rhasspy/piper) - The original Piper text-to-speech system
- [Rhasspy](https://github.com/rhasspy) - For developing the Piper TTS engine
- Apple Silicon community for testing and feedback

## Related Projects

- [Original Piper TTS](https://github.com/rhasspy/piper)
- [Piper Voices Collection](https://huggingface.co/rhasspy/piper-voices)
- [Home Assistant Piper Integration](https://www.home-assistant.io/integrations/piper/)

---

<div align="center">
<sub>Built with ❤️ for the Apple Silicon community</sub>
</div>
