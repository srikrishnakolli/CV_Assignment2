
## QUESTION 1: Template Matching

### Methodology
Template matching uses normalized cross-correlation to find the location of a template image within a larger scene image.

**Correlation Method:**
- Uses `cv2.matchTemplate()` with `cv2.TM_CCOEFF_NORMED`
- Normalized correlation coefficient ranges from 0 to 1
- Higher values indicate better matches
- Locates the template by finding maximum correlation value

### Implementation Steps
1. Load template image from templates folder
2. Load scene image to search for the object
3. Convert both images to grayscale
4. Apply template matching using correlation
5. Find location with maximum correlation coefficient
6. Draw bounding box around detected object
7. Save output image with detection visualization





#### Actual Object

<img width="1233" height="920" alt="image" src="https://github.com/user-attachments/assets/77e918b1-40e6-463e-9624-c1657c5fdd88" />


### Template Images
The following 10 objects were used as templates:
1. Object 1: <img width="608" height="221" alt="Bot" src="https://github.com/user-attachments/assets/ad94d710-0b30-4136-8d63-2fbcaf4c0a50" />
2. Object 2: <img width="182" height="304" alt="Car" src="https://github.com/user-attachments/assets/44f24e26-6d7b-4b0d-8c0d-8fe6188b70ee" />
3. Object 3: <img width="540" height="298" alt="Ketch" src="https://github.com/user-attachments/assets/840ca005-3968-4ec9-9f98-b6700eee57f7" />
4. Object 4: <img width="218" height="199" alt="Wat" src="https://github.com/user-attachments/assets/048ae299-d0bd-4929-94e8-cb722bbc874f" />




### Detection Results
<img width="1197" height="925" alt="image" src="https://github.com/user-attachments/assets/10753879-61bd-4759-bf8f-6d96a19a2082" />



## QUESTION 2: Fourier Transform Deconvolution

### Theory
Gaussian blur in spatial domain is equivalent to multiplication in frequency domain.

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
<img width="661" height="886" alt="image" src="https://github.com/user-attachments/assets/d969d90c-f63d-4bfa-9675-4b8c02b03e15" />


#### Retrieved Image (L reconstructed)
<img width="656" height="885" alt="image" src="https://github.com/user-attachments/assets/c8113a54-8909-44a4-8b31-1e388a979281" />




## Question 3: Web Application Implementation



### Output
<img width="1569" height="904" alt="image" src="https://github.com/user-attachments/assets/2757e01b-8926-4db9-897d-c02400492545" />



