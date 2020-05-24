# Surgical mask detection

I wrote a machine learning project that deals with surgical mask recognition based on wav audio files. For implementing this task I used **Mel-frequency cepstral coefficients (mfcc)** and **Logistic regression.**

## Why mfcc and logistic regression

**Mel-frequency cepstrum** is a representation of the short-term power spectrum of a sound, based on a linear cosine transform of a log power spectrum on a nonlinear mel scale of frequency, it's very often used in speech recognition because of how similar it is to the way humans process sounds.

**Logistic regression** is a statistical model that in its basic form uses a logistic function to model a binary dependent variable. It is a simple model in it's nature and is especially useful in classifying data in a binary way, reason why it works well for this task.

## Data transformation

![transformData](https://user-images.githubusercontent.com/49075040/82742037-ac84e300-9d61-11ea-8b1a-85af2b4d2ece.PNG)

The first step was to extract the mfcc features from the audio files, this was done using **librosa**, 40 coefficients were returned and a mean was calculated using numpy.

![normData](https://user-images.githubusercontent.com/49075040/82742035-ac84e300-9d61-11ea-9d93-50168102a95c.PNG)

The data transformation also included the normalization of the values obtained using StandardScaler from **sklearn.preprocessing**, fitting the data on the training set and transforming on every set.

## Data caching

![useCache](https://user-images.githubusercontent.com/49075040/82742038-ac84e300-9d61-11ea-9f85-7a23272e9211.PNG)

At first it was observed that on each run of the code, the part that took a substantial amount of time was the transforming of data, because of that a data caching mechanism was implemented to ensure very short code executions when fidgeting with the classifier, the plotting and other things unrelated to the transformation of data.

## Classifier

![classifier](https://user-images.githubusercontent.com/49075040/82742039-ad1d7980-9d61-11ea-8069-8cf8cae99b96.PNG)

The classifier used was **LogisticRegression from sklearn.linear_model**, the solver used was **liblinear** because the dataset was small and because the classification needed wasn't a multiclass one.
Multiple hyperparameters were tried out but the result was usually worse after modifying any of the default hyperparameters so the approach was kept simple.

## Precision

![precision](https://user-images.githubusercontent.com/49075040/82742040-ad1d7980-9d61-11ea-9cb3-c16b05a061ac.PNG)

The precision obtained from the validation set was 0.649.

## Plotting

For plotting I used a binary color scheme, the green points are samples that have a positive label, and the red points are samples that have a negative label.
The y axis represents the probability that a sample has a positive label, which the classifier uses to predict the value of the label by comparing the probability to 0.5.
The x axis represents the mfcc values of a sample flattened to a single value, although the classifier used more data to build the model, this value was used to visually represent an estimate of the features.

![LogReg_Train](https://user-images.githubusercontent.com/49075040/82742033-ab53b600-9d61-11ea-8a6d-6c41601b1459.png)

The plot above shows the distribution of the training dataset and the sigmoid function that was used by the classifier.

![scatter](https://user-images.githubusercontent.com/49075040/82742043-ae4ea680-9d61-11ea-8dd9-1394c01117a3.png)

This is a scatter plot of the validation dataset.

![CM](https://user-images.githubusercontent.com/49075040/82742044-ae4ea680-9d61-11ea-9ecd-cd22144bccd9.png)

Here we can see the confusion matrix of the validation dataset, we can observe that the cases of false negatives and false positives is almost identical, this might be a coincidence because of the small dataset so we can't base any conclusion on it.
