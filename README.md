# Image stitching using OpenCV

```python
# Reading the image data.
left_img = cv2.imread('./Images/mall1.jpg')
cent_img = cv2.imread('./Images/mall2.jpg')
right_img = cv2.imread('./Images/mall3.jpg')

# Initializing the OpenCV image stitcher.
stitcher = cv2.Stitcher_create()

# Stitching the left, center and right images together.
status, panorama = stitcher.stitch((left_img, cent_img, right_img))

if status == cv2.Stitcher_OK:
    # Stitching was successful
    # Convert and display the stitched image
    plt.imshow(cv2.cvtColor(panorama, cv2.COLOR_BGR2RGB))
    plt.axis('off')  # Turn off axis
    plt.show()
else:
    # Stitching failed
    print("Stitching failed with status code:", status)
```




Resources:-

- [Image Stitching with OpenCV and Python](https://pyimagesearch.com/2018/12/17/image-stitching-with-opencv-and-python/)
