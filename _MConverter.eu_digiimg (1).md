---
jupyter:
  kernelspec:
    display_name: Python (opencv-env1)
    language: python
    name: opencv-env
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.13.14
  nbformat: 4
  nbformat_minor: 5
---

::: {#289b8bad-8d98-4118-8b25-0475a300941c .cell .raw}
```{=ipynb}
Step1:
Load an image from your local directory and display it.
```
:::

::: {#5d1611dc-4412-4b74-92b9-ee6ec9edb4e0 .cell .code execution_count="1"}
``` python
import cv2
import matplotlib.pyplot as plt
```
:::

::: {#4a6e481a-4e8c-4ef0-814e-8d35f0bf032d .cell .code execution_count="2"}
``` python
# Read the image using OpenCV
img = cv2.imread('img3.png', cv2.IMREAD_COLOR)
```
:::

::: {#5a6f5d2c-92b1-46ab-a7df-8fc6bb2e9ee4 .cell .code execution_count="3"}
``` python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
:::

:::: {#3e8485ab-9443-485c-a59e-59165292caf1 .cell .code execution_count="4"}
``` python
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

::: {.output .display_data}
![](d46dd79827f2c94199903a36f694c45e4f2762c2.png)
:::
::::

::: {#5005da6d-91bc-41bc-8185-8edfaa6984d1 .cell .raw}
```{=ipynb}
Step2:
o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image. 

o Draw a rectangle around a specific region of interest in the image. 

o Add the text "OpenCV Drawing" at the top-left corner of the image.
```
:::

::: {#193096e4-5f54-4550-a6da-d449db3f5c5b .cell .raw}
```{=ipynb}
Draw a line from the top-left to the bottom-right of the image
```
:::

::: {#a57dc044-9b0b-4449-b727-b79d9624b2b5 .cell .code execution_count="5"}
``` python
# Load the image
image = cv2.imread('img3.png') 
```
:::

::: {#64425575-b842-457d-8c40-f1c6f1a3ef1f .cell .code execution_count="6"}
``` python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
:::

:::: {#32fcff7f-9dfe-4790-8395-c46f46b2d77f .cell .code execution_count="7"}
``` python
img_rgb.shape
```

::: {.output .execute_result execution_count="7"}
    (473, 610, 3)
:::
::::

::: {#f2342f2b-3b6e-4720-ad14-75e566259a20 .cell .code execution_count="8"}
``` python
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
```
:::

:::: {#c1fadb28-3d17-403c-bafc-cb5f858d6085 .cell .code execution_count="9"}
``` python
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

::: {.output .display_data}
![](08c9da34744309bbf767571f47d82c15d223ca6f.png)
:::
::::

::: {#e2f4661e-a804-4a80-b11c-9b38214a2804 .cell .raw}
```{=ipynb}
Draw a circle at the center of the image.
```
:::

::: {#9a63215e-55b0-435d-af60-e786602274e8 .cell .code execution_count="46"}
``` python
# Load the image
image = cv2.imread('img3.png') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
:::

:::: {#944e9dd8-fc28-485e-9d05-9237d2e12cb1 .cell .code execution_count="47"}
``` python
img_rgb.shape
```

::: {.output .execute_result execution_count="47"}
    (473, 610, 3)
:::
::::

::: {#44f3f857-9fb8-4be1-ba99-5723cbe0719f .cell .code execution_count="48"}
``` python
circle_img = cv2.circle(img_rgb,(450,250),160,(255,0,0),5) # cv2.circle(image, center, radius, color, thickness)
```
:::

:::: {#1066d6b8-501f-4280-b962-cdbe9260f8b4 .cell .code execution_count="49"}
``` python
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

::: {.output .display_data}
![](75e278fba7f96403fdd4473ecce900c8a619ad0d.png)
:::
::::

::: {#1fc3d85b-1d1f-4ad2-9bbb-65396b1bba47 .cell .raw}
```{=ipynb}
Draw a rectangle around  the whole image
```
:::

::: {#8ff15797-ba05-43aa-9340-d96fcb8a8e57 .cell .code execution_count="101"}
``` python
# Load the image
image = cv2.imread('img3.png') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
:::

:::: {#a04c1c7f-0ca8-4e79-adbb-a308e9133347 .cell .code execution_count="102"}
``` python
img.shape
```

::: {.output .execute_result execution_count="102"}
    (473, 610, 3)
:::
::::

::: {#fe84a910-7c0f-4389-898e-9680544c679b .cell .code execution_count="103"}
``` python
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (610, 470), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
```
:::

:::: {#e1cee884-a97c-4471-800b-ac8ea7091270 .cell .code execution_count="104"}
``` python
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

::: {.output .display_data}
![](36ee3cc4e53a084fc29f0d8e527d3587d81d2e2c.png)
:::
::::

::: {#33d7b233-1748-47ca-be9b-2a65a0d9c15b .cell .raw}
```{=ipynb}
Add the text "OpenCV Drawing" at the top-left corner of the image.
```
:::

::: {#c74c46e6-cd99-4027-989f-e764bd4ca21e .cell .code execution_count="105"}
``` python
# Load the image
image = cv2.imread('img3.png') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
:::

::: {#5f820408-91de-43d7-b4da-688f48566b90 .cell .code execution_count="106"}
``` python
# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
```
:::

:::: {#b8d2e84e-8b79-4cae-8c63-29cd8cfdb76d .cell .code execution_count="107"}
``` python
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

::: {.output .display_data}
![](18e1e5a891db7a9b0f434a65c496cc81a54c4dfd.png)
:::
::::

::: {#b70a0ed6-e743-450d-892b-474a63bc3cc6 .cell .raw}
```{=ipynb}
Step3:
o Convert the image from RGB to HSV and display it.
    
o Convert the image from RGB to GRAY and display it. 

o Convert the image from RGB to YCrCb and display it. 
    
o Convert the HSV image back to RGB and display it.
```
:::

::: {#280fcd06-3ad1-44d7-9841-86048bbad6d6 .cell .code execution_count="108"}
``` python
# Load the image
image = cv2.imread('img3.png') 
```
:::

::: {#ca9a84bc-c091-4b81-a5b8-2560810dd2d0 .cell .code execution_count="109"}
``` python
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
:::

::::: {#9dcf8fc0-f2b6-48db-ace0-971a377e937d .cell .code execution_count="110"}
``` python
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

::: {.output .execute_result execution_count="110"}
    (np.float64(-0.5), np.float64(609.5), np.float64(472.5), np.float64(-0.5))
:::

::: {.output .display_data}
![](8b3937e27745704cc6910c987047222d37f1978b.png)
:::
:::::

::: {#afda8be8-fb4c-4e0f-8674-f869f9ad7c2b .cell .code execution_count="111"}
``` python
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
```
:::

::::: {#f62d067f-deca-4b0f-85bd-6a2ea92e3a82 .cell .code execution_count="112"}
``` python
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

::: {.output .execute_result execution_count="112"}
    (np.float64(-0.5), np.float64(609.5), np.float64(472.5), np.float64(-0.5))
:::

::: {.output .display_data}
![](585af0f0971ac25fd177f6392a223010bc7b7c39.png)
:::
:::::

::: {#58520f3c-1955-4a5c-b679-c97ed72f8117 .cell .code execution_count="113"}
``` python
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```
:::

::::: {#e89ea3a8-3bac-49fc-9338-5f7a95126bf9 .cell .code execution_count="114"}
``` python
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

::: {.output .execute_result execution_count="114"}
    (np.float64(-0.5), np.float64(609.5), np.float64(472.5), np.float64(-0.5))
:::

::: {.output .display_data}
![](677ff75f9b8d3025cd26ad82d85aa940e12f7ae5.png)
:::
:::::

::: {#3eab444b-53a6-4b75-88a4-a55d387021d4 .cell .code execution_count="115"}
``` python
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```
:::

::::: {#cfa94e70-078a-4d9c-b613-9be6361ffa4b .cell .code execution_count="116"}
``` python
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

::: {.output .execute_result execution_count="116"}
    (np.float64(-0.5), np.float64(609.5), np.float64(472.5), np.float64(-0.5))
:::

::: {.output .display_data}
![](7dd00a4a5f5e98209fb665e3b6d8aa9575dc34e6.png)
:::
:::::

::: {#1d308f1b-0795-49c0-8b77-3beb6bc11bc3 .cell .code execution_count="117"}
``` python
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
```
:::

::::: {#5cce934a-2ad2-4513-bf55-b8a3dfb2df09 .cell .code execution_count="118"}
``` python
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

::: {.output .execute_result execution_count="118"}
    (np.float64(-0.5), np.float64(609.5), np.float64(472.5), np.float64(-0.5))
:::

::: {.output .display_data}
![](8b461e88b19dd738b0284f295fe59ef2b85f7e65.png)
:::
:::::

::: {#5309faeb-f326-438f-9cb9-d5f701d76ab2 .cell .raw}
```{=ipynb}
Step4:
o Access and print the value of the pixel at coordinates (100, 100). 

o Modify the color of the pixel at (200, 200) to white.
```
:::

::: {#098ef09c-309f-4102-8ebc-e1e0e8a28b4b .cell .code execution_count="119"}
``` python
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
```
:::

::: {#8b362ddb-768a-4bb7-8ad2-ecdea5b4cc02 .cell .code execution_count="120"}
``` python
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
:::

:::: {#f36f7249-a14e-4523-879b-79cec3c7ea92 .cell .code execution_count="121"}
``` python
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

::: {.output .display_data}
![](6891fc9250f02f26cbd4f37070e9f03f47adad66.png)
:::
::::

::: {#8cceb4fb-e11e-4070-bb2d-7cef0874b032 .cell .raw}
```{=ipynb}
Step5:
o Resize the original image to half its size and display it.
```
:::

::: {#638614dc-fbed-432c-b6b2-8d14a99ee78c .cell .code execution_count="122"}
``` python
# Load the image
image = cv2.imread('img3.png') 
```
:::

:::: {#04290528-cc9e-4a78-b585-710cfdf01eb6 .cell .code execution_count="123"}
``` python
image.shape
```

::: {.output .execute_result execution_count="123"}
    (473, 610, 3)
:::
::::

::: {#fa050b6d-1877-4abc-8e15-f1152b81fe3c .cell .code execution_count="124"}
``` python
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
```
:::

::: {#f366e133-a23a-4473-94c2-d4c0a4dd9ef1 .cell .code execution_count="125"}
``` python
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
```
:::

:::: {#d3c80341-9247-4550-a414-af7e3be1100c .cell .code execution_count="126"}
``` python
resized_image_rgb.shape
```

::: {.output .execute_result execution_count="126"}
    (300, 384, 3)
:::
::::

:::: {#e049801e-c574-4814-9bd8-dafe296e7cdd .cell .code execution_count="127"}
``` python
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

::: {.output .display_data}
![](4ed6f19fb8a4dfb6cb022e6a781432c9c4d396b9.png)
:::
::::

::: {#a049d450-addb-4b91-9ffa-62125c6735c5 .cell .raw}
```{=ipynb}
Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
```
:::

::: {#0cb7482e-43c9-4b0a-9f07-00ca65d81572 .cell .code execution_count="128"}
``` python
# Load the image
image = cv2.imread('img3.png') 
```
:::

:::: {#0fa7ff1a-f6d6-489c-8b1d-47e4782119f5 .cell .code execution_count="129"}
``` python
image.shape
```

::: {.output .execute_result execution_count="129"}
    (473, 610, 3)
:::
::::

::: {#0a26103d-ccf1-43aa-ab0d-404acd65e9c3 .cell .code execution_count="130"}
``` python
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
```
:::

::: {#27ce86e9-4499-4151-ada5-5d3fee54fdbe .cell .code execution_count="131"}
``` python
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```
:::

:::: {#77d4c544-9086-4747-bd26-35529f2673d2 .cell .code execution_count="132"}
``` python
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

::: {.output .display_data}
![](0d0c6e630696f6ebf57040863ba327ac242eaa77.png)
:::
::::

::: {#d8cbcb27-b60c-4b5e-877b-2e4b58472cb2 .cell .raw}
```{=ipynb}
Step7:
o Flip the original image horizontally and display it. 

o Flip the original image vertically and display it.
```
:::

::: {#ea1e663d-dcca-414c-84f8-78ffdafd42dd .cell .code execution_count="133"}
``` python
# Load the image
image = cv2.imread('img3.png') 
```
:::

::: {#b755de7f-74be-4984-8f95-2d7631d2de6a .cell .code execution_count="134"}
``` python
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
```
:::

::: {#552ec002-b908-4888-9b3f-37a1f8a94837 .cell .code execution_count="135"}
``` python
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```
:::

::::: {#47774f0e-d6a6-4867-b9d0-a91e1c222f70 .cell .code execution_count="136"}
``` python
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

::: {.output .execute_result execution_count="136"}
    (np.float64(-0.5), np.float64(609.5), np.float64(472.5), np.float64(-0.5))
:::

::: {.output .display_data}
![](8ba6e2f5956049c8e602b2bd2c794f1f73d2e080.png)
:::
:::::

::: {#93229398-69ae-4586-ab69-5bb8ebc13bf7 .cell .code execution_count="137"}
``` python
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
```
:::

::: {#c0ce65b7-025d-464c-b9a1-72e1150477d3 .cell .code execution_count="138"}
``` python
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
:::

::::: {#5a473d78-c723-4226-915e-4e0c551227ff .cell .code execution_count="139"}
``` python
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

::: {.output .execute_result execution_count="139"}
    (np.float64(-0.5), np.float64(609.5), np.float64(472.5), np.float64(-0.5))
:::

::: {.output .display_data}
![](3ac170988612918779a50df269089195db297281.png)
:::
:::::

::: {#9ae599c9-f6ba-4a1c-b8bf-6772b6516dd1 .cell .raw}
```{=ipynb}
Step8:
o Save the final modified image to your local directory.
```
:::

::: {#9a6f4bd4-7684-4518-b14e-156cd811caab .cell .code}
``` python
```
:::

::: {#1b994250-911b-4f6f-8236-3a75db8081e2 .cell .code}
``` python
```
:::

::: {#17bc797e-10bd-451b-ad19-15e7288b581f .cell .code}
``` python
```
:::

::: {#882f6e06-bad9-4058-a15f-1efd82a2625b .cell .code}
``` python
```
:::
