Error context
I installed PyTorch in Anaconda with CUDA 10.2 as compute platform via the following command line:

conda install pytorch torchvision torchaudio cudatoolkit=10.2 -c pytorch
The following error shows up:


when following command is run: 
# Imports
import torch
import torchvision
from torchvision.datasets import MNIST



 UserWarning: Failed to load image Python extension: Could not find module 'D:\conda\envs\py38\Lib\site-packages\torchvision\image.pyd' (or one of its dependencies). Try using the full path with constructor syntax.
  warn(f"Failed to load image Python extension: {e}")


solution:

*.pyd files are Python extension modules compiled from other languages like C.

This approach is to manually rename 'image.pyd' in torchvision package folder (for example, the path is  'D:\conda\envs\py38\Lib\site-packages\torchvision' in my computer) to 'image.py'.

