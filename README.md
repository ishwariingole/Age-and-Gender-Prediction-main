# Age-and-Gender-Prediction


# Data preprocessing

Data I have downloaded is composed of 23,708 images with age and gender in the Image Name. For Example, 1_0_0_239389.JPG image means that age is 1, gender is 0 (male) and 0 refers to the race (not needed in this task).
So I split the image name on ' _ ' so I can get separated age and gender with image.
Also, I have shuffle all the images

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Dependencies](#dependencies)
- [Dataset](#dataset)
- [Usage](#usage)
- [Training](#training)
- [Results](#results)
- [File Structure](#file-structure)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)


## Project Overview

This repository contains a Jupyter Notebook that implements an Age & Gender prediction pipeline using computer vision and deep learning techniques. The notebook covers data loading, preprocessing, model building, training, evaluation, and inference. It is intended as a reproducible project to demonstrate how to predict age and gender from face images.


## Features
- Data preprocessing (face detection, resizing, normalization)
- Data augmentation (if present in the notebook)
- Deep learning model training (CNN / transfer learning)
- Model evaluation and visualization (accuracy, loss, sample predictions)
- Inference section to predict age and gender on new images


## Dependencies
A best-effort list of Python packages used in the notebook. Install with `pip` or `conda`.


```bash
pip install PIL pathlib sklearn tensorflow tensorflow tensorflow tensorflow matplotlib.pyplot numpy os pandas seaborn tensorflow
```

## Dataset

The notebook references dataset paths and image labels. Typical datasets used for age and gender prediction include IMDB-WIKI, UTKFace, or custom datasets with images and CSV labels. Check the notebook for the exact dataset path and format. Example expected structure:

```
/dataset/
  images/
  labels.csv  # contains image filename, age, gender
```


Detected dataset mentions / hints from the notebook:

- `Data I have downloaded is composed of 23,708 images with age and gender in the Image Name. For Example, 1_0_0_239389.JPG image means that age is 1, gender is 0 (male) and 0 refers to the race (not needed in this task).`

- `So I split the image name on ' _ ' so I can get separated age and gender with image.`

- `Also, I have shuffle all the images`

- `# Plotting Images`

- `Since dataset is too large, It is taking a lot of time to train the model so I am splitting the data and only using half of the dataset.`

- `I have already shuffled all the data to ensure no biasness in the dataset.`

- `According to the loss, the model is overfitting. I should have add some more regularization in the model to prevent overfitting but it is taking a lot of time. With 5k images, it takes 2.5 hours to fit on the train set. I stopped here but you can try adding regularization techniques to prevent overfitting.`

- `age_labels, gender_labels, image_path = [], [], []`

- `image_path.append(filename)`

- `age_labels.append(temp[0])`

- `gender_labels.append(temp[1])`

- `df['image'], df['age'], df['gender'] = image_path, age_labels, gender_labels`

## Usage
1. Clone this repository.
2. Place your dataset in the expected folder structure (see **Dataset** section).
3. Open the notebook `age-and-gender-detection.ipynb` in Jupyter Notebook or JupyterLab.
4. Run the cells sequentially to preprocess data, train the model, and run inference.


### Example: Run inference on a single image
```python
# inside the notebook
img = load_image('path/to/image.jpg')
preprocessed = preprocess(img)
pred = model.predict(preprocessed)
print(pred) # age prediction and gender class
```


## Training
Training instructions and detected training commands from the notebook:

- `model.compile(loss=['binary_crossentropy','mae'], optimizer='adam', metrics=['accuracy'])`

- `model_history = model.fit(x=x_train, y=[y_gender, y_age], batch_size = 10, epochs=20, validation_split= 0.1)`

- `plt.plot(model_history.history['gender_output_loss'])`

- `plt.plot(model_history.history['val_gender_output_loss'])`

- `plt.title('Gender loss')`

- `plt.ylabel('loss')`

- `plt.plot(model_history.history['age_output_loss'])`

- `plt.plot(model_history.history['val_age_output_loss'])`

- `plt.title('Age loss')`

- `# Visualizing loss`

- `According to the loss, the model is overfitting. I should have add some more regularization in the model to prevent overfitting but it is taking a lot of time. With 5k images, it takes 2.5 hours to fit on the train set. I stopped here but you can try adding regularization techniques to prevent overfitting.`


## Results
The notebook contains evaluation code and sample prediction outputs. Check the evaluation cells for metrics and sample visualizations.


## File Structure
- `age-and-gender-detection.ipynb` - main notebook (this file)
- `README.md` - project description (this file)
- `dataset/` - folder with images and labels (not included)
- `models/` - saved model weights and artifacts (if generated)


## Contributing
Contributions are welcome. If you want to improve the notebook, consider:
- Adding a requirements.txt or environment.yml
- Packaging preprocessing and model code into Python modules
- Adding unit tests for data processing functions


## License
This project does not include a license in the notebook. If you want to publish this repo, consider adding an open-source license such as MIT.


## Contact
Author: Ishwari Ingole
Project file: `age-and-gender-detection.ipynb`

If you want this README adjusted (shorter/longer, different sections, or to include exact commands and dataset references from the notebook), tell me which parts to expand and I will update it.
