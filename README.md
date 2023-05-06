# Color-Detection-using-Python
Context 



Colour detection is the process of detecting the name of any color. Simple isn’t it? Well, for humans this is an extremely easy task but for computers, it is not straightforward. Human eyes and brains work together to translate light into color. Light receptors that are present in our eyes transmit the signal to the brain. Our brain then recognizes the color. Since childhood, we have mapped certain lights with their color names. We will be using the somewhat same strategy to detect color names.



![color-detection-python-project](https://user-images.githubusercontent.com/89685890/214575711-54a2355b-af79-4e37-bdb7-dd0900369929.gif)



◼ About the Python Project


In this color detection Python project, we are going to build an application through which you can automatically get the name of the color by clicking on them. So for this, we will have a data file that contains the color name and its values. Then we will calculate the distance from each color and find the shortest one.



◼ The Dataset


Colors are made up of 3 primary colors; red, green, and blue. In computers, we define each color value within a range of 0 to 255. So in how many ways we can define a color? The answer is 256*256*256 = 16,581,375. There are approximately 16.5 million different ways to represent a color. In our dataset, we need to map each color’s values with their corresponding names. But don’t worry, we don’t need to map all the values. We will be using a dataset that contains RGB values with their corresponding names. The CSV file for our dataset has been taken from this link: Colors Dataset
The colors.csv file includes 865 color names along with their RGB and hex values.



◼ Prerequisites



Before starting with this Python project with source code, you should be familiar with the computer vision library of Python that is OpenCV and Pandas.
OpenCV, Pandas, and numpy are the Python packages that are necessary for this project in Python. To install them, simply run this pip command in your terminal:

Steps for Building a Project in Python – Color Detection
Here are the steps to build an application in Python that can detect colors:


### Create Files 

The project folder contains 3 files:

  1. Color_detection.py – main source code of our  project.
  2. Colorpic.jpg – sample image for experimenting.
  3. Colors.csv – a file that contains our dataset.


### Taking an image from the user


We are using argparse library to create an argument parser. We can directly give an image path from the command prompt:

![code1](https://user-images.githubusercontent.com/89685890/224466670-be09aca0-9182-4f75-b1cd-698fbbc23c49.png)

### Next, we read the CSV file with pandas


The pandas library is very useful when we need to perform various operations on data files like CSV. pd.read_csv() reads the CSV file and loads it into the pandas DataFrame. We have assigned each column with a name for easy accessing.

![code2](https://user-images.githubusercontent.com/89685890/224466690-e4b3d70d-f803-4ee3-9108-c0431fe545aa.png)

### Set a mouse callback event on a window
First, we created a window in which the input image will display. Then, we set a callback function which will be called when a mouse event happens.

![code3](https://user-images.githubusercontent.com/89685890/224466703-8e46e311-90dd-4661-b0ba-a43fec0402e5.png)

### Create the draw_function
It will calculate the rgb values of the pixel which we double click. The function parameters have the event name, (x,y) coordinates of the mouse position, etc. In the function, we check if the event is double-clicked then we calculate and set the r,g,b values along with x,y positions of the mouse.

### Calculate distance to get color name
We have the r,g and b values. Now, we need another function which will return us the color name from RGB values. To get the color name, we calculate a distance(d) which tells us how close we are to color and choose the one having minimum distance.

Our distance is calculated by this formula:

d = abs(Red – ithRedColor) + (Green – ithGreenColor) + (Blue – ithBlueColor)

![code5](https://user-images.githubusercontent.com/89685890/224466613-9017c760-0738-4b77-8be2-9e7544fde6d5.png)

### Display image on the window
Whenever a double click event occurs, it will update the color name and RGB values on the window.

Using the cv2.imshow() function, we draw the image on the window. When the user double clicks the window, we draw a rectangle and get the color name to draw text on the window using cv2.rectangle and cv2.putText() functions.

![code6](https://user-images.githubusercontent.com/89685890/224466602-ed4cdd8a-b5a9-4b80-a59f-0946eab5c770.png)

### Run Python File
The beginner Python project is now complete, you can run the Python file from the command prompt. Make sure to give an image path using ‘-i’ argument. If the image is in another directory, then you need to give full path of the image:

![code7](https://user-images.githubusercontent.com/89685890/224466555-7aab44a9-684f-4686-86e2-ef36596ebbe2.png)

![code8](https://user-images.githubusercontent.com/89685890/224466579-8672b688-af58-47c5-9fc8-2de435a10213.png)
![code9](https://user-images.githubusercontent.com/89685890/224466585-413af912-e0fa-43dc-944d-b0120caab04e.png)
![code10](https://user-images.githubusercontent.com/89685890/224466589-07101bcf-3c68-40ed-aac1-22ed290b1394.png)


## Output:
Double click on the window to know the name of the pixel color
With these lines, we named our window as ‘image’ and set a callback function which will call the draw_function() whenever a mouse event occurs.

![result1](https://user-images.githubusercontent.com/89685890/224466716-fa35feff-6b38-4fdf-b246-4ad80e6777f6.png)

![result2](https://user-images.githubusercontent.com/89685890/224466721-682160f7-0193-40b9-b097-2cd4539cf6f7.png)

![result3](https://user-images.githubusercontent.com/89685890/224466724-aebd3c5e-7f41-49e7-be02-ea3070185429.png)
Outputs for the same.

If any suggestion or issue, feel free to post it in issue section !!
Thanks !!
More projects works on similar concept
