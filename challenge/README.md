# The 3d World Challenge

![](../videos/opensfm_demo.gif)

## About this Challenge
In this challenge you'll be working in groups to build your own 3d model or map! We'll be using some terrific open source code from [Mapillary](https://www.mapillary.com/) called [OpenSFM](https://github.com/mapillary/OpenSfM). 

## Instructions

1. Decide what you want to map. Your group is required to take all of your own pictures, you may use phone cameras or other cameras. You may map large things (like a buliding on campus), or build 3d models of objects. Feel free to experiment with your group! 

2. Get OpenSFM running. Due to a few dependencies, OpenSFM is easiest to use on Linux systems. Please see instructions below. 

3. Build and tune your maps/models! OpenSFM is a complex piece of softward with lots of configurable options. Check out [config.yaml](https://github.com/mapillary/OpenSfM/blob/master/config.yaml) in the OpenSFM repo. As we work through this module, you'll learn what goes into a number of the configurable pieces of OpenSFM. This should help you make intelligent tuning experiments. You will also likely want to experiment with the images you feed into OpenSFM. 

4. Submit! Your deliverables are a 30-60 second screenshot video navigating your map/model (like the animation above), and your images and generated files from OpenSFM, see the Deliverables section below for full details. 


## Installing OpenSFM

Due to dependencies, OpenSFM is easiest to use on Linux systems. However, you are free to use whatever system you would like, as long as you produce the deliverables below. One good option for the project is to use Amazon EC2 or another cloud computing service. 

### Amazon EC2 (Optional)
As a student, you should be eligable for [$35-$100](https://aws.amazon.com/blogs/aws/aws-educate-credits-training-content-and-collaboration-for-students-educators/) in AWS credits. If you haven't already burned through your credits, this is a great option for this project, and a good way to get some experience with AWS EC2. General setup instructions:

1. Create an AWS account and launch an EC2 instance.
2. When asked to choose an Amazon Machine Image (AMI), I recommend **Ubuntu Server 16.04 LTS (HVM), SSD Volume Type**
3. For instance type, I've had good luck with **t2.medium**, I wasn't able to get the micro instance to install OpenSFM, I believe due to RAM limitations. 
4. You will likely need to increase your default storage. 
5. Follow Amazon instructions to access your instance via SSH.
6. Create a new inbound rule under Security Groups for your instance. I've had good luck with allowing all traffic from all ports from my IP address. 

### Installation + Running on Ubuntu Linux

**After SSHing into your instance, execute the following commands in your instance**


1. Get the 3D World repository & the OpenSFM repository.

```
git clone https://github.com/unccv/the_3d_world.git
```

```
git clone --recursive https://github.com/mapillary/OpenSfM.git
```

2. Execute the setup script.

```

cd ~/the_3d_world/util
sudo bash ubuntu_setup.sh 

```


3. Install requirements and build OpenSfM:

```
cd ~/OpenSfM
pip install -r requirements.txt
pip install repoze.lru
python setup.py build

```

5. Create a new OpenSfM data directory:

```
cd ~/OpenSfM/data
mkdir -p objects/images
```

6. Copy images from the_3d_word repo to OpenSfM/data/images

```
cp ~/the_3d_world/data/objects/* ~/OpenSfM/data/objects/images/

```

7. Copy over an example config file. From the OpenSfM/data directory:

```
cp ~/OpenSfM/data/berlin/config.yaml objects
```

8. Check out the yaml file. You'll need to make changes to this later:

```
cd objects
nano config.yaml

```

9. Run the OpenSfM pipeline:

```
cd ~/OpenSfM
sudo bin/opensfm_run_all data/objects
```

10. Enjoy watching OpenSfM do a bunch of work for you. 

11. Launch the OpenSfM server:

```
python -m SimpleHTTPServer
```

12. To view your map on your local machine, navigate your browser to 

```
http://XX.XXX.XXX.XXX:8000/viewer/reconstruction.html#file=/data/objects/reconstruction.meshed.json
```

where `XX-XXX-XXX-XXX` is the **Public** IP address of your instance. Note the dashes instead of dots.

### Jupyter Notebook from EC2
You can also serve jupyter notebooks to your local machine from EC2s, [here's](https://medium.com/@alexjsanchez/python-3-notebooks-on-aws-ec2-in-15-mostly-easy-steps-2ec5e662c6c6) a guide. 


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



