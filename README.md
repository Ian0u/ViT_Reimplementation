## Introduction
The main goal of this project is to reimplement the paper [An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale](https://arxiv.org/pdf/2010.11929). The reimplementation also explores how using both [MixUp](https://arxiv.org/pdf/1710.09412) and [CutMix](https://arxiv.org/pdf/1905.04899v2) during training can improve the performance of the Vision Transformer. 

## Demo Video
The demo video link is [here](https://youtu.be/EXG2I3gBZw8). This video introduces the project and demonstrates the main features of the code. The video was uploaded onto YouTube by using an anonymous account to adhere to the double-blind review process.

## Running the Code

### Option 1: Google Colab (ViT.ipynb)

This option is straightforward; however, ensure sufficient compute quota. The provided `.ipynb` file defaults to only 5 epochs, which achieves ~70% test accuracy on CIFAR-10 and ~99% on MNIST. For optimal results, run for 50 epochs on CIFAR-10 and 10 epochs on MNIST, but this would require more time and compute resources.

**Steps:**
1. Download the `ViT.ipynb` file and connect to a GPU.
2. By default, the global variables will work. If you wish to modify settings, then set the following global variables at the top of the script: 
   - `mode = 'train'` (set to `'load'` if resuming from a checkpoint). Note that if running for the first time, you must set `mode = 'train'`, as your current environment does not have any model checkpoints saved.
   - `dataset = 'CIFAR10'` (or `'MNIST'`)
   - `torch_save_dir = r"model.pth"` (specify model save location)

**Optional (Testing with Custom Image):**
To test the model on custom images, follow these steps:

3. Download image(s) from CIFAR-10 classes (e.g., random images of airplanes, dogs, cats, etc.) or MNIST (digits 0-9). Supported formats: `.jpg`, `.jpeg`, `.png`. 
   - *Note: MNIST images are grayscale (28x28), and while the model performs well on the MNIST test set, it may not generalize well to random digit images found on the web, especially if they are 3D in nature. For this reason, CIFAR-10 does a better job at predicting images found on the web, as it is trained on RGB images that more closely resembles normal pictures.*
4. Create a folder in the local directory of Google Colab and upload the image(s) into the folder.
5. Set the following variable to the folder name (e.g., `CIFAR_testing`):
   - `CIFAR_testing_dir = r"CIFAR_testing"`
   - `MNIST_testing_dir = r""` (leave blank if not using)
   - An example of a custom input image folder is included in the GitHub.

The model will now predict images from the specified folder.

### Option 2: Local Machine (ViT.py)

**Steps:**
1. Download the `ViT.py` file and ensure your local machine has a GPU for optimal performance, with CUDA enabled.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
3. Follow steps 2-5 from above. However, for step 5, since the folder is not located in a Google Colab directory, you must specify the full path to the folder's location on your local machine. For example:
   - `CIFAR_testing_dir = r"C:/Downloads/CIFAR_testing"`
