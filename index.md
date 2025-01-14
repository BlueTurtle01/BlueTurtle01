My LinkedIn can be found here: https://www.linkedin.com/in/daniel-jones01/

# Timeline of skills
I will use this section to create a diary of my skills as a personal reflection of how far I have come on my coding journey.

## 22-23/09/2021 - PythonAnywhere/Linode and Flask deployment
1. Initially I tried to use Linode to deploy my Flask app but whilst I could get the server running and the demo app to work, once I uploaded my own - working - Flask app it would not fully work. Rather than giving up I have contacted their support team, and SO for help.
2. I then moved to PythonAnywhere, which I got working as expected but their file size limit has meant that I can't upload my Mask RCNN weights file for the end user to use for inference. I think this is a dead end but I have also contacted their support team to negotiate a solution.

NB. I think deploying this app over the internet is a much better solution than my initial Raspberry Pi/Jetson Nano plan (because of global chip shortages, and the updatability problem of dispersed machines), but RAM limitations of a lot of these Web Application services is also a concern. The cost of using a Web service is much cheaper for the end user too as they can use their own Desktop and a cheap webcam. This means I can deploy my medical based Flask App to more impoverished countries.

## 20-21/09/2021 - Flask and Jinja
Shifted a recent Mask R-CNN script I have been working on over to a web app using Flask. Initially I had planned to produce this script as a full product using a Jetson Nano / Raspberry Pi but the global silicon and chip shortage caused me to have to rethink. I am testing whether it will work as a SaaS platform and make use of the client's webcam.

Currently having problems getting the model detection to work: https://stackoverflow.com/questions/69269750/why-does-my-mask-r-cnn-model-not-work-in-flask but I am pleased with my ability to get OpenCV's videocapture working and the necessary Jinja templating style to display information next to the webcam feed to inform the user how to use the product.

## 15/09/2021 - Tensorboard and Hyper-parameter optimisation
Using a toy CIFAR example I used Tensorboard and the parallel view to choose optimal parameters. 512 units for the penultimate Dense layer produced the outright higher accuracy but 256 units produced multiple - very close to optimal - accuracies. Therefore, I chose to use 256 in the hope that I will have a more consistent model. 256 units often gave high accuracy regardless of the drop out rate and learning rate. This makes me think, in this setup, that the number of units was the most important factor.

## 14/09/2021 - Tensorboard + Functional Keras Models
1. Learnt about Tensorboard and how to implement it for Scalars and to visualise Hyper-parameter tuning.
2. Learnt more about the difference between the Sequential and Functional API for Keras and the benefits of Functional over Sequential.<br>

nb. I practiced this skill by changing the Sequential model that was in the tutorial for 1. into Functional.

## 08-09/09/2021 - Mask R-CNN
I have previous experience of Instance Segmentation but I am working on increasing my knowledge of these models by learning how to train the models to include new classes from images that I have annotated. Training is being done on my RTX 3090 which has allowed me to further improve my knowledge of TensorFlow GPU. Inference is currently being done on the same machine but I will run some tests soon to see if it can be run on a Raspberry Pi 4.

## 28-29/08/2021 - Python Efficiency recoder
Creating a script that will read in another script and change any inefficient code. The code considers a balance of speed and readability before making the changes. i.e. fstrings are slightly slower, but much more readable than long string concats, and hence in this case readability takes priority. I am a bit stuck with what to do with for loops that include a nested if/else statement because if this was rewritten as a list comprehension it may become unwieldy.

## 27/08/2021 - More OpenCV and potential Quadruped
1. Continued learning more OpenCV skills including Face and Object Detection. I make sure to comment my code well so it often takes longer. I also try to make my code modular so I can then reuse it in other projects later to help me work efficiently.
2. Improved my use of f-strings.
3. Started a new project that takes in a .py file and searches for inefficient loops and replaces them with list comprehension.


## 24/08/2021 - More OpenCV and cv.moveWindow()
1. I continued following some more OpenCV tutorials including Histogram equalisation and corner detection.
2. When displaying multiple windows, by default they often overlap. To allow easier comparison between the 3 versions of my input image I shifted the windows so they did not overlap. This is an nice time efficiency improvement. 

## 17/08/2021 - Project Euler & testing the speed of the sum() method
Today I joined Project Euler and have solved my first 4 problems. I learnt more about the set() datatype and how it can be used to easily sum the elements. This is an alternative to summing the elements in a list but achieves the same result. Interestingly after doing some tests I found that summing a list is 10x faster than summing the elements of a set.

``` Python
import time

numbs = []
for i in range(10000000):
    numbs.append(i**2)

numb_set = set()
for i in range(10000000):
    numb_set.add(i**2)

t0 = time.time()
sum(numbs)
t1 = time.time()
sum(numb_set)
t2 = time.time()

print("List Sum time: ", t1-t0) # 0.1671433448791504
print("Set Sum time: ", t2-t1) # 1.1795122623443604
```


## 15/08/2021 - MiniKMeans, cProfile
1. :heavy_check_mark: Used cProfile to profile my ColouringBook code. This allowed me to easily identify that the kmeans algorithm accounted for 90% of the total run time.
2. :heavy_check_mark: Learnt about MiniKMeans from the sklearn package and used this instead. Script now runs in ~1/9th of the time now.
3. :x: I tried to use the Potrace and PyPotrace packages to turn the .png outputs of the ColouringBook code into SVGs as the vector output of those is much cleaner than the bitmap of the .png. However, I could not get it to work. Given that PNG>SVG convertors are so freely available online I will stop trying to encorporate Potrace directly into my script and manual convert any files. This does mean it would not be a fully fledged autonomous script that can convert and share outputs to users. But, I will treat this current script as a MVP and consider trying again if the manual method becomes overwhelming - depending on demand for the product.


## 14/08/2021 - Normalisation & Optuna
1. :heavy_check_mark: Attempted to use the Optuna package to auto tune my LightGBM model but I got a few errors. I will return to this
2. :heavy_check_mark: Improved my performance on a tabular competition from 7.90739 to 7.90728 using normalisation of the features before passing the data to the model.

## 13/08/2021 - eli5
Started using the eli5 package to complete a permutation test on my LightGBM model that I have created for the August 2021 Kaggle Tabular competition. Inserted a custom loop that refits the model after removing the uninformative features as found by the permutation test rather than having to hard code the columns to be dropped. This will allow me to repurpose this code in future tabular settings where the column names may be different. This feature reduction reduced my RMSE from 7.90759 to 7.90739. Not a huge improvement, but at least my changes were useful.

## 10/08/2021 - LazyPredict
Started using the LazyPredict package to more easily run many classification and regression models on a data set in one method. The resulting table can then inform me of the best potential models going forward which I can more finely tune.

## 09/08/2021 - Icecream
Started using the Icecream package to create better print statements for debugging. I like Icecream as it allows me to leave the print statements in, but to disable them easily when the script is ready for production.


<!--
**BlueTurtle01/BlueTurtle01** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
