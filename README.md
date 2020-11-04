# Pulmonary Embolism Dectection

This repo contains our work for the RSNA STR Pulmonary Embolism Dectection on Kaggle:
https://www.kaggle.com/c/rsna-str-pulmonary-embolism-detection.

In this competition, we had the CT scans and train a model that helps predict whether those scans indicates Pulmonary Embolism and specify its different attributes.
The evaluation of this competitation is divided into 2 parts: the image model, which predicts whether there is Pulmonary Embolism from the CT scans, and the exam model, which specifies the attribute of the Pulmonary Embolism if the output from the image model is positive.

 - Image model
 
 We implemented different Windowing techniques on the CT scans then train them through a pretrained EfficientNetB0. We trained the model for 25000 with batch size of 64.
 The result in the validation set turned out to be average binary_cross_entropy loss: 0.6931602358818054 and auc_pr: 0.054040178656578064, which is definitely not a good result.
 
 - Exam model

We implemented a 3D Conv model to process stacks of CT scans for each study so the model can learn better the correlation of the results in each individual scans in a study.

Below is the link to the submitted trained weights for our models: 

https://www.kaggle.com/hungndo/pulmonary-embolism-model-weights

In this competition, we were competing with real-experienced Data Scientists from all over the world.
We ended up ranked 726 on the leaderboard. We had an submission error at the end of the competition so this ranking does not reflect the true performance of our model.

---------------
**Contributors**

- Joseph Tan
- Hung Do

**Acknowledgements**

- https://www.kaggle.com/allunia/pulmonary-dicom-preprocessing - DICOM preprocessing

- https://www.kaggle.com/seraphwedd18/pe-detection-with-keras-model-creation - DICOM preprocessing

- https://www.kaggle.com/redwankarimsony/rsna-str-pe-gradient-sigmoid-windowing/comments - DICOM windowing
