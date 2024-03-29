# Smart_CCTV_using_TelegramBot
# CVZone

[![Downloads](https://pepy.tech/badge/cvzone)](https://pepy.tech/project/cvzone)
[![Downloads](https://pepy.tech/badge/cvzone/month)](https://pepy.tech/project/cvzone)
[![Downloads](https://pepy.tech/badge/cvzone/week)](https://pepy.tech/project/cvzone)



This is a Computer vision package that makes its easy to run Image processing and AI functions. At the core it uses [OpenCV](https://github.com/opencv/opencv) and [Mediapipe](https://github.com/google/mediapipe) libraries. 

## Installation
You can  simply use pip to install the latest version of cvzone.

`pip install cvzone`

<hr>

## Pose Estimation

<hr>

<p align="center">
  <img width="640" height="360" src="https://www.computervision.zone/wp-content/uploads/2021/04/vlcsnap-2021-03-27-22h34m51s546.jpg">
</p>

<pre>
from cvzone.PoseModule import PoseDetector
import cv2

cap = cv2.VideoCapture(0)
detector = PoseDetector()
while True:
    success, img = cap.read()
    img = detector.findPose(img)
    lmList, bboxInfo = detector.findPosition(img, bboxWithHands=False)
    if bboxInfo:
        center = bboxInfo["center"]
        cv2.circle(img, center, 5, (255, 0, 255), cv2.FILLED)

    cv2.imshow("Image", img)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

</pre>

