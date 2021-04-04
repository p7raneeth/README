# Indian Paper Curreny Prediction

## Table of Contents
---
* Demo
* Overview
* Motivation
* Technical Inspection
* Installation
* Run
* Deployment
* Directory Tree
* Technologies Used



## Demo
---

[Link to Application](https://indian-currency-prediction.herokuapp.com "Predict here ")

![Demo picture](https://camo.githubusercontent.com/75de4c7440d00b819dbbe651051f72203cff9893bc4299f753e4f46ecadaa5dd/68747470733a2f2f692e696d6775722e636f6d2f35676a3455536a2e706e67)


## Overview
---

This is a simple __image classification__ Flask app trained on the top of Keras API. The trained model ```(app/model/model.h5)``` takes an image (Indian Paper Currency) as an input and predict the class of image from **10, 20, 50, 100, 200, 500, 2000** denominations.


## Motivation
---

What could be a perfect way to utilize unfortunate lockdown period? Like most of you, I spend my time in cooking, Netflix, coding and reading some latest research papers on weekends. The idea of classifying indian currency struck to me when I was browsing through some research papers. I couldn't find any relevant research paper (and of course dataset!) associated with it. And that led me to collect the images of Indian currency to train a deep learning model using [this](https://github.com/hardikvasa/google-images-download "google images download github repo") amazing tool.


## Technical Aspect
---

1. Training a deep learning model using Keras. __*(Not covered in this repo. I'll update the link here once I make it public.)*__
2. Building and hosting a Flask web app on Heroku.
A user can choose image from a device or capture it using a pre-built camera.
Used **Amazon S3 Bucket** to store the uploaded image and predictions.
Used **CSRF Token** to protect against CSRF attacks.
Used **Sentry** to catch the exception on the back-end.
After uploading the image, the predictions are displayed on a **Bar Chart.**

## Installation
---

The Code is written in Python 3.7. If you don't have Python installed you can find it here. If you are using a lower version of Python you can upgrade using the pip package, ensuring you have the latest version of pip. To install the required packages and libraries, run this command in the project directory after cloning the repository:

```python
pip install -r requirements.txt
```

## Run
---

> Step1

__Linux and macOS User__ 

Open ```.bashrc``` or ```.zshrc``` file and add the following credentials:


```
export AWS_ACCESS_KEY="your_aws_access_key"
export AWS_SECRET_KEY="your_aws_secret_key"
export ICP_BUCKET='your_aws_bucket_name'
export ICP_BUCKET_REGION='bucket_region'
export ICP_UPLOAD_DIR='bucket_path_to_save_images'
export ICP_PRED_DIR='bucket_path_to_save_predictions'
export ICP_FLASK_SECRET_KEY='anything_random_but_unique'
export SENTRY_INIT='URL_given_by_sentry'
```

Note: **SENTRY_INIT** is optional, only if you want to catch exceptions in the app, else comment/remove the dependencies and code associated with sentry in *app/main.py*

**Windows User**

Since, I don't have a system with Windows OS, here I collected some helpful resource on adding User Environment Variables in Windows.

**Attention**: Please perform the steps given in these tutorials at your own risk. Please don't mess up with the System Variables. It can potentially damage your PC. **You should know what you're doing.**

* https://www.tenforums.com/tutorials/121855-edit-user-system-environment-variables-windows.html

* https://www.onmsft.com/how-to/how-to-set-an-environment-variable-in-windows-10


> STEP 2

To run the app in a local machine, shoot this command in the project directory:

```gunicorn wsgi:app```

# Deployement on Heroku
---
Set the environment variable on Heroku as mentioned in **STEP 1** in the Run section. [Reference](https://devcenter.heroku.com/articles/config-vars)


![Deployment Image](https://camo.githubusercontent.com/1e4780b4983e1779438fa78840c50e930ad350d9409214bf2555a0d5e021efde/68747470733a2f2f692e696d6775722e636f6d2f546d534e6859472e706e67 )


## Directory Tree
---

```
|---app
|   |--- __init.py
|   |--- main.py
|   |--- model
|   |--- static
|   |--- templates
|   
|--- config
|   |--- __init.py
|---requirements.py
|--- runtime.txt
|--- LICENCE
|--- procfile.txt
|--- README.md
|--- wsgi.py

```

## Technologies Used
---
![](https://img.shields.io/badge/MADE_WITH-Python-informational?style=flat&logo=<LOGO_NAME>&logoColor=red&color=FF0000)

![](https://camo.githubusercontent.com/d441b09246a1e2c7ef0eaf05f1523d5250885a27b5b23324e1196d78aa30f056/68747470733a2f2f6b657261732e696f2f696d672f6c6f676f2e706e67)

![](https://camo.githubusercontent.com/fca916e3bef7b47789e4f46ee0648111eb59e0111fa21af46547a4a9687bb50b/68747470733a2f2f7777772e6b696e64706e672e636f6d2f706963632f622f3330312f333031323438342e706e67)