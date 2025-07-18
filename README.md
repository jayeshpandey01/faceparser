# FaceParser

A Python library for face parsing and feature extraction using BiSeNet architecture. This library provides powerful tools for facial feature detection, segmentation, and detailed facial analysis.

[![PyPI version](https://badge.fury.io/py/faceparser.svg)](https://badge.fury.io/py/faceparser)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.7+](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/)

## Features

- **Facial Feature Detection**: Accurate detection and segmentation of 19 different facial features
- **Feature Extraction**: Detailed coordinate and metric extraction for each facial feature
- **Face Analysis**: Comprehensive metrics including symmetry scores and feature relationships
- **Easy-to-use CLI**: Command-line interface for quick model management and image processing
- **Visualization Tools**: Built-in tools for visualizing parsed features and masks
- **GPU Support**: Automatic GPU acceleration when available

## Installation

```bash
pip install faceparser
```

After installation, you need to download the model weights:

```bash
faceparser install
```

## Usage

### Python API

```python
from faceparser import FaceParser, get_coordinates

# Initialize parser
parser = FaceParser()

# Parse an image
parsing_map, coordinates = parser.parse("path/to/image.jpg")

# Get feature coordinates
feature_coords = coordinates.get_feature_coordinates("nose")

# Get feature embeddings
embeddings = coordinates.get_all_embeddings()

# Get face metrics
metrics = coordinates.get_relative_metrics()
symmetry = coordinates.get_symmetry_score()

# Access individual feature metrics
for feature, area in metrics['feature_areas'].items():
    print(f"{feature} area: {area:.3f}")
```

### Command Line Interface

1. Install model:
```bash
faceparser install
```

2. Check model installation:
```bash
faceparser check
```

3. Parse an image:
```bash
faceparser parse path/to/image.jpg -o output_directory --save-masks
```

## Supported Features

The face parsing model can detect and segment the following facial features:

- Skin
- Nose
- Eyes (left and right)
- Eyebrows (left and right)
- Ears (left and right)
- Mouth
- Upper and lower lips
- Hair
- Hat
- Eyeglasses
- Earrings
- Necklace
- Neck
- Clothes

## Feature Metrics

The library provides various metrics for facial analysis:

- Feature embeddings (normalized position, size, area, aspect ratio)
- Face symmetry score
- Feature areas (normalized)
- Normalized distances between features
- Relative positions
- Feature aspect ratios

## Model Architecture

FaceParser uses the BiSeNet (Bilateral Segmentation Network) architecture trained on the CelebAMask-HQ dataset. The model is optimized for both accuracy and speed, making it suitable for real-time applications.

## Requirements

- Python 3.7+
- PyTorch
- NumPy
- OpenCV
- Pillow
- Click (for CLI)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

- **Jayesh J. Pandey** - [jayeshpandey01](https://github.com/jayeshpandey01)
- Email: pandeyjayesh020@gmail.com

## Citations

If you use this library in your research, please cite:

```bibtex
@software{faceparser2025,
  author = {Pandey, Jayesh J.},
  title = {FaceParser: A Python Library for Face Parsing and Feature Extraction},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/jayeshpandey01/faceparser}
}
```
