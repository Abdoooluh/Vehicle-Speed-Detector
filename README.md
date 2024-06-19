A basic veicle-speed-detector I made using python's CV2 library for image manipulation, back in 2022.
Theory:
The program takes in a video with moving object(s). It retains the video's framerate 
(to determine how much time is elapsed between two frames). Then for each frame, it 
turns the image into gray-scale, separates moving objects from the background, and 
draws bounding boxes to mark the location of each object. The center points of these
bounding boxes on two alternate frames are used to calculate the distance travel by 
each object between two-frames. This distance is then multiplied with a constant ratio
specific to the video (on-screen distance : real life distance) to obtain how much
distance the said object covered in reality. This value can be multiplied with 
1/framerate to obtain the speed of the said object in the last 2 frames.

Room for improvement:
- This code can be modified to use a live video-feed instead of a saved video, for
  making this compatible with cameras
- Support needs to be added for instances when more than  one moving objects are
  in the camera view (to mark and differentiate between bounding boxes)
- Adding an env file that can be used to easily edit the distance constant for each
  video or camera feed.
