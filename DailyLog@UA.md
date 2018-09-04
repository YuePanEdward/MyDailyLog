# 2018.7.14(Very Important): 
Finally, the resolution and graphic card problem of my ubuntu16.04 is solved.

It's really frustrating for having Nvidia independent graphic card togther with Intel intergrated graphic card on my laptop.

Follow the instruction here when you cannot login with out the recovery mood: 
https://blog.csdn.net/kilotwo/article/details/79258107

And if you meet the problem of login loop, please refer to here: 
https://blog.csdn.net/ssmixi/article/details/73483795

And when you install the drvier, remember that you should not update(or something like that) the kernel and do not adpat the X server.

After that, for use the intel graphic card without Nvidia one, you need to install the bumblee-Nvidia to switch between the graphic cards.

# 2018.7.14(Important): 

Solved the source problem with aliyun

It's not in China, so gedit the /etc/apt/source.list file and delete aliyun sources or there would be unmet dependency error when you do apt-get xxx things.

Add -f after the apt-get to get through this problem.

For more details, please refer to https://askubuntu.com/questions/140246/how-do-i-resolve-unmet-dependencies-after-adding-a-ppa.
 
# 2018.7.23(Very Important): 

When constructing the connection between computer(desktop or laptop) and the robot (jackal), you need to edit the /etc/hosts file and add "192.168.0.1 jackal" (Host IP and Host name) to it except for edit the ~/.bashrc file. Or your computer won't accept the message coming from the robot.

# 2018.7.25(Daily):

Review pointcloud registration method such as 4PCS and Super4PCS, they are the improvement version of RANSAC (which has o(n^3) complexity according to the paper).

### 4PCS:o(n^2)
Use the stable affine transformation property for 4 points set. It's really robust to noise.

### Super4PCS:o(n)
Improve 4PCS by using the intelligent indexing strategy so its efficiency is literally awesome. It applys the quatra-tree and angle-distance hash stuff according to the paper. 

Reviewer of 3DV2018 said it shall be the baseline of my algorithm so I' will try it on a bit more large scale point clouds.

### Details: 4pcs and super4pcs
#### RANSAC o(n^3)
#### 4PCS   o(n^2)
#### Super 4PCS o(n)

4PCS for two pointcloud S and T

find several(L) 4 approximate coplanar points from S,called the group M.

Then use the d1,d2,e1,e2 to find the candidate 4point groups in T, which meets the affine transformation's property.

And then use the angle alpha to delete some impossible candidates.

Then use RANSAC's scheme to get the best one from these candidates, which giving a better efficiency than RANSAC.

Super4PCS use the smart indexing strategy for both d's search (search candidate pairs) and 
the further selecting so that have a linear complexity, which is progressison of 4PCS.

For more details,please refer to https://blog.csdn.net/Ha_ku/article/details/79480613.

4PCS's PPT and project website http://graphics.stanford.edu/~niloy/research/fpcs/fpcs_sig_08.html.

Super4PCS's PPT and project website http://geometry.cs.ucl.ac.uk/projects/2014/super4PCS/.

May be I will further write a Zhihu Anwser on it.  

### Codes: 
#### 4PCS 
http://docs.pointclouds.org/trunk/classpcl_1_1registration_1_1_f_p_c_s_initial_alignment.html
#### Super4PCS 
https://github.com/nmellado/Super4PCS  
#### run Super4PCS on ubuntu 
https://blog.csdn.net/Yangzhihua1347142721/article/details/50205237

# 2018.7.26(Daily):

Tuning the parameters of Google Cartographer really sucks but I've sloved a part of them, at less the fact that Jackal can do basic mapping and localization around the lab and corridor. 

The problem is mainly due to the rotation, the absence of IMU and the failure of loop closure detection.

Jackal's system setting: Once jackal is powered on, ros.launch is launched
the automatic launch tree is listed below

> ros.launch->accessories.launch

>          ->base.launch        ->description.launch(something about urdf, published by robot_state_publisher)

>                               ->control.launch(ekf_localization_node, about the sensor intergration)

>                               ->teleop.launch(connect with PS4 joystick by publishing geometry_msgs/Twist, specialfized in the robot_localization.yaml file)

According to http://docs.ros.org/melodic/api/robot_localization/html/index.html#

