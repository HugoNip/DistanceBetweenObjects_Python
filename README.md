## Measuring distance between objects

![distance_between_objects_result_01.gif](https://github.com/HugoNip/DistanceBetweenObjects_Python/blob/master/images/distance_between_objects_result_01.gif)

[Source](https://www.pyimagesearch.com/2016/04/04/measuring-distance-between-objects-in-an-image-with-opencv/)  

Our goal in this image is to 
1. find the quarter
2. use the dimensions of the quarter to measure the distance between the quarter and all other objects.

## Algorithm
1. Confirm the reference object and its deminsions.  
2. Detect the objects and get the bounding box for each objects.  
3. Compute the distance.  

## Property
1. We know the dimensions of the object in some measurable unit (such as inches, millimeters, etc.).  
2. We can easily find and identify the reference object in our image.  

Just as we did last week, we’ll be using a US quarter 
as our reference object which has a width of 0.955 inches (satisfying Property #1).  
We’ll also ensure that our quarter is always the left-most object in our image,
thereby satisfying Property #2.

## Usage
### distance_between.py
Compute distance between the respective corners and centroids of objects in images.  
```
$ python distance_between.py --image images/example_01.png --width 0.955
$ python distance_between.py --image images/example_02.png --width 0.955
$ python distance_between.py --image images/example_03.png --width 3.5
```
**--image** is the path to the input image containing the objects we want to measure.  
**--width** is the width (in inches) of our reference object.  

### img_center_distance_between.py
Compute the distance between the centroids of objects in images.  
```
$ python img_center_distance_between.py
```

### video_center_distance_between.py
Real-time compute the distance between the centroids of objects in videos.  
```
$ python video_center_distance_between.py
```

## Requirement
1. OpenCV > 2.4 (test by OpenCV 4.4.0)  
2. Python > 2.7 (test by Python 3.7)  
3. imutils (Package)  
If you don’t already have the imutils package installed, stop now to install it:  
```
$ pip install imutils

```
Otherwise, you should upgrade to the latest version 
(0.3.6  at the time of this writing) so you have the updated order_points function:  
```
$ pip install --upgrade imutils
```
