# EmpathNet: Depression detection from clinical interviews
Explored the use of deep learning techniques for non-intrusive monitoring of depression based on video and audio data. Experimented with different models and data augmentation techniques and achieved a maximum recall of 84% and accuracy of 81%. The best performance is achieved by a VGG16 model that used both audio and text encoded using Google's BERT, resulting in a mean absolute error of 6.54.

-------------------------------------------------


To download the entire dataset  :

--->   wget -r --no-parent *link given by https://dcapswoz.ict.usc.edu/*


We have taken permission from University Of Souther California to get access to Extended DAIC Database. As we are not sure if we can freely share the link to this, we are not pasting the link here. Please reach out to us if you want to reuse the dataset. We will send a mail to the organization meanwhile if we can share the dataset.



Dataset structure:

| data|
      |
       301_P.zip 303_P.zip ..... 703_P.zip 

Need to unzip all the files

Total 265 zip files, each zip files consists of following structure

| 301_P|
       |
        --- 302_P_AUDIO.wav
	--- 302_P_Transcripts.csv
	--- Features



Now specify the path of your unzip files folder in the path of below script

Run Data_preprocessing.ipynb replacing the path 

It will generate the text_concatenated.csv and the spectrogram images from audio files with those names example : 302_spectogram.png etc

The converted spectrogram is given in data/materials folder in zip format named spectogram_images_mel_frequency.zip .

test_text_split.csv, train_text_split.csv are custom made csv from concatenating the audio transcripts to the train, test file provided in the dataset downloaded.


------------------------------------
Running the Models:-

A.
Spectoram_images_mel_fequency.zip, test_text_split.csv, train_text_split.csv need to uploaded in the google drive or colab instance to use it.

---> Run Empathnet_vgg16_bert.ipynb collab note-book 

Every time run a model not run more than one the notebook will fail, every time rerunning rerun all the cells before the model and except model before that.

https://colab.research.google.com/drive/1zgPwy5dDcTr8CSSzBQK2lD7Z3zGDN26g?usp=sharing Link to the code of colab and in the materials folder copy of this ipynb is provided with the reference taken to implement the code.


If you want to run the program on non-pro versions of Colab the notebook will collapse. So please make sure that you have minimum 25 GB of Ram and sufficient GPU.



B. In order to run the code that trained the Xception Model and The Custom CNN using Data Augmentation:

1. Have The "CV-EmpathNet folder" (link given below) consisting of the sepctogram_images.zip and spectogram_images_old.zip files in you MyDrive after mounting your gdrive to colab, or create a shortcut to this shared folder in your MyDrive.
So that the path /content/drive/MyDrive/CV-EmpathNet/spectogram_images_old.zip exists in colab, along with the folders CustomModelWeights and XceptionNetWeights to save the model weights.

2. Then run the notebook "Xception_CustomCNN_DataAugmentation.ipynb" from beginning to end.


Link to the shared "CV-EmpathNet" Google Drive Folder: https://drive.google.com/drive/folders/1ruAqoq1XAYJ1NFkm-Ea83M8lgXcJ7Ltm?usp=sharing
