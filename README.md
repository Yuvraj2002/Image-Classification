# Image-Classification

## Dataset- 
- For this project, I selected five sporstpersons to be classified- Serena Williams, Virat Kohli, Roger Federer, Maria Sharapova and Lionel Messi.
- The images for the aforementioned people was downloaded from Google using the Google Chrome extension called Fatkun Batch Downloader. This extension lets you download full pages of images of your search result, hence giving us a decent sample size to work with.

## Problem Statement- 
- The idea for the project is to build an image classifier that tells you which sportspersons picture you've entered. This will be limited to only the five people mentioned above.
- For now, we're only focusing on the Data Science aspect of the project, i.e., Dataset building, Data Cleaning and Engineering, and Model Building. The frontend will be added in later iterations.

## Methodology- 
- First off I have used Pythons OpenCV to perform a bunch of operations such as reading the image (cv2.imread) and convert it into greyscale (cv2.cvtColor).
- Then, I have used Haar Cascade to detect the face and eye outline of the said image, which will further help us during feature engineering.
- I've then made a function that returns the cropped face of an image if it detects two eyes. This is also done using Haar Cascade.
- We now iterate this function for all our images and create a new cropped folder in our directory using the 'os' library.
- Then we perform Feature Engineering on the cropped images using Wavelet Transform. A wavelet transform (WT) is based on wavelets. It is used to analyze a signal (image) into different frequency components at different resolution scales (i.e. multiresolution). This allows revealing image's spatial and frequency attributes simultaneously.
- We then stack this Wavelet Transformed image onto the raw image for better results using np.vstack. We store this in an x array and the celebrity names in the y array in this very step. This gives us our x and y variables for model building.
- Now for the model building, we use GridSearchCV to choose the best suited model for our dataset as well as hypertune the parameters we choose for that model.
- So we give GridSearchCV three different options- SVM, Random Forest and Logistic Regression.
- We find that we get the best score using Logistic Regression with the C-Value being '1'.
- We now save our model as a '.pkl' file. This file will be used to run the model in the server in later iterations. 
