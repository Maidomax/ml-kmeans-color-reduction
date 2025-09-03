# K-Means Color Reduction

A high-performance Python implementation of K-means clustering for image color quantization, with special handling for dark/black regions.

## Features

- **Optimized K-means clustering** using vectorized NumPy operations and SciPy
- **K-means++ initialization** for faster convergence and better results
- **Memory-efficient batch processing** for large images
- **Automatic convergence detection** to minimize unnecessary iterations
- **Dark pixel preservation** with configurable black threshold
- **Professional-grade performance** with Euclidean distance metrics

## Installation

```bash
# Install dependencies
uv add numpy pillow matplotlib scipy

# Or with pip
pip install numpy pillow matplotlib scipy
```

## Usage

```bash
# Start Jupyter notebook
uv run jupyter notebook

# Open Vitrage.ipynb
```

### Basic Example

```python
from vitrage import Vitrage

# Load and process image
v = Vitrage('input.jpg', numcolors=8, black_threshold=50)
v.optimize(epochs=20)
v.save('output.jpg')

# View statistics
stats = v.get_stats()
print(f"Processed {stats['total_pixels']} pixels")
print(f"Reduced to {stats['num_colors']} colors")
```

## Parameters

- `numcolors`: Number of color clusters (default: 3)
- `black_threshold`: RGB threshold for black pixel detection (default: 10)
- `batch_size`: Pixels per batch for memory management (default: 10000)
- `tolerance`: Convergence threshold (default: 1e-4)

## License

MIT