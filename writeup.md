## Project: Search and Sample Return
---


[//]: # (Image References)

[image1]: ./misc/rover_image.jpg
[image2]: ./calibration_images/example_grid1.jpg
[image3]: ./calibration_images/example_rock1.jpg 
[image4]: ./output/warped_example.jpg 
[image5]: ./output/mask_example.jpg
[image6]: ./output/rock.jpg
[image7]: ./output/example_rock.jpg

## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points

### Notebook Analysis
#### 1. I added a few lines to `perspect_transform()`, at first I added `mask` (white triangle as u can see on image below) to output warped images, be sure, there won't be any unnecessary pixels or stuff.


![alt text][image4] ![alt text][image5]


#### 2. Next was edited `process_image()`
 * by using `perspect_transform()` I defined `warped` and `mask` which was used by `color_thresh()`, defined as `threshed`, next defined are obstacles and coordinates of the rover `xpix` and `ypix`
 * after defined size of the world `world_size`, using coordinates and angle of yaw, I defined position of the rover on the world map, using class `Databucket` defined as `data`, I set this up
 * next was marking position of rocks by looking for another colours on warped picture, function is using conditional loop to detect any changes of colours, in specified range,  as you can see in the video,on map, path is marked in lighter blue, seen walls darker blue, the rocks are azure, video is named `mapping.mp4`
 * function `find_rocks` are returning images: 
 
 ![alt text][image6] ![alt text][image7]
 

### Autonomous Navigation and Mapping in local files

#### 1. Filling up the `decision_step()` 
 * I was focused to make my Rover drive correctly and I wanted to be sure it will avoid all of obstacles, funtion `time` is added and used in conditional loop writed by me at beginning, making my Rover driving backward I delayed it 2 seconds to be sure he were in right position to continue driving
 * added was `Rover.mode` `backward`, rest of `decision_step()` is not changed
#### 2. Filling up the `perception_step()`
 * I used almost the same functions as I used in Jupyter Notebook document, the differences were that I had to define `source` and `destination` variables, the Rocks are marked on map as squares,
 * The function is also counting finded and collected rocks, which u can see in the simulator on the map
 
