# Tree Tracks

This repository contains the application that works with user submitted video recordings and GPS tracks to identify trees.

This is a helper tool for the Tree Maps application.


## User Experience

The user records a video file of a street or any location, pointing the camera to the left or right, while walking or driving.
The GPS track is recorded simultaneously, capturing the path taken during the video recording.
Both produced files are uploaded to the application.

The files are then split into a series of geo-tagged images.
Those series of images are presented to the user with a UI similar to Street View.

The user can navigate back and forth within the track to find unique trees.
When a tree is found, the user can mark it on the map, using the current frame GPS location as a hint, and submit it to the database.

When the user finishes processing a track, they can export all collected trees with their GPS locations and images to a JSON file.
That file can then be imported in the Tree Maps application.


## Data Processing

When the files are uploaded, we split them into static images, extracting every 10th frame from the video.
The images are then geo-tagged with the GPS coordinates from the GPX track.
Both file names and GPS coordinates are stored in the database as separate records.
Those records represent the track.

There is no automated image processing at this moment.
