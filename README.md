# Swin Transformers for Diabetic Retinopathy Grading

## About
Author: Selen Erkan \
erkan.selen@campus.lmu.de \
This project was implemented for the seminar "Unsupervised Deep Learning"  at LMU.
## Description of the task
+ This notebook is an implementation of Swin Transformers on Diabetic Retinopathy Grading.
+ Output of this task is uploaded to the DRAC challenge.
+ Diabetic Retinopathy Grading is a disease that can cause blindness in people with diabetes.
+ The dataset consist of black and white retina images with three labels as Normal (0), NPDR (1), and PDR (2).

## Description of the code structure
+ The notebook consist of four main parts: dataloaders, setting the model, training the model and testing.
+ In the dataloader part, a custome dataloader is prepared for the dataset.
+ In the model part, a pretrained swin transformer model is loaded from huggingface library. 
+ Two different training procedures are implemented to train this model.
+ First approach is to use the pretrained model weights as weight initialization for the model. During training gradients flow through all the layers and the weights are tuned (updated) for the task.
+ Second approach is to use pretrained weights as final weights of the model and flow the gradients only through the classification head. So, the model will only update the weights in the classification layer and other weights will stay the same.
+ For both approaches the model that is giving the best training loss is saved to be used for the test set.
+ The cells under the part Submission is created to generate an output file for the DRAC challenge. This part also contains testing of the model. 
+ This part can be updated depending on the dataset and task.

## How to run the code
+ The code is in .ipynb format and it can be run in Google Colab with GPU runtime. 
+ All the cells need to be run one after another. 
+ The notebook connects to the google drive to find the dataset in the specified location.
+ For the training part one must pick one training procedure and run only the cells under it. 
+ Do not run the training for both models one after the other.
+ If both training procedures are needed to be experimented, one needs to initilaize the model again before running the second training procedure. 
+ One can initialize the model by running the cells unders the part MODEL.
