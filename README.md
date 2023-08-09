# Image-identifier
This is a python code which is used to predict the name of the image which is given as input.
Certainly! This code uses the ImageAI library to perform image classification using the MobileNetV2 model. It takes an input image, predicts the top classes for that image, and displays the predicted classes along with their corresponding probabilities.

Here's the explanation of the code step by step:

1. `from imageai.Classification import ImageClassification`
   This line imports the `ImageClassification` class from the `imageai.Classification` module. This class provides functionality for performing image classification tasks.

2. `import os`
   This line imports the built-in `os` module, which is used for interacting with the operating system, such as working with file paths.

3. `exec_path = os.getcwd()`
   This line gets the current working directory and stores it in the variable `exec_path`. This path will be used to locate model files and the input image.

4. `prediction = ImageClassification()`
   This line creates an instance of the `ImageClassification` class.

5. `prediction.setModelTypeAsMobileNetV2()`
   This line sets the model type to MobileNetV2 for image classification. The model will use the MobileNetV2 architecture for making predictions.

6. `prediction.setModelPath(os.path.join(exec_path, 'mobilenet_v2-b0353104.pth'))`
   This line sets the path to the pre-trained MobileNetV2 model file. The `os.path.join()` function is used to create a full path by joining the current working directory and the model file name.

7. `prediction.loadModel()`
   This line loads the MobileNetV2 model using the provided path.

8. `predctions, probabilities = prediction.classifyImage(os.path.join(exec_path,'house.jpg'), result_count=5)`
   This line uses the loaded model to classify the image located at the specified path (`os.path.join(exec_path,'house.jpg')`). The `result_count` parameter is set to 5, which means it will return the top 5 predicted classes along with their probabilities.

9. The next loop iterates over the predicted classes and probabilities:

   a. `for eachPred, eachProb in zip(predctions, probabilities):`
      This loop iterates over pairs of predicted classes (`eachPred`) and their corresponding probabilities (`eachProb`).

   b. `print(f'{eachPred} : {eachProb}')`
      This line prints each predicted class along with its corresponding probability.

To summarize, the code uses the MobileNetV2 model to perform image classification on an input image (`'house.jpg'`), predicts the top classes, and displays the predicted classes along with their probabilities.
