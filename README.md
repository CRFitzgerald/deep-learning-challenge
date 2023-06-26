# deep-learning-challenge

## Analysis Overview

The purpose of this analysis is to help the nonprofit foundation Alphabet Soup to select the applicants for funding with the best chance of success in their ventures. Alphabet Soup's business team has provided a CSV file continaing the metadata of 34,000 organizations to whom AS has provided funding in the past. Using machine learning and neural networks, I have found the organizational features most strongly coorelated with success.

## Results

# Data Preprocessing

* "IS_SUCCESSFUL" is the target for my model.
* Aside from the removal of EIN and NAME, all other columns were used as features at various times (excluding, of course, IS_SUCCESSFUL, as it was the target).
* "EIN" and "NAME" should be removed as they are identifiers only. 

# Compiling, Training, and Evaluating the Model

* How many neurons, layers, and activation functions did you select for your neural network model, and why?
* None of my three optimization models achieved success.
* In my first optimization attempt, I leveraged kerastuner. I believed that its automation would cut down on trial-and-error attempts. It did not provide valuable insight, however, so I moved on to simpler methods. In my second attempt, I removed the CLASSIFICATION and ACTIVE columns. My thought was that CLASSIFICATION is a bigger set of variables that are put more concisely by the USE_CASE column. And we should only be contributing to active organizations, so a column for this variable was just noise. Dropping the columns also did not help with accuracy. Finally, I tried using fewer epochs. Similarly, this did not help.

## Summary

Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
