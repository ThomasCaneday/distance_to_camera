# Distance to Camera

## Overview
This Python program calculates the distance between a camera and an object in a series of images. It uses computer vision techniques such as edge detection and contour analysis to locate a specific object (a piece of paper in this case) in an image and then calculates the distance based on the known width of the object and its perceived width in the image.

## Requirements
- Python 3.x
- OpenCV (`cv2`)
- `imutils` package
- `numpy`

To install the required packages, you can use the following command:
```bash
pip install opencv-python imutils numpy
```

## How It Works
The program calculates the distance to the camera using the formula:

\[
\text{distance} = \frac{\text{known width} \times \text{focal length}}{\text{perceived width}}
\]

### Key Steps:
1. **Marker Detection**: 
   - The object (e.g., a piece of paper) is detected in the image by converting the image to grayscale, applying a Gaussian blur, and then detecting edges using the Canny edge detector. The largest contour is assumed to be the object of interest.
   
2. **Distance Calculation**:
   - Using the known width of the object (in inches) and the focal length of the camera, the program calculates the distance of the object from the camera based on the perceived width of the object in the image.

3. **Bounding Box and Display**:
   - A bounding box is drawn around the detected object, and the calculated distance (in feet) is displayed on the image.

## Program Flow
1. The program initializes with a known distance and object width.
2. It uses the first image (known to be at a set distance) to calculate the camera's focal length.
3. The program loops over a set of images, calculating and displaying the distance of the object from the camera for each image.

## Usage
1. Place the images of the object at different distances in an `images/` directory.
2. Modify the `KNOWN_DISTANCE` and `KNOWN_WIDTH` variables to match the actual setup (e.g., known distance and width of the object).
3. Run the program to process the images and compute the distance for each one.

```bash
python distance_to_camera.py
```

## Example
If the object is a piece of paper with a width of 11 inches and the first image is taken from 24 inches away, the program calculates the camera’s focal length. It then uses this information to calculate the distance of the object in other images based on its perceived width in those images.

## Notes
- Ensure the images are clear and the object is well-defined for accurate distance calculations.
- You can change the object type and its known width as needed.

## License
This project is licensed under the MIT License.
