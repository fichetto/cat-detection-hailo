# Cat Detection and Classification System

Cat Detection and Classification System using Hailo-8 AI Accelerator on Raspberry Pi 5. Automatically detects and captures cats using real-time AI inference, with a user-friendly GUI for cataloging and organizing cat images into a structured dataset for machine learning training.

## Features

- **Real-time Cat Detection**: Uses YOLOv8 model on Hailo-8/8L accelerator
- **Intelligent Capture**: Implements cooldown and confidence thresholds
- **Automatic Image Saving**: Captures and saves images when cats are detected
- **GUI Catalog System**: User-friendly interface for image organization
- **Dataset Creation**: Automatically structures data for ML training
- **Multi-cat Support**: Ability to classify different cats
- **Training/Validation Split**: Organizes images for machine learning

## Prerequisites

### Hardware Requirements
- Raspberry Pi 5 (8GB RAM recommended)
- Hailo-8 or Hailo-8L AI Accelerator
- USB Camera or Raspberry Pi Camera Module
- Active Cooling Solution for Raspberry Pi 5

### Software Requirements
- Raspberry Pi OS (64-bit)
- Python 3.x
- Hailo Runtime
- GStreamer with Hailo plugins

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/cat-detection-hailo.git
   cd cat-detection-hailo
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Desktop Shortcuts**
   ```bash
   ./scripts/setup_cat_detection_desktop.sh
   ./scripts/setup_cat_catalog_desktop.sh
   ```

## Usage

### Cat Detection

1. Launch the detection application either from the desktop shortcut or command line:
   ```bash
   python src/detection/detection_with_cat.py --input /dev/video0 --show-fps
   ```

2. Configuration options:
   - `--input`: Specify camera input (USB or RPi camera)
   - `--show-fps`: Display frame rate
   - `--use-frame`: Enable frame display
   - `--min-confidence`: Set detection threshold (default: 0.7)
   - `--cooldown`: Set capture cooldown in seconds (default: 5)

### Cat Cataloging

1. Launch the catalog application:
   ```bash
   python src/cataloging/enhanced_cat_catalog.py
   ```

2. Features:
   - View and name detected cats
   - Organize images by cat
   - Split data into training/validation sets
   - Track image statistics
   - Manage dataset structure

## Project Structure

```
cat-detection-hailo/
├── src/
│   ├── detection/           # Detection scripts
│   └── cataloging/         # Cataloging GUI
├── scripts/                # Setup and utility scripts
├── docs/                   # Documentation
└── requirements.txt        # Dependencies
```

## Storage Structure

The system creates and manages the following directories:
- `detected_cats/`: Raw detected images
- `named_cats/`: Cataloged images
- `dataset/`: Organized ML dataset
  - `train/`
  - `val/`
  - `test/`

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Hailo-AI](https://hailo.ai/) for the AI accelerator and SDK
- [YOLOv8](https://github.com/ultralytics/ultralytics) for the object detection model
- [Raspberry Pi Foundation](https://www.raspberrypi.org/) for the hardware platform

## Support

For support, questions, or suggestions:
1. Open an issue in the GitHub repository
2. Visit the [Hailo Community Forum](https://community.hailo.ai/)
3. Refer to our [documentation](./docs/)

## Roadmap

- [ ] Add support for multiple camera inputs
- [ ] Implement automatic retraining pipeline
- [ ] Add web interface for remote monitoring
- [ ] Improve detection accuracy for specific cat breeds
- [ ] Add export functionality for common ML frameworks
