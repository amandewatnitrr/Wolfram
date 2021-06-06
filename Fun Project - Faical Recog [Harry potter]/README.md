# Fun Project - Facial Recognition - Similarity with Harry potter Characters
<p align="center">
  <img width="460" src="https://github.com/amandewatnitrr/Wolfram/blob/main/Fun%20Project%20-%20Faical%20Recog%20%5BHarry%20potter%5D/7cd53d36d121d839da9600ca055b01db.gif">
</p><br>
The Project is just made for fun purpose it doesn't have any real-world implementation though you can make one out if you try and innovate!!
<hr>

## Requirements

1. A Laptop\Computer\Raspberry Pi with Camera
2. Wolfram | One (Installed) Click here to get trial 👉<a href="https://account.wolfram.com/access/wolfram-one/trial"> ![Wolfram](https://img.shields.io/badge/Wolfram-DD1100?style=flat-square&logo=Wolfram&logoColor=white)</a>

<hr>

## Introduction

We are going to build a classifier program that will learn to recognise categories of pictures. The classifier will then be able to study new images and guess which division they belong to. We will use images of Harry Potter, Hermione Granger, and Ron Weasley as data for the categories. We will use Classify function to order images of Harry Potter characters depending on the characteristics of the images.

First, In order to train the model, we need images of Harry, Ron, and Hermione so that we can train the classifier to recognise their faces. To do this, we need to get the URL to a Google image search and then use Import to import the images. Then train the classifier function on these images, so that it puts them into three categories: "Harry", "Ron", and "Hermione".

```Wolfram
potter = Classify[<|
   "Harry" -> Import["https://www.google.co.uk/search?q=\"harry+potter\"+\"\Daniel+Radcliffe\"&tbm=isch", "Images"], 
   "Ron" ->   Import["https://www.google.co.uk/search?q=\"ron+weasley\"+\"\Rubert+Grint\"&tbm=isch", "Images"], 
   "Hermione" ->   Import["https://www.google.co.uk/search?q=\"hermione+granger\"+\"\emma+watson\"&tbm=isch", "Images"]|>]
```
