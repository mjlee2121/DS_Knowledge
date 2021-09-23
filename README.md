# DS_Knowledge
Deep study on ML algorithms and overall ML knowledge

## Contents
Entropy  
Hierarchical Clustering  
Decision Tree  


### Entropy

<pre>What is entropy</pre>
Simply put, entropy is measure of disorder.  
![alt text](https://user-images.githubusercontent.com/48074724/134520914-b9891103-a22d-41c7-ba6a-ad266e35b9e9.png)

In the formula, Pi is the frequentist probability of an element/class 'i' in our data. Let's say we have two classes, + and -. Then i will be either + or -.  
Now, if we have 30 + and 70 -, P+ will be 3/10 and P- will be 7/10. Plug that in the formula above, then you'll get this  
![alt text](https://user-images.githubusercontent.com/48074724/134523772-14e596a0-1104-4405-8bc0-968adc1345da.png)
The antropy is about 0.88. This considered a high entropy, a high level of disorder, and meaning a low level of purity. Entropy is measured between 0 and 1. (sometimes it can go over 1 but it means the same thing, high level of disorder).   

![alt text](https://user-images.githubusercontent.com/48074724/134523895-230e311e-1b39-44ec-beee-170239b68bd6.png)
x-axis measures the proportion of data points belonging to the positive class in each bubble and the y-axis measures their respective entropies. You can see the inverted U-shape.  
Entropy is lowest at the extremes, when the bubble either contains no positive instances or only positive instances. Entropy is highest in the middle when the bubbl is evenly split between positive and negative instances. Extreme disorder, because there is no majority.

**entropy is a measure of disorder or uncertainty and the goal of ML models and DS in general is to reduce uncertainty**

Now you know how to measure disorder. Next we need a metric to measure the <ins>reduction of this disorder in our target variable/class given additional informaton about it.</ins>

[!alt text](https://user-images.githubusercontent.com/48074724/134525302-acdf201b-cc59-4ca1-b1a9-b5fb9044c615.png)


<pre>Reference</pre>
https://towardsdatascience.com/entropy-how-decision-trees-make-decisions-2946b9c18c8
