# MAML-Investigation

*I will be reorganizing the folder structure, refactoring the code and adding comments so that the project is easier to understand once I have the time !*

## Project Organization
This is the final project for the course Comp 550: Introduction to Natural Language Processing (more info here [link](https://www.mcgill.ca/study/2023-2024/courses/comp-550)) which I completed with Tommaso Rivetti and Eliott Regnier. We received the grade of 85% (A) for the project.

# Abstract
Deep neural networks are known for their excellent performance on classification tasks in NLP. However, a large amount of training data is required in order to generalize to generalize to unseen data and achieve competitive performance. On the other hand, simpler ML models such as Logistic Regressions or Naive Bayes models start giving accurate results on classification tasks with much less input data in training. 

This paper seeks to experiment with few shot learning through the use of a Model Agnostic Meta Learning model (MAML) to bridge the gap between low training data size and performance. First, we implemented the MAML learning algorithm, built a Bi-LSTM model and train the model first normally, then using the MAML algorithm. Then, we built a Naive Bayes- and Logistic Regression- classifier. We then compared how many training points the MAML-augmented Bi-LSTM model needed to see before it got results similar to the simpler models on a binary classification task. The goal is to determine how few datapoints are required for few shot learning augmented deep neural model to surpass simpler models. We find that a Logistic Regression model with GloVe word embeddings still performs better than our MAML augmented Bi-LSTM on low amounts of data. However, the latter does in fact yield high results (90\% and up on F1) after seeing a smaller number of points than a vanilla Bi-LSTM model. Although it may not be quite competitive enough with the Logistic Regression model on few samples, our model can still be optimized further.

# Findings
Given our results, we can tentatively validate our hypotheses that the MAML-augmented Bi-LSTM can learn faster than vanilla Bi-LSTM. However, it does not outperform simpler methods after being shown small amounts of data points while the simpler models were trained on these small numbers of points. Training our Bi-LSTM with MAML does seem, as well, to have a stabilization effect regarding a model's score on the validation dataset. While the vanilla model's score on the validation data fluctuates a lot, the MAML-augmented Bi-LSTM's scores continuously rise and stabilize around its optimal score parameters. Thus, MAML might have a stabilizing effect on the model it trains.

More information can be found in the paper uploaded [above](https://github.com/mika-jpd/MAML-Investigation/blob/master/(Paper)%20Investigating%20the%20Limits%20of%20MAML%20Meta-Learning%20for%20Few-Shot%20Learning%20in%20a%20Bi-LSTM%20Model.pdf).
