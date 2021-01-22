# Introducing Hades Machine Learning Lambda Container
Hades invests a lot of time figuring out how to distribute Machine Learning Models on the cloud, we are making all our DevOps and MLOps work open source so you don't have to. Use this custom Image to server your Machine Learning Models on AWS Lambda.
![Hades](https://github.com/the-muses-ltd/Hades-Machine-Learning-Lambda-Function-Container/blob/main/Readme%20Assets/jelly.gif?raw=true)


## How to use this custom container setup:
To get started, clone the repo and `cd` into the `hades_ml_lambda` folder. Now run the following commands in your terminal:
1. Build the image using Docker.
```
docker image build -t lambda_env/hades-lambda:latest .
``` 
2. Run the docker container using the image you just built.
```
docker run -p 9000:8080 lambda_env/hades-lambda:latest
```
4. Change your working directory to the `tester folder`

```
cd tester
```
5. Run our custom file for testing the lambda function.
```
python test.py
```
If you're still using our saved model and the unchanged test script you should get a response of 9 as your prediction and that means it's working!


## How to use your own saved models:
All you need to do is swap out your saved model with the one saved in the app folder and you're good to go, it really is that easy! 

How does this work:
Since the announcement of 

![Docker](https://github.com/the-muses-ltd/Hades-Machine-Learning-Lambda-Function-Container/blob/main/Readme%20Assets/6846390_preview.png?raw=true)
First, we package up our image using Docker to enable
![AWS Lambda](https://github.com/the-muses-ltd/Hades-Machine-Learning-Lambda-Function-Container/blob/main/Readme%20Assets/1_GwOUMMMXKde8kr1i2kDByw.png?raw=true)
Next, we upload our built image to ECR to run it on AWS Lambda. Follow the instructions here on how to get your pre-built image Lambda Image on the cloud:
https://aws.amazon.com/blogs/aws/new-for-aws-lambda-container-image-support/

## Things to note:
1. We suggest saving your model in .h5 format to ensure compatibility.
2. You may need git-lfs if your model is too large.

## Prerequisites:
To use this contianer you'll need:
1. Docker Desktop Installed https://www.docker.com/products/docker-desktop
2. The Docker CLI installed on your local machine.
3. Your model will need to be trained with Tensorflow 2 or above and ideally saved with Keras.
