# Rotation CAPTCHA Solver: Circular Patch Alignment Network

## About
<div style="display: flex; width: 100%;">
  <img width="900" height="auto" alt="image" src="https://github.com/user-attachments/assets/d6471aa2-8351-4254-ae81-eb79ca4285e3" style="max-height: 500px; width: auto;" />
</div>
&nbsp;
The repository contains a convolutional neural network based on **ResNet-18** that solves **rotation-based CAPTCHA** challenges. In these CAPTCHAs, a circular region is cut from the center of an image and rotated by an unknown angle. The task is to predict the rotation angle required to realign the circular patch with its original position.
&nbsp;
The network takes as input:
- An image with a circular hole at the center  
- The corresponding rotated circular patch
&nbsp;
It predicts the correct rotation angle, allowing for the automatic reconstruction of the correctly aligned image.

## Dataset
The project utilizes a set of **2000 real images** from Kaggle’s open **Cats vs Dogs** [dataset](https://www.kaggle.com/datasets/abhinavnayak/catsvdogs-transformed).  
All images are sized at **224×224 pixels**, with the radius of the patch set to **40 pixels**. The angle changes from **0 to 360 degrees**. The target variable is represented as the sine and cosine of the angle to avoid discontinuity when transitioning from **360 to 0 degrees**.

## Project Structure

- **cat-captcha-weight.pth**: [Pre-trained weights](https://mega.nz/file/qiRCnJ5Y#gkHD9FwlT8Hhnduzxc-HvnCBMUT5YEHRNXer7EwxQSA) for the ResNet18 model.
- **cat-captcha.ipynb**: Jupyter Notebook with a step-by-step solution for the regression task.

## Results
After training for **60 epochs**, the network demonstrates stable results, with a **Mean Absolute Error (MAE)** on the test subset of approximately **10 degrees**.