All the state estimation nodes in robot_localization share common features, namely:

   ### Fusion of an arbitrary number of sensors.
   The nodes do not restrict the number of input sources. If, for example, your robot has multiple IMUs or multiple sources of odometry information, the state estimation nodes within robot_localization can support all of them.
   
   ### Support for multiple ROS message types.
   All state estimation nodes in robot_localization can take in nav_msgs/Odometry, sensor_msgs/Imu, geometry_msgs/PoseWithCovarianceStamped, or geometry_msgs/TwistWithCovarianceStamped messages.
   
   ### Per-sensor input customization.
   If a given sensor message contains data that you don’t want to include in your state estimate, the state estimation nodes in robot_localization allow you to exclude that data on a per-sensor basis.
   
   ### Continuous estimation.
   Each state estimation node in robot_localization begins estimating the vehicle’s state as soon as it receives a single measurement. If there is a holiday in the sensor data (i.e., a long period in which no data is received), the filter will continue to estimate the robot’s state via an internal motion model.

   All state estimation nodes track the 15-dimensional state of the vehicle: (X,Y,Z,roll,pitch,yaw,X˙,Y˙,Z˙,roll˙,pitch˙,yaw˙,X¨,Y¨,Z¨)

# 2018.7.27(Daily):

Try to configure the GPS RTK on jackal. A lot of stuffs to done.

For details of the setup of GPS and RTK, please refer to the formal document and the experiment log given by Noal. 

Noal is a awesome guy, I will miss him.

Besides, I fork the personal website of Zhangyixiao to construct my own website. I suppose it's not a plagrisim or something like that. Anyway, thanks, Zhang yixiao.

# 2018.7.29(Daily):
An excellent blog for pointcloud registration, see: https://www.cnblogs.com/yhlx125/p/4955337.html

# 2018.8.8(Important): 
Reinstall Rtabmap on my desktop

I Can't compile the rtabmap_ros package, something wrong with opencv version collision.

search for the version command : pkg-config --modversion opencv

Tasks given by Martin:

### 1.Cartographer parameter tunning document

### 2.Cartographer accuracy measurement (2+ ways ) and see if it has the covariance

### 3.Cartographer outdoor sensor fusion test: how to use gps rtk 

By the way, setup gps rtk and figure out how to transfer its coordinate system

### 4.Cartographer indoor sensor fusion test togther with Rtabmap

for details, you can refer to 8.9's log. The map is not vital, what we really care about is the robot's pose.

Remember rtabmap has a mapping and localization process respectively, so determine which one is better for the pose. 
If VO is really slow and unaccepteable, we can try to replace it with the /odometry/filtered as the input of ratbmap mapping process for better performance

### 5. Velodyne Calibration

### 6. （Optional）Jetson setup and the installation of all kinds of sensor driver. Oh my god, it's really frustrating.

### 7. （Optional）LOAM test， find out if there's a ros opensource package for V-LOAM， which is the state-of-art for Viusl-Laser-Intergrated SLAM solution.

### 8. Others......

Other Tasks for me:

### 1.Finish the paper for ISPRS, conduct the following experiment:

#### (1) To prove global optimal matching is better than closest point. Conduct this one without hybrid metric.

#### (2) To prove hybrid metric is better than single metric. 

#### (3) More comparsion with state-of-art solutions like 4PCS,Super4PCS...etc.

### 2.INS project Android programming 

### 3. Making poster for SLAM project and IGSP 3DV-Conference

Everything sucks, but you need to persist.
You need to trust yourself.

# 2018.8.9(Daily): 

Finally, I managed to install rtabmap on my laptop. I think the main problem falls on the version collision of opencv 
The preinstall opencv is on 2.4.11 but the opencv provided by rtabmap dependency is not the same.

So I have to install it on another computer that is free of opencv (no preinstalled opencv) because I don't actually know how to remove the opencv completely.

For Rtabmap, as the visualization part is really slow and often stuck on Jackal's own computer, we decide to run rtabmap slam calculation on  Jcakal's inner computer (provided the trajectory /visual odometry of the robot) and just use the laptop to visualize it. 

It works but there are still some problem of the tf. It really sucks.

The Next step is to record all the data and compare the pose of robot for 
### 1: Rtabmap with different sensor integrated in EKF 
navigation mode output ekf-global
### 2: Cartographer with different sensor intergrated and different parameter setting
directly output /trajectory_node_list
### 3: Vicon Ground Truth 
output /vicon/jackal

(You need a transformation from map frame {vicon data fixed to} to odom frame {robot trajectory refer to}, the starting point of robot)

Fortunately, this work has been done by Ruifan via a matlab programme

### 4: Other SLAM algorithm's result

