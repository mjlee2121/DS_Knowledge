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

We simply subtract the entropy of Y given X from the entropy of just Y to calculate the reduction of uncertainty about Y given an additional piece of information X about Y. **This is called Information Gain**. The greater the reduction in this unertainty, the more information is gained about Y from X.  

Let's bring a Credit Rating and Liability example and bring all of it together how DT uses entropy and information gain to decide what feature to split their nodes on as they are being traied on a dataset.  

<pre>Contingency Table</pre>
![alt text](https://user-images.githubusercontent.com/48074724/134529123-5b5c6e74-5a9d-4135-a2d0-f81f125bfa4d.png)  

Our target variable is Liability which can take 'Normal' and 'High' and we only have one feature called Credit Rating which can take on 'Excellent','Good', and 'Poor'.  
Let's use the contingency table to calculate the entropy of our target variable by itself and then calclate entropy of our target variable given additional information about the feature, CR. This will allow me to calculate how much additional information does 'CR' provide for my target variable 'Liability'.  

![alt text](https://user-images.githubusercontent.com/48074724/134529836-1f5e3e5e-bf9f-4d18-8b7b-cb7e22311694.png)  
The entropy is 1, at maximum disorder due to the even split between class label 'Normal' and 'High'.  
Our next step is to calculate the entropy of our target variable Liability given additional information about CR. For this we'll calculate the entropy for Liability for each value of CR and add them using a weighted average of the proportion of observations that end up in each value. 


![alt text](https://user-images.githubusercontent.com/48074724/134529955-d868ac1e-9bb3-4b43-837f-6e4647e0cf6a.png)  
Now we can compute the Information Gain on Liability from CR to see how informative this feature is.  

![alt text](https://user-images.githubusercontent.com/48074724/134530440-674a3f77-5a98-49f5-9ded-56f86c120d8d.png)  
Knowing the CR helped us reduce the uncertainty around our target variable, Liability. That's what a good feature is supposed to do; provide us information about our target variable.  
This is exactly how and why DT uses entropy and information gain to determine which feature to split their nodes on to get closer to predicting the target variable with each split and also to determine when to stop splitting the tree.  



<pre>Reference</pre>
https://towardsdatascience.com/entropy-how-decision-trees-make-decisions-2946b9c18c8
