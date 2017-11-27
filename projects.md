---
layout: page
title: Projects
permalink: /projects/
---


### Current Projects

- Undergoing an intensive training in C++ by Bloomberg. So just chilling in free time :)

### Past Projects

- #### Apple Detection 
	- This is the GPU based real time object detection system that I got a chance to develop while working as a Research Assistant at the Robotics Sensor Networks Lab here at University of Minnesota. 
	- Here the system is trained against apples. It can be used for many other fruits.

		<iframe width="420" height="315" src="https://www.youtube.com/embed/dg4KFW_Vbow" frameborder="0" allowfullscreen></iframe>

- #### Corn row orientation detection
	- This is the CPU parallelized code for Corn Row orientation detection. 
	- This was also developed by me as a RA in the RSN lab here at Univ. of Minnesota.

		<iframe width="420" height="315" src="https://www.youtube.com/embed/vGBq_tOlBNc" frameborder="0" allowfullscreen></iframe>

- #### Fast Foreground Background image segmentation on CUDA
	- This was done as a class project for course EE 5351 **Applied Parallel Programming** as a team project with my 2 other batch mates. Foreground-background separation forms an important problem with applications in real-life for video surveillance. This problem is usually solved using a formulation known as Robust Principal Component Analysis (RPCA). This generally requires solving a convex optimization problem. There are lots of algorithms that can be thrown as black boxes to solve a convex optimization problem and here we have chosen ADMM (Alternating Direction Method of Multipliers) for this purpose and have parallelized it on CUDA.
	- The SVD implemented by us on CUDA gets **26 times** speedup than CuSolver SVD for the specific tall matrices required in this problem domain. For speed benchmarks and profiling, please see the slides/report below. We are in the process of releasing the code as Open Source soon.
	- Project
	  - Final presentation [Slides](https://docs.google.com/presentation/d/1dJqLt6rFyvk_PioW58vnbbihzjxxyIgbSAsPwjfSxuA/edit?usp=sharing). (look into for speed profiling)
	  - Final [Report](https://drive.google.com/file/d/0B7amwNOMaX8OM1JBX2RFQ3lncUE/view?usp=sharing).
	- Results
	  - Rpca profiling against Matlab implementation.
	  <img src="../images/rpca_profiling.png" width="600" height="400" align="center" />

- #### Exploring Deep Reinforcement Learning
	- This was done as a class project for the research level course CSCI 8980 **Geometric Optimizations in Robotics**. This project encapsulated getting acquainted with the current Reinforcement Learning literature and apply them over some real world problems. In our case, this problem can be divided into two parts wherein we had to survey and  implement the current discreet and continuous action domain RL literature and also to build the robotics simulation environment for carrying out the training part. While we had some success in each of them, due to time restraint we were not able to combine the learning part with the environment. However, our results can become a good starting point for any further work in this domain.
	- Project
		- Deep Deterministic Policy Gradient [Slides](https://drive.google.com/file/d/0B7amwNOMaX8OaXQ3Z2d0eVVBX0k/view?usp=sharing) that I prepared and presented.
		- The [blog post](http://kislayabhi.github.io/Fun_with_Reinforcement_Learning/) and [code](https://github.com/kislayabhi/blog_code/tree/master/rl-car) that came out of this.
		- [Final Report](https://drive.google.com/open?id=0B7amwNOMaX8OMVh6UERZdlc4MGc).
	- Some Results.

		- The final trained system for homing in the target.

			<iframe width="420" height="315" src="https://www.youtube.com/embed/h2pmw6pjONU" frameborder="0" allowfullscreen></iframe>

		- The pursuer evader case. Both the agents are basically Neural Networks. Each one is training against the another. One tries to pursue and the other tries to evade.

			<iframe width="420" height="315" src="https://www.youtube.com/embed/L7-nASmK4ow" frameborder="0" allowfullscreen></iframe>

		- The time taken per episode as visualized on Tensorboard. It decreases as expected.

			<img src="../images/blog_tensorflow_time_per_epoch.png" width="700" height="315" align="center" />

- #### Orchard Map Reconstruction using Strucure from Motion.
	- This was done as a class project under Professor Stergios Roumeliotis for the course CSCI 5552 **Sensing and Estimation in Robotics**. In this project, we designed a system to build the dense map of a row of apple trees. The main sensors involved are Velodyne and Garmin. The fusion of sparse image features and dense laser points aims to estimate the position and orientation of the two sensors and retrieve the absolute scale of the reconstructed apple trees.

	- Project

		- [Proposal](https://drive.google.com/open?id=0B7amwNOMaX8OdVlLRVJGNWhTMzA)
		- [Final Report](https://drive.google.com/open?id=0B7amwNOMaX8OMUtreVdTMVFSaE0)


- #### How much did it rain 2 [Kaggle]
	- This was done as a class project under Professor Arindam Banerjee. We took this Kaggle challenge as it was active at the time of our course of Machine Learning. ( CSCI 5525 at University of Minnesota.)

	- Project

	   - [Proposal](https://drive.google.com/file/d/0ByM6ForkyNZfeEdNM1dSeDJTakE/view?usp=sharing)
	   - [Progress Report](https://drive.google.com/file/d/0ByM6ForkyNZfNXJVamhfRHoyalk/view?usp=sharing)
	   - [Final Report](https://drive.google.com/file/d/0ByM6ForkyNZfOTJDeUxNclA5ZGs/view?usp=sharing)


- #### IPython Notebooks

	- IPython notebooks are a great way to learn python. Herein, I have developed some lucid notebooks showcasing a mixture of Computer Vision and Machine Learning techniques! Check these out and write your own! :)

	- ##### 1. Automatic Number Plate Recognition

		- [Project link](http://nbviewer.jupyter.org/gist/kislayabhi/89b985e5b78a6f56029a/ANPR.ipynb)
		- I wrote this back when I was involved in Google Summer of Code with Shogun Machine Learning toolbox. This system is about detecting automobile license plate in photographs taken between 1-2 meters from a car. It is a robust example showcasing the unification of image processing techniques along with pattern recognition algorithms like SVM and ANN.

	- ##### 2. PCA and its application in face recognition

		- [Project link](https://gist.github.com/kislayabhi/9431770#file-pca_notebook-ipynb)
		- Again this was the outcome of a great Summer of Code as mentioned above. This system shows the usage of Principal Component Analysis for general data compression. Its dimensional reduction capabilities are further utilized to show its application in Eigenfaces Face recognition algorithm.

	- ##### 3. Object categorization using SIFT

		- [Project link](http://nbviewer.jupyter.org/gist/kislayabhi/abb68be1b0be7148e7b7)
		- This system differentiates between images containing a car, a train and a plane. The category of the image is decided on the basis of SIFT descriptors. K-means clustering is employed for generating bag-of-keypoints and multiclass SVMs are used for the prediction of the category of the object.

	- ##### 4. Active Appearance Model

		- [Project link](http://nbviewer.jupyter.org/gist/kislayabhi/0cc4f6e6b625873c15de)
		- Here I developed a parameterized face needed by the Active Appearance Model (AAM), where the variability of shape and texture is captured from a representative training set. PCA on shape and texture is applied to produce the face model which describes the trained faces with a photorealistic quality.Visit ([here](http://kislayvision.com/research/active-appearance-models/)) for more details.
