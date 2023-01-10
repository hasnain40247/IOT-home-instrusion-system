# IOT-home-instrusion-system

On average, there are about 2.5 million burglaries occurring every year. Out of which, 66% of which are home break-ins. However, the number of these has been steadily decreasing over the past decade specifically because of rapid advancements in technologies and massive amounts of homes taking advantage of smart security devices in their homes as a precautionary measure. 
While these methods are either modularized or exist in discrete entities because of which most of the results are false positives.

This system based on a rasberry PI tries to use motion detection and face capture coupled with a notification system to alert the user about a possible break-in. The system also allows the model to be trained on the face encodings of the owner so as to not mistaken them as an intruder.

![image](https://user-images.githubusercontent.com/52504037/211480647-88896e30-1946-49cd-966f-e972e1639fd9.png)

### Motion Detection
The motion sensor picks up movement by watching the infrared view and picking up the infrared changes. Therefore, with a leaf and a human passing the sensor, it only detects human since we as humans generates heat and thus emits infrared ray. Hence, the motion sensor is a good choice for detecting human movements.
There are three pins for PIR motion sensor, Power, Output and Ground. Under the pins you can see the labels, VCC for Power, Out for Output and GND for ground. When the sensor detects movements, the Output pin will output a HIGH signal to the Raspberry Pi pin that you connect the sensor with.

### Facial Capture
Presently, the face recognition module is coded entirely on python. The working of it is as follows- the python code on first run inputs the legitimate user's face and implements the face_recognition module to compute facial features and positions. These are then encoded into a 128 bit array and is unique to each face. Now that it's trained on the user's face, every other face computed in the camera would be encoded similarly and compared to the saved encodings of the trained data. If the encodings do no match, the intruder is logged into a file with the date and time along with a snap. This data is then sent to the user's mobile and email address.

![image](https://user-images.githubusercontent.com/52504037/211480861-e7263ce9-72a3-4489-9701-a72bcb87cdb9.png)

![image](https://user-images.githubusercontent.com/52504037/211480954-a0e9491d-9dc4-4b54-81b5-cdd5a31fc3de.png)

![image](https://user-images.githubusercontent.com/52504037/211481001-9b755a06-9afa-45d0-945f-361a3db49b81.png)

