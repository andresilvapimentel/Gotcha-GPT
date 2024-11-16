# Gotcha-GPT
<img src="gotcha.gif" alt="drawing" width="200"/>

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.13769907.svg)](https://doi.org/10.5281/zenodo.13769907)

Gotcha GPT ensures the integrity of academic writing in universities and publishing houses due to advances in Artificial Intelligence (AI). It discriminates AI- and human-generated manuscripts (English and Portuguese).

Gotcha GPT is a code to dicriminate AI- and human-generated english manuscripts by using classifier models (Decision trees, Extra Trees, Random Forest, and AdaBoost).

The Gotcha GPT framework is highly versatile (coded in Google Colab). It uses Scikit learn libraries to provide the statisctics (precision, accuracy, recall, F1, MCC, and Cohen´ Kappa scores) and the confusion matrix to guarantee confidence to the user. There is a text dataset of about 400 AI-generated texts and around 400 human-generated texts used for training and testing (50/50 random split).

<img src="gotcha GPT.jpg" alt="drawing" width="400"/>

# Installation instructions

Gotcha GPT is 100% compatible with Google Colab platform developed in Microsoft Windows using Python version 3.10. It is important to note that running the notebook with Google colab does not violate the confidentiality and proprietary rights of the author. Also, if the manuscript contains personally identifiable information, this task does not breach the data privacy rights.
The user may also run the notebook with minor changes on Jupiter Lab or any other platform.

# Tutorial

A) The easiest way to run Gotcha_GPT (without training) is using the notebook Gotcha_GPT_new.ipynb and uploading the text_classification_eng.xlsx file (for detecting English manuscripts) or text_classification_port.xlsx (for detecting Portuguese manuscripts). On the Runtime tab in the Google Cola platform, just run all cells and scroll down. The notebook is going to text_classification file in the third cell. Then, upload the DOCX file of real texts to be check for plagiarism using AI in the step 4 (in the end of notebook).

B) Training Gotcha GPT (GotchaGPT_Train_eng.ipynb for English texts or GotchaGPT_Train_port.ipynb for Portuguese texts)

  1. Install and import the required libraries.
  2. Run the function to upload and read DOCX file. Please, DO NOT use PDF files because the model result is not as good as using DOCX files.
  3. Run the function to calculate Perplexity.
  4. Run the function to calculate Burstiness.
  5. After unzipping the DOCX files of AI-generated texts from the data_eng.zip (or data_port.zip for Portuguese texts) file in a directory of your computer, upload the DOCX file in the Google Colab notebook.
  6. Run the loop to calculate Perplexity and Burstiness for each AI-generated text. Note: It is convenient to separate the AI-generated texts in a diretory and the Human-generated texts in a different diretory.
  7. After unzipping the DOCX files of Human-generated texts from the data_eng.zip (or data_port.zip for Portuguese texts) file in a different directory of your computer, upload the DOCX file in the Google Colab notebook.
  8. Run the loop to calculate Perplexity and Burstiness for each Human-generated text.
  9. Prepare the classifier and standardize features (the dimensionality reduction is only important when the user wants to check many features of Human- and AI-generated texts. Using only Perplexity and Burstiness as features, it is not important to reduce the dimensionality).
  10. Train-test split, define the model pipeline, and predict if the text is AI-generated or human-written. Note: Here, we used decision tree as a first tentative.
  11. Run the accuracy, precision, F1, Recall, MCC, and Cohen´s Kappa scores.
  12. Run the confusion matrix.
  13. Plot the Perplexity versus Token and Burstiness versus Token graphs.
  14. Run the Random Forest model pipeline, save the model, and download it. (The steps 11, 12, and 13 are run for this model)
  15. Run the Extra Trees model pipeline, save the model, and download it. (The steps 11, 12, and 13 are run for this model)
  16. Run the Decision Tree model pipeline, save the model, and download it. (The steps 11, 12, and 13 are run for this model)
  17. Run the Ada Boost model pipeline, save the model, and download it. (The steps 11, 12, and 13 are run for this model)
  18. Resample technique: Create two different dataframe of majority and minority class, upsample minority class, Combine majority class with upsampled minority class, and upsample the minority class. Note: this step is important to check if the dataset is imbalanced.
  19. With the balanced dataset, the steps 14-17 are run again.
  20. It is also possible to run the Gaussian Naive Bayes model using Sklearn library to obtain the log-probability or probability estimates for each text.
  21. Do not forget to save and download text_classification.xlsx, rf_model_resample_eng.pkl, et_model_resample_eng.pkl, dt_model_resample_eng.pkl, and ab_model_resample_eng.pkl files for English texts (rf_model_resample_port.pkl, et_model_resample_port.pkl, dt_model_resample_port.pkl, and ab_model_resample_port.pkl files for Portuguese texts) in your computer to use them in the text detection next. Note: we already saved these files in the github repository to the user skip this training step that takes 1-2 hours depending on the web connection and if the user performs this task in a environment of execution with CPU or GPU. Using GPU, it takes only a couple minutes.

