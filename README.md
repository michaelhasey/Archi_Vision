# Archi_Vision
Learning more about where we live


# About 

Archi-Vision is an AI tool that helps us learn more about urban housing and its relationship to the city.  Traditionally, housing data has been collected manually and contains few descriptors beyond house price, sqft, # of bathrooms,and so on.  As a result, housing remains largely undescribed and our understanding of its relationship to the city incomplete. Archi-Vision attempts to solve this by using Deep learning methods (object detection & classification) to rapidly extract far more detailed image-based housing data over larger areas than previously possible.

As proof of concept, I used Pittsburgh as a test area and trained my models on 750 hand-collected and labelled Google Street view images of working-class housing.  A a goal my project attempts to autonomously detect, analyze and record both standard visual housing data as well as new and novel info such as early signs of gentrification including the presence of abandoned buildings and the quality of sidewalks. Various concepts from class such as “Interpretability” and “Bias and Anonymity” were integrated.  In particular, the proposed GUI provides further ai transparency through white-box methods such as prediction and data visualizations and simple explanations, required human input to correct model prediction mistakes or uncertainties therefore building trust in the model, both baseline and expert model adjustment capabilities, therefore staisfying the needs of users with varying ai or cs knowledge, and easy to understand prompts and suggestions regarding determining the appropriate model and settings to satisfy particular goals.


# Models

Summary:  4 different models were used in this experiment. 

Model 1: Vacancy_Image_Classification_Training_Model.ipynb
        - A single label classification model used to train a convolutional neural network algorithm to detect 
          whether a house appears to be occupied or abandonded.
        - The model is built upon the fastai framework and pytorch (pyimage) computer vision library
        - This code was learned and adapted from various tutorials for and methods suggested by Fastai, an
        online platfor that makes building, using and manipulating deep learning algorithms easier and
        more accessible to cs and deep learning beginners.
        - https://docs.fast.ai/tutorial.vision.html#Single-label-classification
        
        Code modification and additions
        
        - Though this tutorial was followed, various significant modifications and additions to thecode           
          were neccessary to achieve the goals of this project. they include: 
        - setting up general framework of model and file structure
        - modification of image transormation variables prior to training
        - modification of batch size and image scale dependent on need and available computing power
        - modification of learner rates after a series of experimentation with various learning rates
        - learner rate of between le-4 and le-2 were found to be most suitable to achieve highest accuracy and lowest loss function
        - model results and confusion rates helped to provide further guidance to finely tune image transformations, batch sizes and learning rate
          to achieve best results.
          
          
Model 2: Vacancy_Image_Classification_Prediction_Model.ipynb
        - A single label classification model that uses the weights obtained in training model (model 1) to detect 
          whether a house appears to be occupied or abandonded.
        - The model also labels and sorts images into folders with corresponding names.
        - The model is built upon the fastai framework and pytorch (pyimage) computer vision library
        - This code was learned and adapted from various tutorials for and methods suggested by Fastai, an
        online platfor that makes building, using and manipulating deep learning algorithms easier and
        more accessible to cs and deep learning beginners.
        - https://docs.fast.ai/tutorial.vision.html#Single-label-classification
        
        Code modification and additions
        
        - Though this tutorial was followed, various significant modifications and additions to thecode           
          were neccessary to achieve the goals of this project. they include: 
        - setting up general framework of model and file structure
        - loading and using custom trained weights from previous training model (model 1)
        - custom labelling and sorting tool that provides corresponding labels depending on predicted class
