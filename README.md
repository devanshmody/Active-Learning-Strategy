# Active-Learning-Strategy
Active learning aims at reducing the number of examples required to achieve the desired accuracy by selectively sampling the examples for a user to label and train the classifier with.

Training via Active Learning

The general process we follow when performing Active Learning is demonstrated below:
<img width="625" alt="Screenshot 2024-05-20 at 11 23 13 AM" src="https://github.com/devanshmody/Active-Learning-Strategy/assets/13017779/58a48421-5e83-473a-9ed0-5d10bfd396d9">

Active Learning

The pipeline can be summarized in five parts:

Sample and annotate a small, balanced training dataset
Train the model on this small subset
Evaluate the model on a balanced testing set
If the model satisfies the business criteria, deploy it in a real time setting
If it doesn't pass the criteria, sample a few more samples according to the ratio of false positives and negatives, add them to the training set and repeat from step 2 till the model passes the tests or till all available data is exhausted.

For the code below, we will perform sampling using the following formula:
<img width="452" alt="Screenshot 2024-05-20 at 11 24 54 AM" src="https://github.com/devanshmody/Active-Learning-Strategy/assets/13017779/2845bd77-e1b4-4a49-9c63-d6fbeb71d893">

Ratio Sampling

Active Learning techniques use callbacks extensively for progress tracking. We will be using model checkpointing and early stopping for this example. The patience parameter for Early Stopping can help minimize overfitting and the time required. We have set it patience=4 for now but since the model is robust, we can increase the patience level if desired.

Multiple areas where this strategy can help when we want to train an LLM or fine-tune any LLM model for specific tasks just by using small amounts of data better results can be achieved with less amount of time spent on training.




