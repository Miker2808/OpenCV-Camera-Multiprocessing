# OpenCV-Camera-Multiprocessing
A python file with ready made multiprocessing for OpenCV
It runs the camera and the algorithm on a seperate process.
How does it work:
The camera reads a frame and sends it to the algorithm process using a two-way pipe. when the algorithm gets the frame it sends
a "BUSY" flag to the camera to tell it to run the frames and by this empty the buffer. when the algorithm is done it sends a "READY" flag to the camera and tells it that it is done, the camera in return sends another frame to the camera.
This process can send few frames at the time before locking the camera (for example if you do a background subtraction, you can send 2 frames at a time)
you can simply play with the flags to decide when to receive a frame and when not.

The idea of this python file is to ease with people sturggling with a buffer and want a ready solution.

Requirements:
Python 3
Opencv for python
numpy
