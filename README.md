# EE604-Image_Processing

This repository contains solutions to assignments for the EE604 Image Processing course. Each assignment focuses on different aspects of image processing, including filtering, inpainting, and blending techniques.


## Features

- **Assignment 1**:
  - Question 1: Implementation of basic image processing techniques.
  - Question 2: Advanced image blending using Gaussian blur and feather masks for smooth transitions. For example:
    ```python
    feathermask = cv2.GaussianBlur(filteredmask.astype(np.float32), (31, 31), 0) / 255.0
    finalimage = (1 - feathermask[..., None]) * inpaintedimg + feathermask[..., None] * blurredimg
    ```
    This ensures natural-looking edges in the processed image.

- **Assignment 2**:
  - Question 1: Divided into three parts (a, b, c) focusing on different sub-problems.
  - Questions 2-4: Solutions to additional image processing tasks.

## Requirements

To run the notebooks, you need the following dependencies:

- Python 3.x
- OpenCV (`cv2`)
- NumPy
- Jupyter Notebook

Install the required packages using pip:

```sh
pip install opencv-python-headless numpy notebook
```

## Usage 

Clone the repository

```
git clone https://github.com/your-username/EE604-Image_Processing.git
cd EE604-Image_Processing
```

Open the desired Jupyter Notebook 

```
jupyter notebook
```

Run the cells in the notebook to execute the solutions.
