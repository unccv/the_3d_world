# The 3d World Challenge

![](../videos/opensfm_demo.gif)

## About this Challenge
In this challenge you'll be working in groups to build your own 3d model or map! We'll be using some terrific open source code from [Mapillary](https://www.mapillary.com/) called [OpenSFM](https://github.com/mapillary/OpenSfM). 

## Instructions

1. Decide what you want to map. Your group is required to take all of your own pictures, you may you phone cameras or other cameras. You may map large things (like a buliding on campus), or build 3d models of objects. Feel free to experiment with your group! 

2. Get OpenSFM running. Due to a few dependencies, OpenSFM is easiest to use on Linux systems. Please see instructions below. 

3. Build and tune your maps/models! OpenSFM is a complex piece of softward with lots of configurable options. Check out [config.yaml](https://github.com/mapillary/OpenSfM/blob/master/config.yaml) in the OpenSFM repo. As we work through this module, you'll learn what goes into a number of the configurable pieces of OpenSFM. This should help you make intelligent tuning experiments. You will also likely want to experiment with the images you feed into OpenSFM. 

4. Submit! Your deliverables are a 30-60 second screenshot video navigating your map/model (like the animation above), and your images and generated files from OpenSFM, see the Deliverables section below for full details. 


## Installing OpenSFM




## Deliverables
1. 30-60 second screenshot video navigating your map/model (like the animation above). Upload your video to YouTube (it can be public or unlisted), and include a link to your video in README.txt file as part of your final submission. Your README must also include the names of your group members. 
2. OpenSFM files. Please submit a zip file to canvas containing your final OpenSM files + folders and README: 
- README.txt (details above)
- config.yaml 
- camera_models.json  
- reconstruction.json 
- reconstruction.meshed.json
- reference_lla.json
- undistorted_reconstruction.json
- tracks.csv
- profile.log
- undistorted_tracks.csv
- features             
- images         
- undistorted
- depthmaps           
- matches                
- exif                  
- reports                     

## Grading
Your grade will be based on the subjective quality of your final map/model. We may also review your config.yaml and other OpenSFM to get a sense for the amount of experimentation that went into your final product. 

## Prize
Top prize will go to the group with the most interesting/coolest map/3d model. This is, of course, highly subjective - the Instructor and TAs will take a vote. 



