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

<hr>

## Code and Implementation

```Wolfram
potter = Classify[<|
   "Harry" -> Import["https://www.google.co.uk/search?q=\"harry+potter\"+\"\Daniel+Radcliffe\"&tbm=isch", "Images"], 
   "Ron" ->   Import["https://www.google.co.uk/search?q=\"ron+weasley\"+\"\Rubert+Grint\"&tbm=isch", "Images"], 
   "Hermione" ->   Import["https://www.google.co.uk/search?q=\"hermione+granger\"+\"\emma+watson\"&tbm=isch", "Images"]|>]
   (*This generates a classifier function potter which can tell which Harry Potter Character you look like.*)
```

We can check how sure is the Classify function is about its classification by using Probabilities. We get the probability that an image fits into each class. In this case, there is an 85.4% probability that the image fits into the Harry class.

```Wolfram
potter[image] (*Drag and drop you photo in place of image here*)
potter[image,"Probabilities"]
```

Take a photo of yourself using your camera, and give the photo the variable name "image" and put this photo through the Classify function. 
Run your photo through the potter classifier, and use "Probabilities" to see how similar you look to each character.

```Wolfram
image = CurrentImage[ImageSize -> 350] (*This function will take an image of yours*)
potter[image]
potter[image, "Probabilities"]
```
Build a button that takes a photo and runs it through the potter classifier.
```Wolfram
 Button["New Photo",
 image = CurrentImage[ImageSize -> 350];
 character = potter[image];
 probabilities = potter[image, "Probabilities"]]
```
```Wolfram
Dynamic[image]
Dynamic[character]
Dynamic[probabilities]
```

Make a Grid with four rows.

1. The first row should have a title. You can make text look the way you want using Text and Style.
2. The second row should be the Dynamic image. This is either be the image from your camera or the image you import using your buttons.
3. The third row should have two items: the result of your Classify function, and your first button. The first button is either CurrentImage or FileNameSetter, depending on whether you have one or two buttons.
4. The fourth row should have one item: the result of "Probabilities" from your Classify function.

You can use Framed and FrameStyle to draw a frame around the Grid.

```Wolfram
Framed[Grid[{
   {Text[Style["Which Harry Potter Character Are You?", Bold, 18]]},
   {Dynamic[image]},
   {Text[Style[Dynamic[character], Bold, 18]],
    Button["New Photo",
     image = CurrentImage[ImageSize -> 350];
     character = potter[image];
     probabilities = Normal[potter[image, "Probabilities"]]]},
   {Text[Style[Dynamic[probabilities], 14]]}}], FrameStyle -> Thick]
 ```
<p align="center">
  <img width="460" src="https://github.com/amandewatnitrr/Wolfram/blob/main/Fun%20Project%20-%20Faical%20Recog%20%5BHarry%20potter%5D/Screenshot%202021-06-07%20022035.png">
</p><br>

<p align="center">
  <img width="460" src="https://github.com/amandewatnitrr/Wolfram/blob/main/Fun%20Project%20-%20Faical%20Recog%20%5BHarry%20potter%5D/0_C-cPP9D2MIyeexAT.gif">
</p><br>
