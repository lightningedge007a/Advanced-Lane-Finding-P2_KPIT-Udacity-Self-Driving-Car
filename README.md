# Advanced-Lane-Finding-P2_KPIT-Udacity-Self-Driving-Car


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


[image10]: ./DisplayWriteUp/undistorted.jpg "undistorted"

[image11]: ./DisplayWriteUp/detectlanes2.png "detect lanes"
[image12]: ./DisplayWriteUp/warped2.png "warped 2"

Steps:-

![alt text][image9]

Distortion correction:

Camera matrix and distortion coeffs were calculated for the chess board images to undistort the image. ouput is saved in output_images/camera_cal .

![alt text][image1]

![alt text][image10]

Thresholding:

I applied thresholds on colors and gradients(rgb,hls) to get a binary threshold black and white image

![alt text][image2]

Perspective transform:

Chose vertices to make a trapezium and transformed to bird's eye view.

![alt text][image12]
![alt text][image3]

![alt text][image4]

Sliding window search:

Calculated position with the help of histogram and drew lane lines and took a margin to 50 pixels to detect the lane lines as a generic broad lane to be followed.

![alt text][image5]

![alt text][image11]

ROC:

Calc. radius of curvature and centre offset


Inverse transform and Coloring Green:

Color the road between lanes and inverse transform it form bird eye view back to driver's view and overlap the colored image with the original one

![alt text][image6]

![alt text][image7]

Pipeline

Applied the functions sequentially to the video


![alt text][image8]
The notebook to refer is **camera_cal_3.ipynb** in main directory and the videos are 

**project_video_solution_3.mp4**


**If images dont display go  to the DisplayWriteUp folder to view output images for "test6" image. And rest images of output are in output_images folder**


# Problems solved in this submission

1. Distortion calculated :)

def get_thresholded_image(img):
    cameraMatrix=mtx
    distortionCoeffs=dist
    img = cv2.undistort(img, cameraMatrix, distortionCoeffs, None, cameraMatrix)
    plt.imsave('DisplayWriteUp/'+'undistorted.jpg',img)
    
    ......rest of function in notebook cell 

2. Warped lines are parallel no matter how tilted they get :)

3. Changed shape of polygon to detect the curving road to left accurately :)

4. Discussion

# Discussion


As such I didn't document the problems faced in detail (sorry this is my first writeup) but most problems were with Gradient & Color Thresholding (chosing parameters), detecting lane lines , and taking out radius of curature in the image (had math difficulty in figuring this out).

Faced some installation problems too! but had to work on workspace because of bad machine and software issues with ubuntu 18.04

The pipeline seems to fail for the harder challenge video. This video has sharper turns and at very short intervals
I could take a better perspective transform with a trapezuim of small height
