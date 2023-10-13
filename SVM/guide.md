SVM(Support vector machine)

SVM works best when the dataset is small and complex. It is usually advisable to first use logistic regression and see how does it performs, if it fails to give a good accuracy you can go for SVM without any kernel 

Used for both classification and regression and is built on top of logistic regression.


Types of Support Vector Machine Algorithms

1. Linear SVM
When the data is perfectly linearly separable only then we can use Linear SVM. Perfectly linearly separable means that the data points can be classified into 2 classes by using a single straight line(if 2D).

2. Non-Linear SVM
When the data is not linearly separable then we can use Non-Linear SVM, which means when the data points cannot be separated into 2 classes by using a straight line (if 2D) then we use some advanced techniques like kernel tricks to classify them. In most real-world applications we do not find linearly separable datapoints hence we use kernel trick to solve them.

  <img width="381" alt="Screenshot 2023-10-12 at 3 23 04 PM" src="https://github.com/zerouchi/Machine-Learning/assets/79967043/0736e958-9937-4db9-8253-e132b170a64e">
 
￼
Best fit line / hyperplane has maximum Distance between their marginal plane

￼<img width="449" alt="Screenshot 2023-10-12 at 3 58 41 PM" src="https://github.com/zerouchi/Machine-Learning/assets/79967043/c13d1f5d-6668-4073-bb06-449bb138f513">
![Pasted Graphic](https://github.com/zerouchi/Machine-Learning/assets/79967043/ee95c562-9433-4732-a00a-4ebeb20f83a8)

￼
Maximising marginal plane distance
￼
![Pasted Graphic 1](https://github.com/zerouchi/Machine-Learning/assets/79967043/7635ed69-a0d2-467b-8f24-2351a9c06481)
￼
![Pasted Graphic 2](https://github.com/zerouchi/Machine-Learning/assets/79967043/09f13e7d-8365-4321-bfe8-ae83037ed94f)
![Pasted Graphic 3](https://github.com/zerouchi/Machine-Learning/assets/79967043/1e32d41e-33fa-4e13-a4cb-811727f088fe)
￼
the most interesting feature of SVM is that it can even work with a non-linear dataset and for this, we use “Kernel Trick” which makes it easier to classifies the points. Suppose we have a dataset like this:


Here we see we cannot draw a single line or say hyperplane which can classify the points correctly. So what we do is try converting this lower dimension space to a higher dimension space using some quadratic functions which will allow us to find a decision boundary that clearly divides the data points. These functions which help us do this are called Kernels and which kernel to use is purely determined by hyperparameter tuning.

![1403824](https://github.com/zerouchi/Machine-Learning/assets/79967043/ea8c5939-5515-4172-82fa-b5d3bd0e364a)
￼

