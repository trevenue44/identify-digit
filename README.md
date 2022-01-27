# identify-digit
In this repository, I put all my work on developing a really good model that is capable of identifying digits from pictures; both handwritten and typed. By "digits", I mean 0 - 9.

I have a trial version of this model already deployed to https://identifydigit.herokuapp.com/

This current model is really bad and doesn't do all the work. 

In this repository, I'm going to try and create an improved version of this model and keep improving it using my skills on supervised machine learning algorithms.

## Current Status of this Project:
Trained a new `SVC()` with pretty good precision, recall and f1 scores of around 0.96. But it still doesn't work well on the real world test images. Maybe the MNIST_784 dataset is not realistic enough to work on real world problems.

Check file named [model_testing_on_images](./model/model_testing_on_images.ipynb) for more information

Progress...

## The Dataset
The dataset that I'll be using is the MNIST dataset which comes with the Scikit-Learn package.

### General Understanding of the MNIST_784 dataset
- There are 70,000 examples. 
- Generally, we use 60,000 for training and the rest 10,000 for testing of the final model
- Plotting the images of the digits for each example show that the images are so clean without any noise or rotation of images
- It is far from the real world pictures of images that are taken
- Due to the above, I have to find a way of creating a more realistic dataset to train models on.
- That's when data augmentation comes in.

### Using Data Augmentation
- The `switch_colors()` function interchanges the white and black pixels. The images come as digits written in black on a white paper but what if it's rather a white text on black paper? Switching the colors in the data used to train model accounts for more posibilities. Hence, a better model
- The `add_noise()` function adds noise the the images. The real life images of digits would not be that clean. It's best to train the model on that sort of image alse.
- The `make_shift()` function helps shift the writings to different locations of the image. The digits would not always be in the middle of the image.
- These functions would be used to create different variations of the 60,000 training examples.
- The final dataset that'd be used to train the models would be a combination of all these variations.

Check the file named [model_creation](./model/model_creation.ipynb) for more information on how I'm really doing the building

## Tools and Technologies
- [Scikit-Learn](https://scikit-learn.org/)
- [Jupyter](https://www.jupyter.org/) notebooks
- [Python programming Language](https://www.python.org/)
- [Pandas](https://pandas.pydata.org/)
- [NumPy](https://numpy.org/)

## Some Resources
- Hands-on Machine Learning with Scikit-Learn, Keras and TensorFlow (a book by [Aurelien Geron](https://www.twitter.com/aureliengeron))

## License?
Yes, this work is licensed. 

Please check the file named [LICENSE](./LICENSE) for the details.
