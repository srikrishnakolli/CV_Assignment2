
## QUESTION 1: Template Matching

### Methodology
Template matching uses normalized cross-correlation to find the location of a template image within a larger scene image[web:40].

**Correlation Method:**
- Uses `cv2.matchTemplate()` with `cv2.TM_CCOEFF_NORMED`
- Normalized correlation coefficient ranges from 0 to 1
- Higher values indicate better matches
- Locates the template by finding maximum correlation value[web:39][web:40]

### Implementation Steps
1. Load template image from templates folder
2. Load scene image to search for the object
3. Convert both images to grayscale
4. Apply template matching using correlation
5. Find location with maximum correlation coefficient
6. Draw bounding box around detected object
7. Save output image with detection visualization

### Template Images
The following 10 objects were used as templates:
1. Object 1: [Description]
2. Object 2: [Description]
3. Object 3: [Description]
4. Object 4: [Description]
5. Object 5: [Description]
6. Object 6: [Description]
7. Object 7: [Description]
8. Object 8: [Description]
9. Object 9: [Description]
10. Object 10: [Description]

### Detection Results
**Format:** Each result shows three images side by side
- Left: Template image
- Center: Original scene image
- Right: Detected object with bounding box

#### Object 1 Detection
![Object 1 Template](templates/object_1.jpg)
![Object 1 Detection](output/detected_object_1.jpg)

**Detection Accuracy:** [Success/Partial/Failed]
**Notes:** [Any observations about detection quality]

#### Object 2 Detection
![Object 2 Template](templates/object_2.jpg)
![Object 2 Detection](output/detected_object_2.jpg)

**Detection Accuracy:** [Success/Partial/Failed]
**Notes:** [Any observations about detection quality]



## QUESTION 2: Fourier Transform Deconvolution

### Theory
Gaussian blur in spatial domain is equivalent to multiplication in frequency domain[web:44].

**Mathematical Representation:**
- Spatial Domain: L_b(x,y) = L(x,y) * G(x,y)
- Frequency Domain: F{L_b} = F{L} × F{G}
- Deconvolution: F{L} = F{L_b} / F{G}

Where:
- L: Original image
- L_b: Blurred image
- G: Gaussian kernel
- *: Convolution operation
- F{}: Fourier transform

### Implementation Process
1. Capture original image L
2. Apply Gaussian blur to create L_b
3. Compute Fourier transform of L_b
4. Apply deconvolution in frequency domain
5. Compute inverse Fourier transform to retrieve L

### Results

#### Original Image (L)
!<img width="689" height="907" alt="image" src="https://github.com/user-attachments/assets/6b8eaf26-8de2-415a-ab4e-7d7e998495e1" />

#### Blurred Image (L_b)
![Blurred Image](output/blurred_image.jpg)

#### Retrieved Image (L reconstructed)
![Retrieved Image](output/retrieved_image.jpg)


