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
