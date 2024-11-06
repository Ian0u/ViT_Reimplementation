# ViT_Reimplementation

Steps for Running the Code 
Option 1: Google Colab
This is perhaps the easiest choice, but since this is a moderately sized model, make sure you have enough compute units to run 50 epochs. In the provided .ipynb file, it is set to 5 epochs. This is sufficient enough to get relatively good test accuracy (~70% on CIFAR10 and ~99% on MNIST), but for better results on CIFAR-10, 50 epochs is recommended.

Required Steps:
1. Download the .ipynb file and connect to GPU. 
2. At the top of the script, you should see the following global variables: 
mode = 'train' # 'train' or 'load'
dataset = 'CIFAR10' # 'CIFAR10' or 'MNIST'
torch_save_dir = r"model.pth" # Choose where to save the model
CIFAR_testing_dir = r"" # Choose the directory to classify any user inputted image within CIFAR-10 classes. If none, then leave blank.
MNIST_testing_dir = r""

If this is your first time running, 

Optional Steps:
If you would like to test the model to classify any image of your choosing, then follow these steps. Otherwise, skip these steps. 
2. Create a folder in the folder section of Google Colab. Name it to your choosing.
3. You may use the sample images found in the 'CIFAR10_testing', or go online and find your own images (as long as it is within the classes of CIFAR-10 or MNIST). Images must be .jpg, jpeg, or .png.



the 'CIFAR10_testing' folder into a directory of your choosing. I recommend putting it into the folder section of Google Colab. That way, you do not have to connect to your Google Drive. 
