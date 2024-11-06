## Running the Code

### Option 1: Google Colab

This option is straightforward; however, ensure sufficient compute resources for 50 epochs. The provided `.ipynb` file defaults to 5 epochs, which achieves ~70% accuracy on CIFAR-10 and ~99% on MNIST. For optimal results, run for 50 epochs on CIFAR-10 and 10 epochs on MNIST.

**Steps:**
1. Download the `.ipynb` file and connect to a GPU.
2. By default, the global variables will work. If you wish to modify settings, then set the following global variables at the top of the script: 
   - `mode = 'train'` (set to `'load'` if resuming from a checkpoint). Note that if running for the first time, you must set `mode = 'train'`, as your current environment does not have any model checkpoints saved.
   - `dataset = 'CIFAR10'` (or `'MNIST'`)
   - `torch_save_dir = r"model.pth"` (specify model save location)

**Optional (Testing with Custom Image):**
To test the model on custom images, follow these steps:

3. Download image(s) from CIFAR-10 classes (e.g., Airplane, Automobile, etc.) or MNIST (digits 0-9). Supported formats: `.jpg`, `.jpeg`, `.png`. 
   - Note: MNIST images are grayscale (28x28), and while the model performs well on the MNIST test set, it may not generalize well to other digit images.
4. Upload the image(s) to a folder in the local directory of Google Colab.
5. Set the following variable to the folder name (e.g., `CIFAR_testing`):
   - `CIFAR_testing_dir = r"CIFAR_testing"`
   - `MNIST_testing_dir = r""` (leave blank if not using)

The model will now predict images from the specified folder.

### Option 2: Local Machine

Ensure your local machine has a GPU for optimal performance.

**Steps:**
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
2. Follow steps 2-5 from above. However, for step 5, since the folder is not located in the Google Colab directory, you must specify the full path to the folder's location on your local machine. For example:
   - `CIFAR_testing_dir = r"C:/Downloads/CIFAR_testing"`
