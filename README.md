# Challenge
Train a binary classifier on given 7494 academic article titles and/or abstracts to predict if the text belongs to `Material Science` or `Chemistry` category and evalute the best performing model's F-1, accurracy and AUC scores.

### Data
`wos2class.json` dataset is available in `data` folder. This dataset contains 7494 JSON objects with the following schema:
```
Title: String with maximum 279 characters.
Abstract: String with maximum 5289 characters.
Label: Categorical string. Either "Chemistry" or "Material Science".
```

Since the dataset is almost balanced, you may skip balancing step.

### Requirements
1. The project must be developed in Python 3+.
2. The classifier must be implemented in PyTorch or Tensorflow.
3. Datapoints from each label should be split into TRAIN/TEST with 80%-20% rates. Save your training and test datasets as `wos2class.train.json` and  `wos2class.test.json`. Expected distribution:
```              
                       TRAIN       TEST
Material Science:      3033        759
Chemistry:             2962        740
```
4. You can train your model on Titles or Abstracts or somehow combine these two fields as an input.
5. Feel free to use any pretrained models (such as FastText, BERT, ELMo, GloVe etc) to extract features or train your own language model from scratch depending on your accuracy objectives.
6. There is no minimum F-1 or accuracy score requirement. Try your best. The higher the better.
7. You can develop your code to run on CPUs or GPUs. Feel free to choose what's convenient for you.
8. Results must be reproducable. That's why, do not forget to use random seeds where applicable.
9. Check your code against PEP8 style specifications. Flake8 is a great linter package to comply with PEP8 standards.



### Good-to-have's (not required)
1. Dockerfile that install Python 3+, all required packages and runs your training and testing code. Makefile to build the image and run the container would help a lot as well.
2. Precision-Recall curves for classification thresholds in range (0-1).

### Submission
1. Create a private clone of this repository on GitHub (so that other participants cannot copy your solution), and give account [zafercavdar](https://github.com/zafercavdar) at least read access. Read more on duplicating a repository [here.](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/duplicating-a-repository)
2. Put your `wos2class.train.json` and `wos2class.test.json` files to `data` folder.
3. Put your training code (including preprocessing, feature extraction, classification etc) into `train.py`
4. Put your the best performing model's weights to `models` folder.
5. Put your testing code (similar to train.py) into `test.py` along with F-1, accurracy and AUC evaluators + confusion matrix calculators. Include your code to plot ROC curve as well.
6. In case any external dependency is installed, please add them to `requirements.txt` file with their versions, for example:
```
// requirements.txt

pandas==0.24.0
torch==1.6.0
scikit-learn==0.21.3
```
7. Write a short REPORT.md file describing your approach, main challenges experienced and observations, the highest metrics you achieved, ROC curve plot, confusion matrix and your ideas on how to improve further.
8. Send us an email to notify that you're done with your model.
