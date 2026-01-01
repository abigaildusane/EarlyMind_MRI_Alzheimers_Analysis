# Steps:
1. Start with a brain MRI image
Each MRI image is made of pixels, and each pixel has a brightness value:

- Dark pixels usually represent fluid or low-density tissue
- Bright pixels represent denser brain tissue

2. Remove everything that is not the brain
The background outside the head is completely black.
Ignore these pixels so only the actual brain region is analyzed.

3. Measure brain size in pixels
After removing the background:
- Count all pixels that belong to the brain
- This gives the total brain area (in pixels) for that image

4. Identify cerebrospinal fluid (CSF) pixels
In MRI images:
- CSF appears darker than brain tissue
- Classify pixels inside the brain that are below a brightness threshold as CSF

5. Count CSF pixels
Count how many brain pixels are classified as CSF.

6. Calculate the CSF ratio
CSF Ratio=CSF pixels/Total brain pixels
This value represents the fraction of the brain area occupied by CSF.

7. Use the CSF ratio to estimate brain shrinkage
When Alzheimer’s develops, the brain shrinks and fluid spaces grow.
A higher CSF ratio suggests more brain shrinkage and higher risk.

8. Repeat across all images and compare labels
Compute the CSF ratio for all MRI images and analyze how it varies across:
- Healthy individuals
- Early-stage Alzheimer’s
- More advanced Alzheimer’s cases
This allows to study early structural changes associated with Alzheimer’s disease.


# How to Run the Program
Requirements:
- Python installed and the following libraries available
- pip install numpy pandas matplotlib pillow pyarrow
- Google Colab, these libraries are already installed.

Dataset:
- This project uses MRI images stored in a Parquet file.
- Each row contains: image: MRI image bytes, label: Alzheimer’s stage, 0 = Healthy, 1 = Very Mild, 2 = Mild, 3 = Moderate
- Dataset path in the code if needed: TRAIN_PATH = "path/to/train.parquet"

# Identify CSF pixels
- Pixels darker than a chosen intensity threshold (default: 70) inside the brain are treated as CSF.
- Column name used in results: CSF_threshold_pixel_darker_than_intensity

# Compute measurements
- Brain pixel count
- CSF pixel count
- CSF ratio = csf_pixels / brain_pixels
- Assign risk level (only trial indicators)
- CSF Ratio	Risk Level: ≥ 0.20	High, ≥ 0.16	Medium, < 0.10	Likely Healthy

# A results table
- One row per MRI image
- Includes index, label, pixel counts, CSF ratio, risk, and threshold

# Visualize results
- Scatter plot: CSF Ratio vs Alzheimer’s Label
- Shows how CSF ratio varies across disease stages

# Display example MRI images
Shows sample images with:
Brain pixels
CSF pixels
CSF ratio
Risk category

# Running the Code
- Run program  in Google Colab / Jupyter Notebook.

# You will see:
- A table preview of results
- Risk distribution
- A CSF ratio vs label plot
- Example MRI images with calculated values
