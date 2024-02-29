**Introduction** 

Detecting Moving Objects in computer vision involves localizing dynamic objects in video sequences. It has advanced from basic frame differencing and background subtraction with static cameras to complex deep-learning models capable of handling dynamic scenes with moving cameras. Classical computer vision techniques like Gaussian Mixture Models were initially employed for static background modeling. 

**Our Approach to Moving Object Detection**

As we are doing moving object detection, our approach will be to get a perfect output containing video frames with proper detections. We will design a pipeline to make an algorithm in which we can achieve our goal.This Moving Object Detection algorithm contains multiple steps, such as Background Subtraction, Global Thresholding,sContour Detection,Bounding Box Prediction.


**Background Subtraction**

The first step of moving object detection is Background subtraction. Using a static camera is a common and widely used technique for generating a foreground mask As the name suggests, Background Subtraction calculates the foreground mask, performing a subtraction between the current frame and a background model, containing the static part of the scene or more in general, everything that can be considered as background given the characteristics of the observed scene.


**Global Thresholding**

For thresholding, we will use cv2.threshold function and pass all the foreground masks as input.For thresholding, we will use cv2.threshold function and pass all the foreground masks as input. We set the threshold value to 25 and the max value to 255, and it will simply replace all the values under 25 and remove all the shadows.

**Contour Detection**

Contours can be explained simply as a curve joining all the continuous points (along the boundary), having the same color or intensity. The contours are useful for shape analysis, object detection, and recognition. OpenCV makes it easy to find and draw contours in images.

**Implementing Background Subtraction**

We need to capture all the video frames and pass them to the code pipeline. Hence we created a video-capture object using cv2.VideoCapture.For background subtraction, we created another object using cv2.cvtColor(img, cv2.COLOR_BGR2GRAY).

**Detecting and Drawing Contours**

After background subtraction, we now have a clear binary mask of our ROI (Region of Interest). So, we will proceed to the contour detection.


**Draw Bounding Boxes**

The next step of moving-object detection is drawing the bounding boxes around the remaining contours. This is where object detection takes place

**Conclusion**

We delved into the core concepts of moving object detection, background subtraction, and contour detection, offering a detailed implementation approach in OpenCV python. Challenges like noise and small contours were addressed through techniques such as image thresholding and morphological operations, enhancing the accuracy of detection.




