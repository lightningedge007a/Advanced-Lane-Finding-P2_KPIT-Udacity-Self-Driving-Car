## Writeup Template


[//]: # (Image References)

[image1]: ./DisplayWriteUp/calibration12.jpg "Undistorted"

[image2]: ./DisplayWriteUp/thresholded.jpg "thresholded"

[image3]: ./DisplayWriteUp/warped.jpg "warped"

[image4]: ./DisplayWriteUp/out_img.jpg "warped"

[image5]: ./DisplayWriteUp/detectedlanelines.png "lane lines"

[image6]: ./DisplayWriteUp/unwarped.jpg "unwarped"

[image7]: ./DisplayWriteUp/result.jpg "result"

[image8]: ./DisplayWriteUp/finalimg.png "final img"


[image9]: ./test_images/test6.jpg "test img"


Steps:-

![alt text][image9]

Distortion correction:

Camera matrix and distortion coeffs were calculated for the chess board images to undistort the image. ouput is saved in output_images/camera_cal .

![alt text][image1]

Thresholding:

I applied thresholds on colors and gradients(rgb,hls) to get a binary threshold black and white image

![alt text][image2]

Perspective transform:

Chose vertices to make a trapezium and transformed to bird's eye view.

![alt text][image3]

![alt text][image4]

Sliding window search:

Calculated position with the help of histogram and drew lane lines and took a margin to 50 pixels to detect the lane lines as a generic broad lane to be followed.

![alt text][image5]

ROC:

Calc. radius of curvature and centre offset


Inverse transform and Coloring Green:

Color the road between lanes and inverse transform it form bird eye view back to driver's view and overlap the colored image with the original one

![alt text][image6]

![alt text][image7]

Pipeline

Applied the functions sequentially to the video


![alt text][image8]
The notebook to refer is **camera_cal.ipynb** in main directory and the videos are 
**
project_video_solution.mp4

challenge_video_solution.mp4

harder_challenge_video_solution.mp4
**
**If images dont display go  to the DisplayWriteUp folder to view output images for "test6" image. And rest images of output are in output_images folder**


