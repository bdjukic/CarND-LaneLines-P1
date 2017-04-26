# Finding Lane Lines on the Road

This is my first project in [Udacity self-driving car course](http://udacity.com/drive). The goal of this project is creating a software pipeline which is capable of identifying lanes on the road in a video from a front-facing camera on a car.

## Data Preprocessing
We will be converting video frames into gray scale images as a preprocessing step in our pipeline. Afterwards we would apply Gaussian Noise kernel.

## Pipeline
Once preprocessing is done we will be using Canny edge detector on our video stream and getting our region of interest based on the vertices coordinates. 

We will provide the result from above to Hough Transform operation which will return us lines which are an array containing the endpoints of all line segments detected by the transform operation. The resulting array will be used to draw the lines on the input image. 

### Final outcome

This is the final outcome of the video pipeline:

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/RbXp4y-u8j8/0.jpg)](https://www.youtube.com/watch?v=RbXp4y-u8j8)

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/epgsA3t0Gzk/0.jpg)](https://www.youtube.com/watch?v=epgsA3t0Gzk)

### Conclusion

I've spent most of my time on the algorithm for lane extrapolations. 

One idea for making the algorithm better would be better parameterization of my _find_road_lanes_ method (in terms of area of interest). This is something which needs to be fixed in order for final challenge video to work properly. further improvement would be to use different color space than gray scale (HSL and it's L channel maybe in order to address issues with shadows). 

The approach which is implemented here also is not able to detect curvature of the lanes on the road. 

Since this approach is based on camera it's prone to usual challenges with this kind of sensor (bad visibility, reflections, shadows, etc.).

Project can be found on my [Github](https://github.com/bdjukic/CarND-LaneLines-P1) profile.
