# EE604-Image_Processing

This repository contains solutions to assignments for the EE604 Image Processing course. Each assignment focuses on different aspects of image processing, including filtering, inpainting, and blending techniques.


## Assignment Details

### **Assignment 1**

#### **Question 1** (EE604_Ass1_Question1.ipynb)
- **Objective**: Render text into an image using a 5x7 binary matrix representation of characters.
- **Details**:
  - Each character is represented as a 5x7 binary matrix.
  - The function `rendertexttoimage` takes a string input and renders it into an image with customizable scaling, spacing, and padding.
  - The notebook includes a sample input string and demonstrates rendering it into an image.
  - The output image is saved as `output.png`.

#### **Question 2** (EE604_Ass1_Question2.ipynb)
- **Objective**: Identify and remove leopard spots from an image.
- **Details**:
  - The function `leopardspotsremove` processes an input image to detect and remove leopard spots.
  - Techniques used:
    - Convert the image to grayscale.
    - Apply adaptive thresholding to create masks for the spots.
    - Use morphological operations to refine the masks.
    - Inpaint the image to remove the spots and blend the surrounding areas.
  - The final output is a smooth, spot-free image.

---

### **Assignment 2**

#### **Question 1 (Part A)** (EE604_Ass2_Question1_part_a.ipynb)
- **Objective**: Generate foreground masks for MNIST images using Otsu's thresholding.
- **Details**:
  - The function `getforegroundmasks` creates binary masks for MNIST images.
  - Otsu's thresholding is applied to separate the foreground (digits) from the background.
  - The masks are visualized and saved for further processing.

#### **Question 1 (Part B)** (EE604_Ass2_Question1_part_b.ipynb)
- **Objective**: Perform inpainting on MNIST images using the generated masks.
- **Details**:
  - The function `inpaintimages` uses the masks from Part A to inpaint the MNIST images.
  - OpenCV's inpainting techniques are applied to fill the masked regions.
  - The output is a set of inpainted images with the digits removed.

#### **Question 1 (Part C)** (EE604_Ass2_Question1_part_c.ipynb)
- **Objective**: Blend the inpainted MNIST images with Gaussian-blurred versions.
- **Details**:
  - The function `blendimages` blends the inpainted images with Gaussian-blurred versions for smooth transitions.
  - A feather mask is created using Gaussian blur to ensure natural-looking edges.
  - The final blended images are saved as output.

#### **Question 2** (EE604_Ass2_Question2.ipynb)
- **Objective**: Implement a custom image filtering technique.
- **Details**:
  - The function applies a custom kernel to an input image for edge detection or smoothing.
  - The kernel size and type can be adjusted for different effects.
  - The output is a filtered image.

#### **Question 3** (EE604_Ass2_Question3.ipynb)
- **Objective**: Perform histogram equalization on grayscale images.
- **Details**:
  - The function computes the histogram of an input image and applies equalization to enhance contrast.
  - The original and equalized histograms are visualized.
  - The output is a contrast-enhanced image.

#### **Question 4** (EE604_Ass2_Question4.ipynb)
- **Objective**: Implement a basic image compression technique.
- **Details**:
  - The function compresses an image by reducing its resolution and applying quantization.
  - The compressed image is reconstructed and compared with the original.
  - The compression ratio and quality metrics are calculated.

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
