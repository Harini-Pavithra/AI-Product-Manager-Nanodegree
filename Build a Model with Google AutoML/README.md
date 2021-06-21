# Build a Model with Google AutoML

# Overview

In this project, we need to build a labeled dataset that distinguishes between healthy and pneumonia x-ray images.This dataset would eventually be used to build a 
product that helps doctors quickly identify cases of pneumonia in children.we are going to take the next step and build the classification model that would serve as the 
backbone of this product.For this task,we will use Google AutoML,an automated machine learning tool that will allow us to build the model and host it in the cloud. 
In order to appreciate how training data impact models,we will build models with 4 variants of the dataset.The goals of this product are 
1. Help flag serious cases,
2. Quickly identify healthy cases,
3. And, generally, act as a diagnostic aid for doctors.

# The Four Parts of the Project

We will train four different models using four variants of the pneumonia dataset.The dataset contains childrens' chest x-ray images, 
and that they are classified into two classes, "normal" and "pneumonia". The following cases describe the steps we must take to create each model.

## Case 1: Create a binary classifier to detect pneumonia using chest x-rays

We'll start by training a model simply using 100 images from the “normal” class and 100 images from the “pneumonia” class.We are asked to evaluate the following:

- Train/test split: How much data is used for training and how much is used for testing?
- Confusion matrix: What do each of the cells in the confusion matrix describe?
- Precision & recall: What do these measure and how are they calculated?

## Case 2: Create an unbalanced binary classifier

Next, use 100 images from the “normal” class, and add 200 more "pneumonia" class images. At this moment, the total count of images must be:

“normal” class = 100
"pneumonia" class = 300
The model will be trained on very unbalanced classes; this will show what happens when the number of images in different classes is very different. 
 We are asked to evaluate:

- Confusion matrix: What does the confusion matrix tell you about unbalanced data?
- Precision & recall: How are precision and recall affected?
- Unbalanced classes: How do unbalanced classes impact a machine learning model?

## Case 3: Create a binary classifier with dirty data

In this iteration, start with the original dataset of 100 "normal" and 100 "pneumonia" images. Then switch the labels of 30 images in each class. 
After we've done this, 30% of the data are mislabeled. We are asked to evaluate:

- Confusion matrix: How is the confusion matrix affected?
- Precision & recall: How are precision and recall affected?
- Dirty data: How do dirty data impact the model?

## Case 4: Create a three-class model with the classes “normal”, “bacterial pneumonia”, and “viral pneumonia”

For the final model, note that the "pneumonia" images actually have two different classes: "bacterial" pneumonia and "viral" pneumonia. 
These labels are indicated in the image filenames. For this model, add 100 "normal" images, 100 "bacterial pneumonia" images, and 100 "viral pneumonia" images (for a total of 3 classes). 
We are asked to evaluate:

- Confusion matrix: What does the 3-class confusion matrix look like?
- Precision & recall: What are the model's precision and recall? How are these measures calculated?
- More data: Can we continue to add data to each class (while keeping the data balanced) and get the model to 85% precision and recall? How many data did you end up using?

# Google Cloud AutoML Vision

The following steps will guide us through the process of creating and training a model on Google Cloud's AutoML Vision platform.

## Step 1

Download Kaggle Chest X-Ray Images (Pneumonia) Dataset from the below link,                                                                             
https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia#chest_xray.zip.

![Kaggle_Dataset](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Kaggle_Dataset.JPG)

## Step 2

Go to Google AutoML: https://cloud.google.com/automl/.

![Google_Cloud](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Google_Cloud.JPG)

## Step 3

Click “TRY AUTOML” and select “AutoML Vision”.

![AutoML_Vision](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/AutoML_Vision.JPG)

## Step 4

Sign in to Google Developer or create an account.

![Cloud_Account](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Cloud_Account.JPG)

## Step 5 

After logging in, head to the AutoML Vision Console: https://console.cloud.google.com/vision and Accept the terms of service.

![Terms_Conditions](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Terms_Conditions.JPG)

## Step 6

Next create a project with any title.

![create-project](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/create-project.png)


## Step 7

Once on the dashboard click “Get Started” on AutoML Image Classification.

![Image_Classification](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Image_Classification.JPG)

## Step 8 

Accept all the screens then we will reach the last page where we have to set up billing and Vision API.

![Billing](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Billing.png)

## Step 9 

When we go to billing we should see an option to activate free $300 credit at the top of the screen. Click “ACTIVATE”.

![Activation](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Activation.png)
 
## Step 10

We now provide our Email ID and click on next.Once the phone number is verified, we will be redirecting to the last page for activating the credit. Then select “Individual” account type and input all necessary info including card. Google does not charge this card unless you manually upgrade to a paid account.
https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Individual_Account.png)

![Adding_Card_1](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Adding_Card_1.JPG)

![Adding_Card_2](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Adding_Card_2.JPG)

![Individual_Account](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Individual_Account.png)


## Step 11

Once we have completed the billing we can go back to the project set up page and click “SET UP NOW” to enable the vision API. This will automatically set up the API 
and should redirect us to select the Google Cloud Project.In the dropdown we should see the project that we created. Select the project and continue.

![Enable_API](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Enable_API.JPG)

## Step 12

Next,we should see the Datasets page. Click “Create” at the top of the page.

![Create_Dataset](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Create_Dataset.JPG)

## Step 13

Select “Single-Label Classification”.

