# ViT_Reimplementation

**Steps for Running the Code** 

Option 1: Google Colab
This is perhaps the easiest choice, but since this is a moderately sized model, make sure you have enough compute units to run 50 epochs. In the provided .ipynb file, it is set to 5 epochs. This is sufficient enough to get relatively good test accuracy (~70% on CIFAR10 and ~99% on MNIST), but for better results on CIFAR-10, 50 epochs is recommended.

**Required Steps:**
1. Download the .ipynb file and connect to GPU. 
2. At the top of the script, you should see the following global variables:
```
mode = 'train' # 'train' or 'load'
dataset = 'CIFAR10' # 'CIFAR10' or 'MNIST'
torch_save_dir = r"model.pth" # Choose where to save the model
```
If this is your first time running, set ```mode = 'train'```, as a model checkpoint has not been created. To load an existing model, which by default is saved to the directory path given by ```torch_save_dir``` as model.pth, set ```mode = 'load'```, which will skip the training process and skip to the part where it attempts to predict any images you throw at it, as mentioned below in "Optional Steps."

**Optional Steps:**
If you would like to test the model to classify any image of your choosing, then follow these steps. Otherwise, skip these steps. 
3. Download any image for any class within CIFAR-10 (Airplane, Automobile, Bird, Cat, Deer, Dog, Frog, Horse, Ship, Truck) or MNIST (0, 1, 2, 3, 4, 5, 6, 7, 8, 9). Images must be .jpg, jpeg, or .png. 
**Note: MNIST images are grayscale (28x28 pixels) with digits (0-9), and the images are relatively simpler. This means although it performs well on the MNIST test set, it might not generalize as effectively to other digit images from the web. For this reason, it is recommended to test the model on images of CIFAR-10 classes.**
4. Create and name a folder in Google Colab directory. Put in the downloaded images into the folder.
5. Set the following variables to the names of the folder. For example, if the folder was named "CIFAR_testing" I would set the variable name like so. If you put it in another directory, then set it to 'path_to_directory/CIFAR_testing'
```
CIFAR_testing_dir = r"CIFAR_testing" 
MNIST_testing_dir = r""
```
6. The model should now predict images found on the web.

Option 2: Local Machine 
If you choose this option, it is recommended for your local machine to have a GPU. 
**Required Steps:**
1. Install requirements.txt by running ```pip install -r requirements.txt```
2. Run the code and follow steps 2-5 above. 
