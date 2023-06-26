# AlphabetSoup Funding Report 

## Overview

The purpose of this analysis is to help the nonprofit foundation Alphabet Soup to select the applicants for funding with the best chance of success in their ventures. Alphabet Soup's business team has provided a CSV file continaing the metadata of 34,000 organizations to whom AS has provided funding in the past. Using machine learning and neural networks, I aimed to find organizational features most strongly coorelated with success.

## Results

### Data Preprocessing

* "IS_SUCCESSFUL" is the target for my model.
* Aside from the removal of EIN and NAME, all other columns were used as features at various times (excluding, of course, IS_SUCCESSFUL, as it was the target).
* "EIN" and "NAME" should be removed as they are identifiers only. 

### Compiling, Training, and Evaluating the Model

* I used six neurons per hidden layer. I wanted dense layers due to the large numbers of features in the dataset. While the optimal number of hidden layers to use in a given model is still being debated, I chose to use two. From the research I did, this seemed to be the maximum number that is considered helpful in most contexts. I used Relu and Sigmoid as activation functions that I created manually  because I have the most experience using them. However, when used kerastune, it was suggested that Tahn might be a better option.
  
  ![Screenshot 2023-06-25 at 8 25 47 PM](https://github.com/CRFitzgerald/deep-learning-challenge/assets/117607189/b13b7efd-d1bc-4852-9cf8-0786154e8e7c)

* None of my three optimization models achieved success.
* In my first optimization attempt, I leveraged kerastuner. I believed that its automation would cut down on trial-and-error attempts. It did not provide valuable insight, however, so I moved on to simpler methods. In my second attempt, I removed the CLASSIFICATION and ACTIVE columns. My thought was that CLASSIFICATION is a bigger set of variables that are put more concisely by the USE_CASE column. And we should only be contributing to active organizations, so a column for this variable was just noise. Dropping the columns also did not help with accuracy. Finally, I tried using fewer epochs. Similarly, this did not help.

### Summary

All four of the models used (the initial, pre-optimization model, the keras-tuned model, the model with fewer columns, and the model with fewer epochs), all had accuracy between 71-72%. The keras-tuned slightly outperformed the rest with accuracy of 72.68%. My recommentation would be to use this model as a baseline to continue fine-tuning manually with additional time and resources.
