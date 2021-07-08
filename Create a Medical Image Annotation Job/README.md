# Create a Medical Image Annotation Job

# Introduction

Our goal, as a product owner is to build a product that helps doctors quickly identify cases of pneumonia in children. You'll want to build a classification system that
1. Can help flag serious cases
2. Quickly identify healthy cases
3. And, generally, act as a diagnostic aid for doctors As such, this project is designed to test our ability to build a labeled dataset that distinguishes between healthy and pneumonia x-ray images.This can be used by ML engineers later on down the line to build a classification product.Our main task will be to create a data labeling job using [Appen's platform](https://client.appen.com/jobs). If we have not yet, we need to create an Appen account and login to complete this project.

If we intend to purchase any services through Appen, we need want to use a valid business email.so, we can receive notifications. But for the project, if we do not have a business email, we can use the above workaround in the meantime.

we will not be required to actually launch the data labeling job, we be evaluated on submitted documents and design only by Udacity mentor team.

# The Data

The dataset we'll be given is a modified version of this [Kaggle chest x-ray dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), with most labels removed. Every piece of data is a chest x-ray image. We may see images taken that are slightly different in size and taken under slightly different exposure times. A typical, labeled image is shown below.

![Annotated_Chest_Xray](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Annotated_Chest_Xray.png)
<p align="center"> A labeled, healthy, chest x-ray image. Pay close attention to the two lungs and diaphragm (below the lungs) </p>

# What Does Pneumonia Look Like?

This is a challenging task because it is not always clear when pneumonia symptoms are present or not in an image. As such, your system is not meant to be a replacement for a doctor, only to aid in quickly identifying healthy patients and surfacing potential cases of pneumonia.

we should design a data annotation job, such that a non-expert can identify more noticeable cases of pneumonia. Since we are designing for a non-expert annotator, you should design for failure; this means including some way to capture uncertainty in your data labels and test questions.

So, what indicates pneumonia and what kind of advice and examples can we give potential annotators?

There are a few different visual symptoms that indicate pneumonia. The most important areas to have annotators pay attention to are the lungs and the diaphragm.
1. A normal, healthy image will depict clear lungs without any areas of abnormal cloudiness/opacity; there may be structured, web-like vasculature in the lungs but otherwise that area should be clear. In healthy images, you are also more likely to see a diaphragm shadow.
2. A pneumonia image may include a few things: areas of cloudiness/opacity in several concentrated areas or one large area. You may also see a general pattern of opacity that obscures the structure of the lungs, heart and diaphragm.

![Healthy_Example](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Healthy_Example.png)
         <p align="center"> some characteristics of a healthy image: a clear lung area </p>
 
![Pneumonia_Examples](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Pneumonia_Examples.png)
            <p align="center"> Examples of pneumonia symptoms: (Left) a concentrated, opaque area in the lungs, (Right) multiple, smaller opaque areas throughout the lung       area and any diaphragm shadow is obscured. </p>

Note: we may download the above images for use in our annotator Instructions, if we want to.

# Designing a Data Labeling Job

One of our biggest tasks will be to design an appropriate data labeling job using Appen's platform. We need to submit an HTML file of a complete job Preview, which includes: 
1. Instructions for annotation and
2. Example test questions. 

We also need to submit a Proposal document that discusses the design of the job and steps we'll take for quality assurance.

We don't need to launch the annotation job; we are only creating one to demonstrate our ability to create a dataset.

# Good Annotator Instructions (Handling Uncertainty)

This is a very challenging classification task and so we should provide clear examples and instructions to potential annotators.

1. We may choose to have annotators try to label an image as pneumonia or not (binary classification); if this is the case, we should include an Unknown or Other option to account for uncertainty in an annotation.
2. We may also choose to have annotators describe how likely they think a case of pneumonia is in a given image, and we could measure this on a numerical scale; 0-n for their confidence that an image contains pneumonia symptoms or not. A scale like this automatically includes room for low-confidence and uncertainty.
3. In our Proposal document, we will discuss our design choices and methods for quality assurance.

It is suggested that we start with an Appen job-template, and customize it to this particular task. And we can read more about the platform, next.

# Create a Medical Image Annotation Job with Appen 

## Step 1

Login to Appen using our credentials. We will see the landing page as depicted below. On the basis of the kind of job that you want to create, select one of the following options :

![Appen_Platform](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Appen_Platform.JPG)

## Step 2

we want to create a job for Image Annotation, where the annotators will check the presence of Pneumonia signs in a set of images given to them.

![Image_Annotations](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Image_Annotations.png)

## Step 3:

Under the Image Annotation category, we need to select the template that we think will be best suited for creating the annotation job. Using the Preview section while screening for templates will give us a fair idea of how useful a template is for our given job. Here, we want to identify whether any given image contains a Pneumnia signs or not, so we use the image categorization template under the image annotation category

![Image_Categorization](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Image_Categorization.png)

![Preview](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Preview.JPG)


## Step 4

On selecting Use this template under the Image Categorization category, we are prompted to upload our dataset as seen in the step below, here we can click on the browse button and upload the required dataset

![Dataset](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Dataset.jpg)

## Step 5

On the successful upload of the dataset, we will see the entire dataset in the format shown below

![Datasets_Appen](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Datasets_Appen.JPG)

## Step 6

Now, with data at our disposal and the notification in the lower right corner (in green) stating that our file upload was successfully processed, we want to DESIGN our job to help the annotators, so we go to the second tab above which is DESIGN as can be seen below :

![Successfully_Uploaded](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Successfully_Uploaded.jpg)

![Design](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Design.jpg)

## Step 7

In this important step, we want to map our data to the existing template. Many students skip this step, but this is a crucial step to align the template with our data

![MappingJPG](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/MappingJPG.JPG)

In this mapping, we match (just drag and drop) appropriate columns from Your Data (on L.H.S) to the Template column (on R.H.S) and click on Save Mapping.

![Mapping_Done](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Mapping_Done.JPG)

## STEP 8

The next step is to edit the Title, CML code and Instructions according to the job we have in hand. Since we want our annotators to identify whether an image contains a Pneumonia signs or not, we edit all the three accordingly, as can be seen in the image below

![Title%26CML](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Title%26CML.JPG)

We can see that we have edited the Title to suit our job. The next critical step is to edit the CML code for the same. We are simply asking the annotators a question, whether they think that there is a Pneumonia sign in the given image or not, so we have two options Yes and No (which were already present in the template). To account for uncertainty because of the lack of clarity in pictures, we add one more checkbox to the existing Yes and No, a Unknown button for
when the annotators are unable to figure out if a parking sign actually exists and we simply edit out the rest of the code. This is how the above CML code edit renders as a UI element:

![CML_Result](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/CML_Result.JPG)

This step might be baffling at first, but on thorough observation, we will figure out how we can customise this CML code to suit your job. If it’s still not clear, we can always get additional help from the help document on CML reference which is displayed to the right side of this editor (as can be seen below) :

![CML_Reference](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/CML_Reference.png)

Clicking on any one of the items in this list will explain the what, how, when and whys of the CML code elements being used in the editor. Please note that we simply need to edit the basic CML code to suit our job, we do not need to delve too deep into the CML coding.

## Step 9

Next, we need to edit the Overview, Steps and Rules/Tips suited to our job. Remember that in this example, we are asking annotators to find whether an image contains a Pneumonia sign or not, so we need to edit the instructions accordingly as seen below 

![Instructions](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Instructions.JPG)

## Step 10

We don’t need to bother about the images displayed under this section that are a part of the existing template, they can be edited out once we have our Test Questions designed. We can ignore them for now and come back to this step later. Simply click on the Save button.Please note that we can Preview the sections we have modified here, by clicking on the ‘eye’ button seen in the top right corner.

![Preview_Icon](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Preview_Icon.jpg)

Also note that we can only see the modified changes in Preview if we have edited and saved our changes using the Save button that is to the left of the Preview button.

## Step 11

The next step is to Create Test Questions, so click on the Create Test Questions button that can be found right under the Preview button.

![Test_Questions](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Test_Questions.png)

## Step 12

After we click on the Create Test Questions button in Step 11, we see this page 

![Quality](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Quality.JPG)

## Step 13

Now we will start seeing images from the dataset that we just uploaded and we will need to answer 8 questions (they are displayed to us similarly to how annotators who we have created the job for would see them), which will act as a guide to test the annotator’s competency when we are onboarding them. Below is an example of the above mentioned view of the test 

![Test_Question_1](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Test_Question_1.JPG)

![Test_Question_2](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Test_Question_2.JPG)

The idea here is to have the entire range of reference test images divided equally among the number of options we are providing. Since we are required to have 8 test images, we will find and answer such images so that the tally for each possible option that we have designed (Yes or No or Unknown) here is equal. This is to make sure that our job isn’t biased towards accepting and validating one specific option from the annotators. We can click the Skip Question button if we feel that the responses are getting biased towards one specific option. We can keep answering and checking the View Answer Distribution button (on top right) to keep a tally of whether every option is being given a fair weightage in our designed test. Remember that for each test question answered, we need to give a reason for why we chose that option in case test takers falter so they have a clear understanding of why they faltered and which images they annotated incorrectly. After checking the correct option and listing the reason, we click on Save
and Create Another.

### NOTE: 
As we go about answering these questions, remember to take a few (2 or 3 max) screenshots of the images displayed (one for each option would be ideal) and the options
provided below them so we can use them as a preview in Step 10

![Test_Question_3](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Test_Question_3.JPG)

## Step 14

Once we have successfully answered the 8 test questions, we will see this message to the right

![Test_Questions_4](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Test_Questions_4.png)

we can click on View Answer Distribution to check whether each option has been given a fair chance. The following is the distribution of our test questions

![Distribution](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Distribution.JPG)

We see here that the questions are fairly equally distributed among the three options, if we want to continue to refine the weightages, we can answer a few more questions and check the answer distribution again.

## Step 15

In the last step, we go back to the DESIGN tab (the second tab) on top, to eliminate the pictures from the templates and insert the pictures that we just took while answering the test question in Step 13, as can be seen below :

![Design_Alignment](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Design_Alignment.JPG)

Here, we have the option to eliminate both the existing images and add and align the newer images from our dataset to be displayed as a preview Once we have those images, 
we can save the preview page as .html and CHEERS! We have the file that we need to submit along with the proposal. 

The detailed report can be found in [project proposal document](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Data_Annotation_Project_Files/project-proposal.docx)

# Review from Udacity Mentor

![Review](https://github.com/Harini-Pavithra/AI-Product-Manager-Nanodegree/blob/main/Create%20a%20Medical%20Image%20Annotation%20Job/Screenshots/Review.JPG)
