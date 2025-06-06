# Classification Dataset Splitter

A simple Python tool to split image classification datasets into train/validation/test sets with customizable ratios. Perfect for preparing datasets for machine learning models like YOLO, CNN classifiers, and other computer vision tasks.

## Features

- 🎯 **Flexible Ratios**: Customize train/validation/test split ratios (default: 60:20:20)
- 📁 **Preserves Structure**: Maintains original class folder organization
- 🔀 **Random Shuffling**: Ensures balanced distribution across splits
- 🖼️ **Multiple Formats**: Supports common image formats (jpg, jpeg, png, bmp, tiff, webp)
- 📊 **Progress Tracking**: Shows detailed split statistics
- 🔄 **Reproducible**: Fixed random seed for consistent results

## Quick Start

### Prerequisites
```bash
pip install pathlib shutil random
```

### Usage

1. **Clone the repository**:
```bash
git clone https://github.com/SakibAhmedShuva/classification-dataset-splitter.git
cd classification-dataset-splitter
```

2. **Prepare your dataset** in this structure:
```
your_dataset/
├── class1/
│   ├── image1.jpg
│   ├── image2.jpg
│   └── ...
├── class2/
│   ├── image3.jpg
│   ├── image4.jpg
│   └── ...
└── ...
```

3. **Run the notebook**:
   - Open `cls_splitter.ipynb` in Jupyter Notebook or Google Colab
   - Update the source and output directory paths
   - Execute all cells

## Configuration

Modify these variables in the notebook:

```python
SOURCE_DIR = "path/to/your/dataset"     # Your dataset directory
OUTPUT_DIR = "path/to/output/directory" # Where to save split dataset

# Split ratios (must sum to 1.0)
TRAIN_RATIO = 0.6   # 60% for training
VAL_RATIO = 0.2     # 20% for validation  
TEST_RATIO = 0.2    # 20% for testing
```

## Output Structure

The tool creates a new directory with this structure:

```
output_directory/
├── train/
│   ├── class1/
│   │   ├── image1.jpg
│   │   └── image2.jpg
│   └── class2/
│       ├── image3.jpg
│       └── image4.jpg
├── val/
│   ├── class1/
│   └── class2/
└── test/
    ├── class1/
    └── class2/
```

## Example Output

```
Starting dataset split...
Source directory: dataset
Output directory: dataset_split
Split ratios - Train: 60.0%, Val: 20.0%, Test: 20.0%

Found 2 classes: ['correct', 'incorrect']

Processing class: correct
  Total images: 1000
  Train: 600, Val: 200, Test: 200

Processing class: incorrect
  Total images: 800
  Train: 480, Val: 160, Test: 160

Dataset split completed! Output saved to: dataset_split

Summary:
  train: 1080 images
  val: 360 images
  test: 360 images
```

## Use Cases

- **YOLO Training**: Prepare datasets for object detection/classification
- **CNN Classification**: Split data for image classification models
- **Computer Vision Research**: Organize datasets for experiments
- **Data Preprocessing**: Standard ML workflow preparation

## Custom Ratios

You can easily adjust the split ratios for different use cases:

```python
# For small datasets (more training data)
TRAIN_RATIO = 0.8   # 80%
VAL_RATIO = 0.1     # 10%
TEST_RATIO = 0.1    # 10%

# For large datasets (more validation/testing)
TRAIN_RATIO = 0.7   # 70%
VAL_RATIO = 0.15    # 15%
TEST_RATIO = 0.15   # 15%
```

## Requirements

- Python 3.6+
- Standard libraries: `os`, `shutil`, `random`, `pathlib`
- Jupyter Notebook (for running the .ipynb file)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built for the computer vision and machine learning community
- Designed with YOLO training workflows in mind
- Inspired by common dataset preparation needs

---

⭐ **Star this repo** if you find it helpful!

📧 **Questions?** Open an issue or reach out via GitHub.