C) Text detection using Gotcha GPT (use notebooks GotchaGPT_eng.ipynb for English texts or GotchaGPT_port.ipynb for Portuguese texts)

  1. Install and import the required libraries.
  2. Run the function to upload and read DOCX file. Please, DO NOT use PDF files because the model result is not as good as using DOCX files.
  3. Run the function to calculate Perplexity.
  4. Run the function to calculate Burstiness.
  5. Upload the DOCX files of texts that the user wants to detect if they were generated by AI engines or not.
  6. Run the loop to calculate Perplexity and Burstiness for each text file.
  9. Upload the model files (rf_model_resample_eng.pkl, et_model_resample_eng.pkl, dt_model_resample_eng.pkl, or ab_model_resample_eng.pkl files for English texts (or rf_model_resample_port.pkl, et_model_resample_port.pkl, dt_model_resample_port.pkl, or ab_model_resample_port.pkl files for Portuguese texts)) in your notebook to use them in the text detection next. Note: we already saved these files in the github repository.
  10. Predict if the text is AI-generated or human-written by using any of the above models. Note: some models do not run sometimes. This occurs because of version upgrade in the pickel library or even python upgrade. If this issue happens, the user must train the models again unfortunately.
  This last task takes only a couple seconds. It does not matter if the user performs the task in a environment of execution with CPU or GPU.


# Documentation

The complete documentation about how to run the Gotcha GPT protocol and several tutorials is being developed. The article is now published on line: https://pubs.acs.org/doi/10.1021/acs.jcim.4c01203
Soon, we will build a pip installation for this application and an easy interface non-experts.

# Cite us

Gotcha GPT: Ensuring the Integrity in Academic Writing
Gralha, João Gabriel and Pimentel, André Silva
2024, Journal of Chemical Information and Modeling
doi: 10.1021/acs.jcim.4c01203
https://doi.org/10.1021/acs.jcim.4c01203
https://pubs.acs.org/doi/10.1021/acs.jcim.4c0120

# Get help

Gotcha GPT is being actively developed and some issues may arise or you may need extra help to run Gotcha GPT. In those cases, there are two main ways to get help:

1) Open a new issue in this repository
Or 
2) write an email to André Silva Pimentel (a_pimentel@puc-rio.br) (I will do my best to answer your questions as soon as possible).

# License

Gotcha GPT is available under MIT License. See license document for more details. URL and DOI: https://github.com/andresilvapimentel/Gotcha-GPT (https://doi.org/10.5281/zenodo.13769907)

# Contributors

This code was written under collaboration:
João Gabriel Gralha (Undergraduate student), who prepared the text dataset, and Andre Silva Pimentel (Supervisor), who wrote most of the code.
