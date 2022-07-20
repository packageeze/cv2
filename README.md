# sketch of an image
import cv2
img=cv2.imread("filename.jpg")
img_grey=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
invert=cv2.bitwise_not(img_grey)
blur=cv2.GaussianBlur(invert,(27,27),0)
invertedblur=cv2.bitwise_not(blur)
sketch=cv2.divide(img_grey,invertedblur,scale=256.0)
cv2.imwrite('sketch.png',sketch)