Maybe I won't go to Italy to attend the conference 3DV2018. It sucks. Something to arrange. 

# 2018.8.10(Daily): 
Try to compare among ekf_odom0(old_imu+wheeled odom,topic name:odometry/filtered),ekf_odom1(kvh1750_imu+wheeled odom,topic name:odometry/filtered1) and visual odom(topic name:rtabmap/odom)

The startup launch file of ekf_odom1 is jackal/control control_1.launch

Some problem of odom conflict. ekf_localization, ekf_localization1 and rtabmap odom all related to odom.

so the odom frmae in tf tree keeps changing. Oh my god, that's frustrating.

# 2018.8.11（Daily）：
Add a visualiztion function to IGSP so that we don't need to use cloudcompare to see the result.

Push it to github. Next step is to make a video about it and finish the ISPRS paper.

# 2018.8.12（Daily）：
Finish the IGSP video and then refine my website. 

# 2018.8.13（Daily）：
The problem of g2o graph optimaization failure is sloved by installing GTSAM (another useful graph optimization tool)

website:https://bitbucket.org/gtborg/gtsam

#### What is GTSAM?

GTSAM is a library of C++ classes that implement smoothing and mapping (SAM) in robotics and vision, using factor graphs and Bayes networks as the underlying computing paradigm rather than sparse matrices.

On top of the C++ library, GTSAM includes a MATLAB interface (enable GTSAM_INSTALL_MATLAB_TOOLBOX in CMake to build it). A Python interface is under development.

# 2018.8.15（Daily）：
Note: How to use git on Ubuntu?

1. git clone the repository to your desktop

2. cd to the folder

3. git pull origin master

4. do some change

5. git add --all  (please wait)

6. git commit -m "some comment"

7. git push origin master

8. Input your username and password

Another thing: Everytime g2o can't work well, just remember to edit the ekf_config file, you do not need to actually change it, however you need to reload it.




# 2018.8.16(Daily):
Everytime g2o can't work well, it's the problem of $ROS_PACKAGE_PATH
You need to reset the path to include /opt/ros/kinetic/share something like that.
It's so stupid.

# 2018.8.22（Daily):
A poster symposuim 
Really tired
I nedd to focus on TOEFL.

# 2018.8.24 (Daily):
My English really sucks. Three months is still not enough for me to improve my Engilsh to a certain level so from my perspective, I still can't make any great progress this time for the TOEFL exam. I am just kicked at my ass this time and my oral English make me frustrating.

# 2018.8.25（Daily）：
TOEFL Test today.
The wrost thing is that I burned my own hands, which is really painful. It mitigate a bit after six hours.

# 2018.8.29 (Daily):
For these three days, I finished the IGSP video and poster. Besides, I translated part of my paper and apply for green valley.
I feel that all the other students here are so excellent and outstanding. I am just a little nobody. 
What if I can't change anything even though I work reallt hard?
I comfort myself that I can walk through it and I can be who I am.
However......
Come on, man. 

My plan for my undergraduate final year
1.Keep exercising and playing football (play for Zhenxing Cup)
2.Keep practicing my English
3.Apply for graduate school (listed in Evernote)
4.Learn driving
5.Internship in green valley.
6.Be more open-mind and more outgoing. Try something new bravely and come out of your safety zone. Be confident and try to make friends with more people.
7.Pay attention to your own apperance. Dress decently and be more handsome and attractive.
8.Try to help others and cultivate your leadership
9.Don't waste your precious time. Hardworking does not mean the final success but it can really change something.

Use a poem to sum up

Do not go gently into that good night.

Rage,rage, against the dying of light.

# 2018.9.3 （Important）：
Don't be too lazy.
Please be self-disciplined.

To slove Android Studio Gradle problem
in build.gradle

change the content to



    apply plugin: 'com.android.application'
    
    android {
    compileSdkVersion 26
    buildToolsVersion "27.0.1"
    
    defaultConfig {
        applicationId "com.test.measureapp"
        minSdkVersion 15
        targetSdkVersion 26
        versionCode 1
        versionName "1.0"
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
    }
    dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])
    testCompile 'junit:junit:4.12'
    compile 'com.android.support:appcompat-v7:26.+'
    compile 'com.android.support:design:26.+'
}

It really works. Never forget this solution

Fuck off, my TOEFL
R30 L30 S19 W24 
Fuck my speaking and writing
Please keep practicing your speaking and writing and compare it with the best answers.
Pursue the exllecence.
