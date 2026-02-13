
# SVM(support vector machine) role in real life
Support Vector Machines are widely used in many real-world applications because of their strong theoretical foundation and good performance on both small and large datasets. Some key applications include:

---

- **Image and Handwriting Recognition:**  
    SVM is effective in recognizing patterns like handwritten digits or faces.
    
- **Text Classification and Spam Detection:**  
    Classifying emails as spam or not, and categorizing documents by topic.
    
- **Bioinformatics:**  
    For example, classifying proteins or genes based on biological data.
    
- **Medical Diagnosis:**  
    Detecting diseases from medical images or patient data.
    
- **Financial Forecasting:**  
    Predicting stock market trends or credit risk analysis.
    
- **Fault Detection in Engineering:**  
    Identifying faults or anomalies in machinery or systems.
    
---

SVM is favored for its ability to handle high-dimensional data and provide clear decision boundaries, even in complex problems.

---

### **1. What Are Support Vector Machines?**
Support Vector Machines (SVMs) are **supervised machine learning algorithms** used for both:

- **Classification**
    
- **Regression**

---

  ![[1.jpg]]

---

# SVM Geometry
- In geometry , a hyperplane is a subspace whose dimention is one less than that of its ambient space.A hyperplane seprates the space into two spaces.
- if a space is 3 dimensional then its hyperplane are the 2 dimentional planes
   ![[2.png]]
---

- if the space is 2 dimentional , its are the one dimentional lines.

   ![[3.jpg]]
---
- the **prependicular distance** between two objects is the distance from one to the other, measured along a line that is prependicular to one or both.
- the distance between a point ($x_0$,$y_0$) and a line parameterized by ax+by+c=0
- is equal to:

---

- ![[4.png]]
-  distance the points on the support vector from the hyperplane.
   f(x,w) = b+$w_1$ + $w_2$ 
   
   ### $\frac{|f(x,w)|}{\sqrt{x_1^2+x_2^2}}$
   
   this is simply
   
   $\sqrt{x_1^2+x_2^2}$ = $\|x\|$
---
**Support vector macine (SVM)** is one of the most popular algorithms in machine leraning. It is a powerful supervised algorithm used for classification and regression.

   why we care about maximizing that margin we hope by finding maximum margin in the train set the model is going to perform ok in the test set the model with the maximum margin is going to be the more robust model and its going to perform better.


   with that we can make predictions if I have a new observation here for classificationon the left hand side the black one and i use this model the model is going to tell me that the class is black.

---
MMC  is the hyperplane that among all seperating hyperplanes, find the one that makes the biggest gap (margin) between two classes.

![[5.jpg]]




black line is maximum margin hyperplane or maximum margin classifier the dashed lines are going to be our margins so the observation on the margins are support vectores.
finally distance between these **support vectores** are going to be our margins we are trying to maximize that margin.

---
## Why are we trying to maximize the gap in the train set?
if we find the maximum gap of the observation of the classes in the train set we hope that the model is going to do a decent job in the test set as well so thats why we are looking for the maximum gap.

---
  SVMs try to pick the most robust model (by finding $w^*$ and $b^*$) among all those that yield a correct classification . if we numericly define blue circle as +1 and green circle s as -1.
   

![[6.png]]

---


$\sum_{k=1}{w_kx_i,_k}$+b≥1  $\quad$  when $y_i$ =+1


$\sum_{k=1}{w_kx_i,_k}$+b≤-1 $\quad$   when $y_i$ =-1

imagine wx+b = 1 for blue one and for green one equals -1 and then if we want to calculate the prependicular distance between these two lines we know the equation so the distance of the blue margin from the green margin is going to be two and then we need to divide it norm of the weight matrix so divided by basiclly the magnitude of weight 

w.x + b = $c_1$

w.x + b = $c_2$

d= $\frac{|c_1 - c_2|}{\|w\|}$
 
Margin =  $\frac{2}{\|w\|}$


so  in order to maximmizing this gap this is equivalent to minimizing any function of w 

anything to the left should be greater than +1 and anything to the right should be lower than -1 


---
constraints 


($y_i\sum_{k=1}{w_kx_i,_k}$)+b≥1

$y_i(\sum_{k=1}{w_kx_i,_k}$)+b≤-1


 both of these constraints are going to be narrowed down to one constraint so overall we have two things we are maximizing the gap wich is equivalent to minimizing the functional  weight
 here is the optimization problem : 
 for mathematical convenience we do 1 divided by 2 because down the road if we take gradiants so these two is going to cancel out with the tow in the dinominator and its going to give us easier time to calculate .
 
 Minimize: $\frac{1}{2}\|w\|^2$

