![BFH Banner](https://trello-attachments.s3.amazonaws.com/542e9c6316504d5797afbfb9/542e9c6316504d5797afbfc1/39dee8d993841943b5723510ce663233/Frame_19.png)

# Sithara Song Generator 

### A Manglish lyrics generator that generates manglish lyrics and form a song using AI. 

#### Data Collection

At First we scraped the lyrics(in manglish language) of Sitara songs from the internet. We used this [website](https://www.malayalachalachithram.com/listsongs.php?tot=147&g=1414&p=1) to scrape them and organized the lyrics in separate text files for training and validation. We used Beautiful Soup for web scraping. The source code regarding the same can be found in [scrapper](https://github.com/nandakishormpai2001/manglish_lyrics_generator/tree/main/scrapper) folder.

#### Data Preprocessing and Text Generation model

Minimal Data Preprocessing was done on the collected dataset, as more would have result in the loss of song structure. We split the data into train and validation in the ratio 85:15. A Deep Learning model with an architecture with an Embedding layer, LSTMs and fully connected layers were built using PyTorch and the dataset was trained on the model. We obtained a validation CrossEntropyLoss of `3.325`. Since the training was RAM intensive, it was carried out in Goole Colab and the jupyter notebook used for training and validation can be found [here](https://github.com/nandakishormpai2001/manglish_lyrics_generator/blob/main/model/train_notebook/manglish_lyrics_generator.ipynb)

#### Model Validation

The Validation Loss, was found out and was compared with the number of epochs, using suitable plot diagrams drawn with matplotlib. Required Hypertuning of parameters was done by varying batch size, number of epochs and learning rate. 

The source code regarding the model can be found in [model](https://github.com/nandakishormpai2001/manglish_lyrics_generator/tree/main/model) folder

#### Website and API

The backend was built on the micro-web framework Flask and it contains a function to handle GET request. The lyrics generation script and the model was used. The model was deployed onto Heroku after testing it locally. A website was built on  HTML, CSS, JS along with axios module for API request and response. Then the GET request is sent to the server hosted in Heroku at [api](https://manglish-lyrics-generator.herokuapp.com/.). The demo website is hosted in GitHub Pages and can be found [here](https://nandakishormpai.co/manglish_lyrics_generator/).

## Team members
1. [Nanda Kishor M Pai](https://github.com/nandakishormpai2001)
2. [Aswin Jayaji](https://github.com/aswinjayaji)
3. [Hari Krishnan U](https://github.com/Harikrishnan6336)


## Team Id

BFH/recEHiCGthePHSlQQ/2021

## Link to product walkthrough
[link to video]

## How it Works ?

1. Explaining the working of project
2. Embed video of project demo

## Libraries used

  - pandas - 1.2.4

  - numpy - 1.20.3

  - torch - 1.8.0+cpu

  - matplotlib - 3.4.2

  - flask - 2.0.0

  - gunicorn - 20.1.0

  - beautifulsoup4 - 4.9.3

## How to configure
Instructions for setting up project

## How to Run

👯 Clone the Repository:
```https://github.com/nandakishormpai2001/manglish_lyrics_generator.git```

Then move to the working directory.

```cd manglish_lyrics_generator```

First run the ```train.py``` .This will train the model and create a ML model `manglish_model.pth` in the `data` folder

Then run the ```generate.py```.This will generate the lyrics.

