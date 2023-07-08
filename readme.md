# How Many Fingers?

The program classifies images by the number of fingers raised. Simply provide an image of a hand, run the program, and it'll tell you how many fingers are believed to be raised, 0 to 5.


## The Algorithm

This project was developed using Jetson Nano.  Its basis is a resnet18 model retrained on a dataset of 5000 pictures for 35 epochs. The resulting model was then exported into onnx and is used by Imagenet to determine the classification of the image. 

## Running this project

How to run:
1. Make sure the project has been downloaded correctly with hand-gestures.onnx and labels.txt downloaded onto your Jetson Nano
2. Instal git with "sudo apt install git all"
3. Clone the jetson-inference using "git clone --recursive https://github.com/dusty-nv/jetson-inference" or another method
4. Download the python packages using "sudo apt-get install libpython3-dev python3-numpy"
5. Change directories into the project with "cd How-Many-Fingers"
6. Set the NET and DATASET variables using "NET=models/hand-gestures" and "DATASET=data/hand-gestures" respectively
7. Put your image in the data/hand-gestures/ folder, beside labels.txt. Make sure the file format is compatible. 
8. Run "imagenet.py --model=$NET/hand-gestures.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/<Image Name>.jpg .jpg"
9. To see the output, scp the outputted file from the Jetson Nano onto your computer.

[View a video explanation here](https://youtu.be/LLDAfz8YT04)https://youtu.be/LLDAfz8YT04)
