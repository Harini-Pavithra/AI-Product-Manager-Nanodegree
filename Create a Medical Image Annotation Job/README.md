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

## Step 5

On the successful upload of the dataset, we will see the entire dataset in the format shown below

## Step 6

Now, with data at our disposal and the notification in the lower right corner (in green) stating that our file upload was successfully processed, we want to DESIGN our job to help the annotators, so we go to the second tab above which is DESIGN as can be seen below :