subject to : 

 $y_i$($w^Tx_i$+b) ≥ 1       $\quad$     for all i

---


- the constraint means that we are not allowing  for any kind of misclassification all the observation should be to the right side of the hyperplane the correct side if the hyperplane you are not allowing any kind of misclassification within the margin

- there is either an answer for this optimization problem or no if there is an answer we can come up with the closed form solution if there is no answer we have to use soft margin
---


##   Why should we go beyond the hard margin?
1. the data is non-seperable(overlap)
2. the data is noisy MMC is very sensitive to outliers
---
## Support vector classifier(SVC) Soft Margin
-  We extend the concept of a separating hyperplane in order to develope a hyperplane that almost seperates the classes , using a so_called soft margin
- the generalization of the maximal margin classifier usinf soft margin is known as SVC.

- it could be worthwile to misclassify a few training observations in order to do a better job in classifying the remaining observation.
---
in this case we cant find the MMC
if we find a hyperplane its gonna be sensitive its sensitive to observation close to the margins and gonna be less stable because its only support two vectores 
 
correct side of hyperplane and correct side of margin
observation blue with the black line  from the right is in the wrong side of the margin but on the correct side of hyperplane . for the red part is same.

there is no misclassification in this picture. however thera are couple of observation that are on the wrong side of the margin. but in the mmc we hav a restriction this is not allow .

---

 ![[7.jpg]]
 now our support vectores gonna be the observations on the dash and the observations within the margin in this picture 
 - **Solution:** we can extend the concept of a seprating hyperplane in order to develope a hyperplane that **almost** seperates the classes , using a so-called soft margin.

 - The generalization of the maximal margin classifier using soft margin is known as the support vector classifier(SVC).
 
 - It could be worthwile to misclassify a few training observations in order to do a better job in classifying the remaining observations.
 
 - wrong side of hyperplane brings us missclasification. if hyperplane is a classifier .

---
the idea here is that we are going to allow for these misclassifiaction as well .

if you are low for missclasification and then you are using soft margin .so what are the support vectores here ? I told you (:

so sometimes working with hard margin is almost infeasible.



Now lets see how does a computer find the soft margin problem for the SVC .

- Soft margin classification adds a penalty C to the objective function for observations in the training set that are misclassified . In essence , The SVM algorithm will choose a decision boundry that optimizes the trade-off between a wider margin and a lower total error penalty.


---

- **Slack Variable ξi** allow some observations to fall on the wrong side of the margin , but will penalized them by parameter C : **Cost of misclassification**



 $y_i$($w^Tx_i$+b) ≥ 1−ξi​  $\quad$ when $y_i$ = +1



 $y_i$($w^Tx_i$+b) ≤ -1+ξi​     $\quad$when $y_i$ = +1

so the constraints are going to be pretty much as the mmc but we are adding the slack variable so slack variable psi this allows for some observations to fall on the wrong side of the margin **not necessirily the hyperplane on the wrong side of the margin** but we'll penalize them by multiplying them to the penalty term we difine it  as the c cost of misclassification

---



so here's the optimization problem and as you pay attention this optimization problem is very much similar than compared to mmc but the difference part is here  about the psi and C.

min $\frac{1}{2}\|w\|^2$ + C$\sum_{i=1}{ξ_i}$


s.t 

$y_i$($w^Tx_i$+b) ≥ 1−ξi​        $\quad$          and   ξi​≥0

---


![[8.png]]
we have tow classes , class red and blue and the black dash is our hyperplane , red and blue dashes are our margin as you can see some obseravtion are on the wrong side of the hyperplane but it's not necessarily only tow points so lets say I have a red observation that is on the wrong side of the margin and for blue one but not in a picture up there imagine it yourself.
but we have some observation not only they are on the wrong side of the margin but they are on the wrong side of the hyperplane so we need to give them some slack as well for both .



---
so its ok to have these observation within the margin or missclassification they are on the right side of the hyperplane but not margin but we are gonna penalize them we are gonna panelize  those psi by multiplying them by positive cost function 

C$\sum_{i=1}{ξ_i}$


 and about the constraint it means ok you dont need to be exactly on the right side of the margin 


 $y_i$($w^Tx_i$+b) ≥ 1

Im  going to give you some slack 

$y_i$($w^Tx_i$+b) ≥ 1-ξi​        















 
