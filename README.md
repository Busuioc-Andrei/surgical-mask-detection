# Surgical mask detection

I wrote a machine learning project that deals with surgical mask recognition based on wav audio files. For implementing this task I used **Mel-frequency cepstral coefficients (mfcc)** and **Logistical regression.**

# Why mfcc and logistical regression

**Mel-frequency cepstrum** is a representation of the short-term power spectrum of a sound, based on a linear cosine transform of a log power spectrum on a nonlinear mel scale of frequency, it's very often used in speech recognition because of how similar it is to the way humans process sounds.
**Logistical regression** is a statistical model that in its basic form uses a logistic function to model a binary dependent variable. It is a simple model in it's nature and is especially useful in classifying data in a binary way, reason why it works well for this task.

![LogReg_Train](https://user-images.githubusercontent.com/49075040/82742033-ab53b600-9d61-11ea-8a6d-6c41601b1459.png)
![Sigmoid](https://user-images.githubusercontent.com/49075040/82742034-abec4c80-9d61-11ea-8f3d-a2a151e5ee0c.PNG)
![normData](https://user-images.githubusercontent.com/49075040/82742035-ac84e300-9d61-11ea-9d93-50168102a95c.PNG)
![transformData](https://user-images.githubusercontent.com/49075040/82742037-ac84e300-9d61-11ea-8b1a-85af2b4d2ece.PNG)
![useCache](https://user-images.githubusercontent.com/49075040/82742038-ac84e300-9d61-11ea-9f85-7a23272e9211.PNG)
![classifier](https://user-images.githubusercontent.com/49075040/82742039-ad1d7980-9d61-11ea-8069-8cf8cae99b96.PNG)
![precision](https://user-images.githubusercontent.com/49075040/82742040-ad1d7980-9d61-11ea-9cb3-c16b05a061ac.PNG)
![noNorm_CM](https://user-images.githubusercontent.com/49075040/82742041-adb61000-9d61-11ea-80dc-a898d62a93da.png)
![noNorm_scatter](https://user-images.githubusercontent.com/49075040/82742042-adb61000-9d61-11ea-9c32-941dcee89a31.png)
![scatter](https://user-images.githubusercontent.com/49075040/82742043-ae4ea680-9d61-11ea-8dd9-1394c01117a3.png)
![CM](https://user-images.githubusercontent.com/49075040/82742044-ae4ea680-9d61-11ea-9ecd-cd22144bccd9.png)
