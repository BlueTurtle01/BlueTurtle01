My LinkedIn can be found here: https://www.linkedin.com/in/daniel-jones01/

# Timeline of skills
I will use this section to create a diary of my skills as a personal reflection of how far I have come on my coding journey.

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
