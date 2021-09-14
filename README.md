# Pneumonia-Detection-using-VGG16

#### Goal: The goal of this project is to detect whether a person is suffering from Pneumonia or not.

#### About the Data set:
The Dataset is was downloaded from [Kaggle](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia). The size of the Dataset is 1 GB. 
The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). There are 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal).

Chest X-ray images (anterior-posterior) were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center, Guangzhou. All chest X-ray imaging was performed as part of patients’ routine clinical care.

For the analysis of chest x-ray images, all chest radiographs were initially screened for quality control by removing all low quality or unreadable scans. The diagnosis for the images were then graded by two expert physicians before being cleared for training the AI system. In order to account for any grading errors, the evaluation set was also checked by a third expert.

#### About the project:
In this project I have implemented a Transfer Learning model, VGG16. I have used Google Colab for the entire project implementation. Train, test and validation datasets were kept at a convinient loction in the Google Drive. The initial step was to resize all the images of the training file to [224,224]. Training path and validation(test) path were set. The VGG16 model was called inputting the VGG16 library and keeping the initial and final layer false as I dont want to classify 1000 categories. I have only two categories that is Pneumonia and Normal. I have dropped the first layer too so that I can give my own image size. The [+3] is the RGB dimension that needes to be added. Here I have used imagenet weights. I have not trained the existing weights as the captured weights would changed. Existing layers were flattened, the final layer was made and the model was compiled using loss as "categorical_crossentropy", optimizer as "adam", and metrics as "accuracy". Image Data Generator was used for passing the train and test images and making some amount of added changes like zooming , flipping , etc.

![Screenshot (164)](https://user-images.githubusercontent.com/75041273/133292764-f680e34a-1121-4e7c-a5b8-b5d5d9a2617d.png)

Then the model was fitted with five epochs, the length of the steps per epoch was set equal to the length of the train dataset and the length of the validation steps was set equal to the length of the test dataset. The VGG16 model has lot of layers and the dataset was also huge so it took me around 2hours 40minutes to run five epochs without GPU. I tried setting the runtime type as GPU enabled but after one epoch the runtime got disconnected. If you have colab pro or a GPU then it might take somewhere around 30minutes to train the VGG16 model. 

The model performed really well(as expected) with training accuracy of 97% and test accuracy of 90%. Better results could have achieved if the number of epochs were increased. After model training, loss and accuracy were plotted. 
![Screenshot (163)](https://user-images.githubusercontent.com/75041273/133292014-5a5b4924-8136-409d-be0e-9caf8296ff40.png)

Finally, the model was tested with the validatiion data and the the detections were accurate.



Model link: https://drive.google.com/file/d/1-9MhGzag-4xIEB7cYdl7Q1l6SYfbyqoD/view?usp=sharing
