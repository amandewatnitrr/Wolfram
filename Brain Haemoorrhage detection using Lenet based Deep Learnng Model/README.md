# Brain Haemoorrhage detection using Lenet based Deep Learnng Model
<hr>

## Introduction
<img align="left" src="https://github.com/amandewatnitrr/Wolfram/blob/main/Brain%20Haemoorrhage%20detection%20using%20Lenet%20based%20Deep%20Learnng%20Model/deep-brain-bleeds-new-2.gif" width="40%"/>
Brain haemorrhage is a type of stroke. It's caused by an artery in the brain bursting and causing confined bleeding in the enclosing tissues. This bleeding kills brain cells. The Greek root for blood is hemo. Haemorrhage means "blood bursting forth." Brain haemorrhages are also called cerebral haemorrhages, intracranial haemorrhages, or intracerebral haemorrhages. Cerebral haemorrhage deems for about 13% of all strokes in the United States. It is the next foremost cause of stroke. (The principal cause of stroke is a blood clot – thrombus – in an artery in the brain, which blocks blood flow and cuts off required oxygen and nutrients to the brain.

## Importing Dataset
I implied a data set of haemorrhage and non-haemorrhage brain from Kaggle. Each class placed in its corresponding variable.
```Wolfram
infected = FileNames["*.png","E:\\COURSES\\Wolfram\\BrainTumorImagesDataset\\training_set\\hemmorhage_data"];
uninfected = FileNames["*.png","E:\\COURSES\\Wolfram\\BrainTumorImagesDataset\\training_set\\non_hemmorhage_data"];
```
## Constructing File Objects for Images
I wanted to match each brain image with a value of either true for Hemorrhage or false for no Hemorrhage. To improve the efficiency of the importation, I formulated separate file objects for each of the image variables. Each variable contained 70 images for parasitized and uninfected cells.

```Wolfram
infectedIMG = File /@ infected;
uninfectedIMG = File /@ uninfected;
```
Then I created a record of 70 true and false values which would be used to be matched up with their respective images. I set these lists in variables and made another variable to connect the list of true and false values along with another variable that connected the infected and uninfected file objects.

```Wolfram
Length[infectedIMG]
70
infectedvalues=Table[True,Length[infected]];​​Length[uninfected]
70
uninfectedvalues=Table[False,Length[uninfected]];
```
