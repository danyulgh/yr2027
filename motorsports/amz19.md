> introduction to driverless

SLAM system
* Simultaneous Localization and Mapping
* Builds a map of an unknown area while tracking a device's exact location within the area

### perception
* input:
	* LiDAR
	* Vision
* output:
	* cone detection
	* 3d pose estimation of cones
	* colour cones
1. ground removal algorithm
![[Screenshot 2026-10-03 at 2.55.08 PM.png]]
2. cone detection
	* cluster points after ground removal
	* reconstruct cylindrical area around each cluster using points pre-ground removal
3. cone pattern
	* map 3d bounding box of cone cluster where cluster center is mapped to center of image
		* scale points in cluster to fit in the 32x32 image
	*
### motion estimation & mapping
* input:
	* cone positions
	* sensor measurements (relation to velocity)
* output:
	* map the track
	* detect boundaries
	* estimate physical state of car
1. velocity estimation
2. SLAM algorithm
	* cones = landmarks
	* velocity estimate = motion model
3. boundary estimation
	* even if there was color misclassification

todo
* spencer (controls), leo (auton), slam (sophie)
* make my sim do what they all want