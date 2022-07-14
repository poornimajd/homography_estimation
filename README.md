# homography_estimation
<h2>What is homography and how to compute it?</h2>
Briefly, the planar homography relates the transformation between two planes (up to a scale factor).
It is a 3x3 matrix,which requires input as the 2D image coordinates,and the corresponding 2D real world coordinates.More details about the basics of homography can be found here-https://docs.opencv.org/4.x/d9/dab/tutorial_homography.html .


<h3>Prerequisites</h3>
The homography method needs the intrinsics of the camera to undistort the image.The intrinsics for the given camera can be computed using opencv.For further details to compute the intrinsics,refer here-https://docs.opencv.org/4.x/dc/dbb/tutorial_py_calibration.html <br />

<h3>Procedure to compute homography</h3>
1. Place some markers on the region of the floor,for which the homography needs to be estimated.The accuracy of the real world position estimates depends on the number of markers,more the number,better the accuracy of the estimated position.The markers also need to be spread apart.<br />
<br />
2. Capture the image,and then undsitort the image.<br />
<br />
3. Manually select the markers in the image to get the 2d image point of the marker.<br />
<br />
4. Note down the corresponding 2D real world positions of the marker in cm or meters.<br />
<br />
5. Divide the points into train and test set.The train set is used to estimate the homography matrix,and test set is to get an estimate of how accurate the homography matrix is.Usually this is quantified by computing the reporjection error between the manually selected test points and the projected 2d test points using the homography matrix.<br />
<br />
6. Feed the train points to the opencv cv2.findhomography API to get the homography matrix estimate and then compute the reprojection error.<br />
<br />

All of the above steps are implemented in the files under compute_homography folder.[todo-change name]<br />





