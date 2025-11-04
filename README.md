
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
![Original Image](![L](https://github.com/user-attachments/assets/f9a3cf98-4761-43ea-b555-c6f4cedea578)
)

#### Blurred Image (L_b)
![Blurred Image](output/blurred_image.jpg)

#### Retrieved Image (L reconstructed)
![Retrieved Image](output/retrieved_image.jpg)

### Analysis
**Image Quality Metrics:**
- PSNR (Peak Signal-to-Noise Ratio): [Value] dB
- SSIM (Structural Similarity Index): [Value]
- MSE (Mean Squared Error): [Value]

**Observations:**
[Discuss the quality of reconstruction and any limitations]

## Task 3: Web Application Implementation

### Features
- Upload scene images for object detection
- Local database of 10 template objects
- Real-time template matching
- Automatic detection and bounding box visualization
- Gaussian blur applied to detected regions
- Display results with template, original, and blurred images[web:39][web:40]

### Web Interface Components
1. **Upload Section:** Upload scene images
2. **Template Gallery:** Display all 10 templates in database
3. **Detection Results:** Show matched objects with confidence scores
4. **Blur Preview:** Display images with blurred detected regions

### Detection and Blurring Process
1. User uploads scene image
2. System iterates through all 10 templates
3. Performs template matching for each template
4. If match confidence > threshold (e.g., 0.7):
   - Draw bounding box around detected region
   - Extract region of interest (ROI)
   - Apply Gaussian blur to ROI
   - Replace ROI in original image
5. Display results with detected and blurred objects

### Output Examples

#### Example 1: Multiple Object Detection
**Scene:** [Description of scene]
**Detected Objects:** Object 3, Object 7
**Processing:**
- Template matching completed in [X] ms
- 2 objects detected above threshold

**Visualization:**
![Detection Example 1](output/webapp_example_1.jpg)

*Left: Original scene | Center: Detection with bounding boxes | Right: Blurred regions*

#### Example 2: Single Object Detection
**Scene:** [Description of scene]
**Detected Objects:** Object 5
**Processing:**
- Template matching completed in [X] ms
- 1 object detected above threshold

**Visualization:**
![Detection Example 2](output/webapp_example_2.jpg)

*Left: Original scene | Center: Detection with bounding box | Right: Blurred region*

## Usage

### Running Template Matching (Task 1)
