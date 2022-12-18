# BiLSTM-IMDb-Review-Sentiment
Bidirectional Long Short-Term Memory Network to predict review sentiment as positive or negative

- The model learns bidirectional long-term dependencies between time steps of time series or sequence data which is ideal for analysis texual sentiments
- I initially used a pre-trained word-vec model and build a function to split the review into words and then representing each word by it's word vector .
- Set the max length of words as 258
- Sentences having more than maxlen words were truncated while shorter ones are zero-padded** by pre-adding all zero vectors.
- Built a generator function which takes **data [review,sentiment] and batchsize as input**. If number of rows processed is greater than batchSize, it trims X & y. This way we avoid running into memory issues by not bloating X and y bigger and bigger
- Finally built a Birectional LSTM model. Adding a dropout layer to force some of the feature values to zero. Note: Dropout is a regularization technique which sets the activation of few randomly chosen neurons of a hidden layer to zero.
- Set the learning rate, criterion as Binary cross Entropy as loss function and adam optimiser and ran the model on train data for 5 epochs.
- Used ROC AUC score and test accuracy to evaluate my model, with ROC AUC score coming just under 0.94 and test accuracy of close to 87%
