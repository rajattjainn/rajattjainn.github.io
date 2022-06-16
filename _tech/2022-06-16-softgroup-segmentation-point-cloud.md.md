---
layout: post
title: "Softgroup for 3D Instance Segmentation for Point Cloud"
description: ""
date: 22-06-16

---

### Running Blog
#### June 16, 2022
1. Matterport Camera: Matterport camera is used to create the dataset (apart from MS Kinect). The way you use a Matterport camera is put it at place (it is mounted on a stand) and press scan button. The camera does a 360 degrees rotation and captures all the information there is in order to recreate a digital twin of the place. Next, you place the camera a bit far away (the max distance varies depending upon the camera model you are using) and repeat the process. The Matterport software stiches all the scenes, takes care of all overlapping regions, and at the end provides the user with a navigable 3D layout of the place that were captured. 
2. S3DIS Data Stucture: The data contains multiple areas scanned from multiple buildings. Each Area has multiple rooms; and each room, in turn has various objects. The room folder has a Annotations folder and a *room_id.txt* file. The txt file contains xyz and rgb values for all the elements/objects that were scanned in the room, but without any marker as to what object these coordinate corresponds to. The Annotations folder contains multiple txt files (each named after one element/object) which contain the coordinates and rgb values for that particular element/object.
	- I have not verified this, but it seems obvious that if one were to sum up the length of all the files in Annotations folder, the sum would be equal to the length of *room_id.txt* file.
3. K-means nearest neighborhood: provide the number of neighbors as an argument. Gives the indices and distance from the nearest neighbor. This step helps in defining the semantic labels and instance labels.
4. Prepare Data - 
	- From the input data, create tensors for coordinates, rgb, semantic label, instance label and room label. 
	- Downsample the data based on a given ratio
	- (?)
