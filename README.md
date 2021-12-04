# webcam_switcher

This project is based on Juan Camilo López Montes's frontal face and profile detection code, which uses OpenCV haar cascades files.

My variation on it in this project is that I use it to determine which camera a person is looking at. In the scenario where you are working from a laptop with built in webcam and also have an external monitor with a webcam sat on top, this code will determine if you are looking at the latop or looking away and it will send a websocket call to OBS (Open Broadcasting Software) to switch the scene.

Which means when using Teams, Zoom, Slack etc connected to the OBS virtual web cam you will always have a frontal view showing as the scene gets switched to the camera that you are looking at.

In OBS inport the thw webcam on the laptop as one video capture device and import the external webcam that is sat on the monitor as a second capture device.

Now create a scene called "Right", to this scene, add the video capture device that is on your right hand side.
Create a scene called "Left", to this scene, add the video capture device that is on your left hand side.

In OBS enable obswebsocket and set a password. Change the password in obssocket.py to match this password. Also verfiy that in you have the correct video camera selected for determining the face detection ( change the cv2.VideoCapture(0) line in webcam_switcher if needs be)

Run the webcam_swicther.py and you should see the scenes switching in OBS as you turn your head towards on camera or the other.

To use in Teams/Zoom/Slack etc, start the virtual webcam in OBS and use that as the source camera in these apps.