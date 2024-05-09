## Installation Guide
In this section, we demonstrate how to set up the environment and  install dependencies for our project, including miniconda, pytorch, poseMM, camera virtualization, Unity, and communications.  

### Computer Requirement 
Monocular RGB camera. 
Graphics Card  (recommend at least 3060ti). 
Windows Operating System 10  or 11.  

### Python Environment 
Step 0: Install Miniconda.  
Step 1: Create a conda environment and activate it.  
```
conda create --name MagicMirror python=3.8 -y
conda activate MagicMirror
```
Step 2: Install PyTorch following [official instructions](https://pytorch.org).    

For example, if you have CUDA 12.1, use the following command:  

```
pip install torch==2.2.2 torchvision==0.17.2 torchaudio==2.2.2 --index-url https://download.pytorch.org/whl/cu121
```

Attention: Make sure the Cuda runtime version is lower than 12.1. In our project environment, we build everything based on CUDA Toolkit 12.1. The default command from the official website will automatically install the latest version of PyTorch, this might cause an incompatible issue with poseMM.
We recommend installing CUDA runtime 12.1 and using the command given above.

Step4: Install MMEngine and MMCV using MIM.
```
pip install -U openmim
mim install mmengine
mim install "mmcv>=2.0.1"
```
Install mmdet as a dependency by running:
```
mim install "mmdet>=3.1.0"
```
### Unity
install Unity at the official [website](xxx)
```
cd Magic-Mirror # go to the project folder
```
Download the project from this [link](xxx)
```
unzip Test 
```
The folder contains the unity project, including all assets， plug-in files, and objects. After preparing all the files, open the Test folder as a Unity project.
### Communication

Step 0: C# and .NET configuration 
Make sure VS Code is installed before. Install C# Extension and .NET Install Tool, and use which to configure .NET environment. 

Step 1: In VS Code turn on the command panel (Windows and Linux: shortcut ctrl+shift+P), input ‘NuGet’ -> ‘Add Package ’ -> add packages ‘AsyncIO’, ‘NetMQ’, ‘Newtonsoft.Json’, ‘NACI’. Then copy the .dll files of these packages, which can be found in the NuGet installation folder, to ‘.Assets/Plugins’. 

Step2: Install ‘pyzmq’ via ‘pip install pyzmq’ in Python.


### Camera Virtualization 
OBS Studio can be installed from its [official website](https://obsproject.com).

## Running the project
### Camera Virtualization  
To multi-stream the camera for both the estimation model and Unity, firstly you need to add the camera to Obs Studio. After that, click on the start virtualization button. In the end, you should adjust the video screen to full screen by right-clicking the video and selecting the full-screen mode.

### Pose Estimation and Communicate
Open the terminal in the project folder.
```
conda activate MagicMirror
cd Pose 
command.bat
```
### Open Unity Project 
Open the unity 'test' project and run.
