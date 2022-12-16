# Automating the Endoscope Camera of the DVRK using Tobii Eye Tracker 5 

##### In this repository, as a part of our Human-Robot Interaction Project, we have attempted to automate/operate the endoscope camera based on - Gaze tracking, keyboard and mouse interfaces.

 The main contributors of the Project were :
 <br> <a href="https://github.com/UthiraS">Uthiralakshmi Sivaraman</a>
 <br><a href="https://github.com/ssaserkar">Soham Shantanu Aserkar</a>  
 <br><a href="https://github.com/oraisbeck">Olivia Raisbeck </a>

For this project, the following software dependencies are required:
```
Unity 3D 2020+
Anaconda 
Python 3.7
Torch 1.7.1
CUDA 11.0
```

For the purpose of the Project, we have used the Tobii Eye Tracker 5 to track the gaze and move the Camera wihtin the Unity Simulation.
We have setup the Unity Environment based on the real daVinci Research Kit from scratch and integrated the camera output to the main camera. 

The Necessary Packages to Add :
```
1) Tobii Eye Tracker Unity SDK 5.0003
2)  URDF Impoter : https://github.com/Unity-Technologies/URDF-Importer.git?path=/com.unity.robotics.urdf-importer#v0.5.2
```


Steps to Add the Package to Unity:
```
1) Open the Unity HUb, find the project titled ""
2)  Under Window tab, choose Package Manager
3) Package Manager tab gets opened
4) In top left corner, Chooce either of the options 
i) Add package from Disk
ii) Add Package from git URL
Choose the options based the location of package to be imported.
```


Here are the steps to run the Unity Simulation:
```
1) Open the Unity Hub, find the project name titled "DVRK-ROS"
2) Click on the Project Structure.
3) Find the 'Working_Scene' in the Scenes Folder.
4) Connect the Tobii Eye Tracker 5
5) Ensure the current display in active in Game View
5) Upon pressing play, 
    hold down the key 'A' to move the camera based on Gaze
    hold down the key 'B' to move the camera based on Keyboard
    hold down the key 'C' to move the camera based on Mouse
```

For running the training of the Semantic Segmentation using the UNet++ architecture:
1) Install Anaconda and create new virtual environment based on the environment.yml.
```
conda create -f environment.yml
```
2) Upon ensuring the dependencies match the architecture from the environment and the dataset is structured as below:
  ```
  |__ src
	|__ data
		|__ datasets
                    |__ synapse
                        |__ train
                            |__ images
                            |__ groundtruth
                        |__ trainval
                            |__ images
                            |__ groundtruth
                        |__ test
                            |__ images
                            |__ groundtruth
                            
                    |__ cholec
                        |__ train
                            |__ images
                            |__ groundtruth
                        |__ trainval
                            |__ images
                            |__ groundtruth
                        |__ test
                            |__ images
                            |__ groundtruth
 ```
 3) Run the trainSegNet.sh file
 4) The resultant image is saved in the folder 'results' in recurrent folders, where you can find the results for each combination of hyperparameters you try.
 
 The below is the result obtained for the batch size of 2 for training set and 1 for validation set.
 
 
 
![epoch_19_img_0](https://user-images.githubusercontent.com/116770046/207999666-a120461b-b423-49d0-b014-998cfa53c79a.png)
