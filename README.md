# Orange Counter
A C/C++ application for detecting, tracking, and counting oranges in a video. It uses OpenCV to read and display video frames, along with custom functions (`vc.c`/`vc.h`) for object segmentation and analysis.

## Features

- Segments orange-colored objects in HSV color space and applies morphological operations to reduce noise.
- Filters objects by area, caliber, deformation, fill ratio, and circularity.
- Tracks objects across frames and increments the count when an orange crosses a horizontal line positioned at 65% of the video height.
- Displays each object's ID, measurements, and category, along with the number of oranges in the current frame and the total count.

## Requirements

- Windows and Visual Studio 2022 with the C++ build tools.
- OpenCV 4.13 installed and configured in the project. The current `.vcxproj` settings reference local paths such as `C:\opencv\build` and the `opencv_world4130` library (or `opencv_world4130d` in Debug mode); update them if OpenCV is installed elsewhere.

## Build and Run

1. Open `VC-GY.sln` in Visual Studio.
2. If needed, update the OpenCV include and library paths in the project properties.
3. Select `x64` and the `Debug` or `Release` configuration, then build and run the project.
4. The executable looks for `video.avi` in the current working directory. The repository includes this video at `VC-GY/video.avi`; set `VC-GY` as the working directory or copy the video to the output directory.
5. Press `q` in the video window to exit. Before and after processing, the program waits for Enter in the console before displaying the elapsed time.

## Project Structure

- `VC-GY/Source.cpp` — video reading, tracking, counting, and visualization.
- `VC-GY/vc.c` and `VC-GY/vc.h` — image processing, segmentation, object analysis, and classification.
- `VC-GY/video.avi` — included input video.
- `VC-GY/VC-GY.vcxproj` and `VC-GY.sln` — Visual Studio project and solution.
