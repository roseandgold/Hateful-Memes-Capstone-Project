# HatefulMemesProject

Artificial Intelligence plays a crucial role in mitigating problematic or abusive behavior, such as pornographic material, misinformation, and hate speech on social media platforms. While machines may be good at classifying content that is just images or just text, memes pose a unique challenge because it is often the combination of image and text which make a meme hate speech or not. Training a machine to recognize this as hate speech is not as easy as it sounds. While humans can easily integrate the text and image information holistically, machines struggle with this sort of task. Currently it is impossible for humans to inspect all the content posted on social media sites so being able to create a machine learning model which can accurately categorize memes as hate speech is becoming ever more important. With that in mind, the goal of our project was to develop a machine learning system that could determine whether a meme was hateful or not. We created three different models, 2 unimodal models based on just the image or text and one multimodal model that combined the meme image and text. 

In order to achieve our goal we used the Hateful Memes Challenge dataset which was created by Facebook AI. This dataset includes a training set of 8,500 memes as well as a validation dataset and a hold out test dataset. All three datasets include the images as well as a JSON file with the meme text and label. The full dataset is available to download here: https://hatefulmemeschallenge.com

## What is included in this repo?
### Data Preprocessing and EDA Folder
  * Preprocess_Meme_Image_and_Text_Data.ipynb - preprocesses 120 random samples from the training data for TSNE visualization. Sixty of the memes are classified as hate speech and the other sixty are classified as non-hate speech. Creates a BERT embedding for the text from each meme and a ResNet for the image of each meme and combines the two embeddings into one multimodal data representation. Saves all the embeddings to a pickle file.
  * Exploratory Data Analysis.ipynb - includes visual exploration of the training dataset. training_combo.p and training_labels_combo.p can be created using the Preprocess_Meme_Image_and_Text_Data.ipynb file or downloaded here: https://drive.google.com/drive/folders/1gUuicGA6Gnzh1hYdAsE9powrQYuCTvyp?usp=sharing


### CNN Model
The first thing we tried was to create a classifier simply based on the image data. In order to do this we trained a Convolutional Neural Network since this form of model can capture the spatial information in images. 
<img src=https://github.com/roseandgold/HatefulMemesProject/blob/main/CNN%20Model/Capstone%20CNN%20Model%20Diagram3.png>

To test out this model yourself you need the below files as well as the Hateful Memes Challenge Datasets
 * Preprocess the Images for CNN.ipynb - preprocesses the meme images so they are all 200x200x3. Outputs the data as numpy arrays to a pickle file. 
 * CNN Image Model.ipynb - train and test the CNN model. Requires the preprocessed images which can either be obatined by running the Preprocess the Images for CNN.ipynb notebook or downloaded here: https://drive.google.com/drive/folders/1l5QVobAOw52l5ApcVYYceOhT9TzFwVx5?usp=sharing 
 * model_0.533.h5 - This was the best model we obtained. This can be used in the CNN Image Model.ipynb to get the AUROC score and create the ROC curve