![Single_Label_Classification](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Single_Label_Classification.png)

## Step 14

Create your dataset.Create your dataset.
1. Give the dataset a name and create bucket by clicking on "Browse" under Upload data option.

![Dataset_details](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Dataset_details.JPG)

![Bucket_Creation](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Bucket_Creation.JPG)

![Dataset_List](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Dataset_List.jpg)

2. Open the folder of Chest Xrays we downloaded from Kaggle and go into the train folder.
3. In a separate folder create a directory with the following structure:
   - (Main folder) Case 1/
     - normal/
     - pneumonia/
4. Then copy between 100-300 images of each type of each classification from the original train/ folder (normal, pneumonia) into the appropriate new folder. 
The exact number of images in each folder will depend on which of the four parts of the project you are solving,Once you have your images in the new folders 
then zip the whole Case 1/ folder to create Case 1.zip.

![Folders](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Folders.JPG)

![All_Files](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/All_Files.JPG)

## Step 15

Now back in the AutoML Console Dataset go ahead and upload the zip file with all the images. Again, make sure we zipped the top-level folder 
that contains two folders: normal/ and pneumonia/ with the associated sets of 100-300 images in each folder (the exact number of images will depend on which of the four parts of the project we are solving). 
This will allow AutoML to automatically detect the correct ground truth label for each image by looking at the name of the folder in which it is contained. 
Once the zip file is attached go ahead and “CREATE DATASET”. For our current labeling scheme, there is no need to select the button to "Enable multi-label classification" (this allows you to apply multiple labels to a single image). 
This step make take a few minutes to upload all the images and set up the dataset.

![Import_Dataset](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Screenshots/Import_Dataset.jpg)

## Step 16

Once the data is ready we should see a screen with all the images we added as well as a label of “normal” or “pneumonia” under each image. 
These are the images and ground truth labels that will be used to train/test/validate your pneumonia detector model.

![Dataset](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Case%201_Screenshots/Dataset.JPG)

## Step 17

Next click on the “TRAIN” tab and here we will see the distribution of images as well as the splits for training, validation, and test images.

![Train](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Case%201_Screenshots/Train.JPG)

## Step 18

Click “START TRAINING” to begin training your pneumonia classification model. In the options keep all the defaults (Cloud-hosted, 8 node hour) and then start the training.

![Training](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Case%201_Screenshots/Training.JPG)

## Step 19

Now the model is in the training phase.This will take some time. Once the model training is done we will be notified via email and we can see the below results.

![Model_Result](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Case%201_Screenshots/Model_Result.JPG)

![Model_Result_1](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Case%201_Screenshots/Model_Result_1.JPG)

## Step 20

Once the training is complete we can click on the “EVALUATE” tab and we will see various metrics about the model such as precision, recall, and a confusion matrix.
Try to understand what each of these metrics means and how they are calculated.

![Evaluation](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Case%201_Screenshots/Evaluation.JPG)

![Confusion_Matrix](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Case%201_Screenshots/Confusion_Matrix.JPG)

## Step 21

Optional: Next click on the “TEST&USE” tab and this is where we can test the model on new data that the model has never seen. If we click “UPLOAD IMAGES” and 
select an image from the Kaggle dataset that we did NOT use in the training set of images and watch the model predict whether or not the patient in the x-ray has pneumonia or 
not.Try to find images that produce both correct and wrong predictions.

![Deploy](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Deploy/Deploy.jpg)

![Deploy_1](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Deploy/Deploy_1.png)

## Step 22

That's it! we've built our first AI model! Now that we know how to upload data and train the model, follow the steps above for 3 additional variations on the dataset, 
for a total of 4 models.Recommend creating new folders, new zip files, and new datasets in AutoML so that we can keep track of which iteration we're on and retain the results of each trained model for reference:
   1. Clean/Unbalanced: Create a model using 100 "normal" images and 300 "pneumonia" images.
   2. Dirty/Balanced: Create a model with 100 "normal" images and 100 "pneumonia" images, but deliberately create a "dirty" dataset by putting 30 "normal" images in the 
      pneumonia folder and 30 "pneumonia" images in the normal folder.
   3. 3-Class: Note that the filenames of images in the "pneumonia" class have 2 standards; for example: person75_bacteria_366.jpeg and person80_virus_150.jpeg. 
      The inclusion of the word "bacteria" indicates that this was a case of bacterial pneumonia, and the word "virus" means this was a case of viral pneumonia. 
      Go back and create a dataset with 3 classes: "normal", "bacterial pneumonia" and "viral pneumonia".
      
Once you have completed the project, don't forget to disable the Google Cloud Platform billing for this project. 

The various screenshots for Case 2(Unbalanced data),Case 3(Dirty data),Case 4(3-Class data) are available in

[Case 2 Screenshots](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/tree/main/Build%20a%20Model%20with%20Google%20AutoML/Case%202_Screenshots)

[Case 3 Screenshots](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/tree/main/Build%20a%20Model%20with%20Google%20AutoML/Case%203_Screenshots)

[Case 4_Screenshots](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/tree/main/Build%20a%20Model%20with%20Google%20AutoML/Case%204_Screenshots)

and a detailed AutoML Modeling report can be found in [automl modeling report.pdf](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/automl-modeling-report.pdf)

# Review from Udacity Mentor

![Review](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Build%20a%20Model%20with%20Google%20AutoML/Review/Review.JPG)
