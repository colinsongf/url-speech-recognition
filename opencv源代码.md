#### 资源汇总
1. [makelove/OpenCV-Python-Tutorial: OpenCV问答群1,QQ群号:187436093](https://github.com/makelove/OpenCV-Python-Tutorial )


#### 技巧优化
1. [Fast, optimized for pixel loops with OpenCV and Python](https://www.pyimagesearch.com/2017/08/28/fast-optimized-for-pixel-loops-with-opencv-and-python/ )
2. [OpenCV Text Detection (EAST text detector)](https://www.pyimagesearch.com/2018/08/20/opencv-text-detection-east-text-detector/# )
3. [10分钟上手，OpenCV自然场景文本检测（Python代码+实现）](https://mp.weixin.qq.com/s?__biz=MzU1NTUxNTM0Mg==&mid=2247489252&idx=1&sn=55da067de1dc0ec93f76eaf98c27a080&chksm=fbd27a45cca5f35378e583266c5534e96669d8ffdccc2680088bd77b4d916a1893fa178ec408 )
4. [How to install OpenCV 4 on Ubuntu](https://www.pyimagesearch.com/2018/08/15/how-to-install-opencv-4-on-ubuntu/ )
5. [OpenCV People Counter](https://www.pyimagesearch.com/2018/08/13/opencv-people-counter/ )
6. [Tracking multiple objects with OpenCV](https://www.pyimagesearch.com/2018/08/06/tracking-multiple-objects-with-opencv/ )
7. [OpenCV Object Tracking](https://www.pyimagesearch.com/2018/07/30/opencv-object-tracking/ )
8. [Simple object tracking with OpenCV](https://www.pyimagesearch.com/2018/07/23/simple-object-tracking-with-opencv/ )
9. [opencv完整入门教程](https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/)
10. [Zero-parameter, automatic Canny edge detection with Python and OpenCV](https://www.pyimagesearch.com/2015/04/06/zero-parameter-automatic-canny-edge-detection-with-python-and-opencv/ )
11. [Python和imutils获取图片的鸟瞰图](https://blog.csdn.net/qq_34199383/article/details/79571318 )
12. [Faster video file FPS with cv2.VideoCapture and OpenCV](https://www.pyimagesearch.com/2017/02/06/faster-video-file-fps-with-cv2-videocapture-and-opencv/ )
13. [(Faster) Non-Maximum Suppression in Python](https://www.pyimagesearch.com/2015/02/16/faster-non-maximum-suppression-python/ )
14. [上述代码](https://github.com/jrosebr1/imutils/blob/master/imutils/object_detection.py#L4 )
15. [Python+OpenCV教程14：轮廓特征](http://ex2tron.top/2017/12/20/Python-OpenCV%E6%95%99%E7%A8%8B14%EF%BC%9A%E8%BD%AE%E5%BB%93%E7%89%B9%E5%BE%81/ )


#### 代码参考
1. cv2.cvtColor：改变颜色空间
- [参考](https://docs.opencv.org/3.0.0/df/d9d/tutorial_py_colorspaces.html)
2. cv2.threshold：阈值函数，如果像素值大于阈值，则它被分配一个值（可以是白色），否则它被分配另一个值（可能是黑色）。
- 参数：四个参数，第一个参数是源图像，它应该是灰度图像。第二个参数是用于对像素值进行分类的阈值。第三个参数是MaxVar，它表示如果像素值大于（有时小于）阈值，则要给出的值。第四个参数Opencv提供了不同的阈值类型
- 输出：img对象
- [参考](https://docs.opencv.org/3.4/d7/d4d/tutorial_py_thresholding.html)
- [Python下opencv使用笔记（四）（图像的阈值处理）](https://blog.csdn.net/on2way/article/details/46812121 )
3. cv2.findContours：寻找轮廓函数
- 参数：三个参数，一是img对象，二是轮廓搜索模式，三是轮廓逼近方式
- 输出：轮廓的列表和层次结构
- [参考](https://docs.opencv.org/3.1.0/d4/d73/tutorial_py_contours_begin.html )
    ```
	import numpy as np
	import cv2

	im = cv2.imread('test.jpg')
	imgray = cv2.cvtColor(im,cv2.COLOR_BGR2GRAY)
	ret,thresh = cv2.threshold(imgray,127,255,0)
	im2, contours, hierarchy = cv2.findContours(thresh,cv2.RETR_TREE,cv2.CHAIN_APPROX_SIMPLE)
	```
4. cv2.getStructuringElement：形态转换
- [参考](https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_imgproc/py_morphological_ops/py_morphological_ops.html)

5. cv2.medianBlur 和 cv2.Laplacian 
- <img src="https://raw.githubusercontent.com/EliasCai/opencv_note/master/images/detect01.PNG" style="width:400px;">
- <img src="https://raw.githubusercontent.com/EliasCai/opencv_note/master/images/detect02.PNG" style="width:400px;">
6. cv2.canny 边缘检测
- <img src="https://raw.githubusercontent.com/EliasCai/opencv_note/master/images/canny01.PNG" alt="drawing" style="width: 400px;"/>
- <img src="https://raw.githubusercontent.com/EliasCai/opencv_note/master/images/canny02.PNG" alt="drawing" style="width: 400px;"/>
7. cv2.canny
- [参考](https://docs.opencv.org/3.1.0/da/d22/tutorial_py_canny.html)
8. cv2.mser
-[参考](https://docs.opencv.org/3.4/d3/d28/classcv_1_1MSER.html)