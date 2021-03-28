# Gradient Boosting

In gradient boosting decision trees, we combine many weak learners to come up with one strong learner. The weak learners here are the individual decision trees.
All the trees are connected in series and each tree tries to minimize the error of the previous tree.

The weak learners are fit in such a way that each new learner fits into the residuals of the previous step so as the model improves. The final model adds up the result of each step and thus a stronger learner is eventually achieved.

![](RackMultipart20210328-4-1sob42i_html_e93d756c14df80ba.gif)
A loss function is used to detect the residuals. For instance, mean squared error (MSE) can be used for a regression task and logarithmic loss (log loss) can be used for classification tasks. It is worth noting that existing trees in the model do not change when a new tree is added. The added decision tree fits the residuals from the current model.

**_1. _** _Fit a simple linear regressor or decision tree on data (I have chosen decision tree in my code)__ ** ** _**_[call x as input and y as output]_**

_ **2. ** __Calculate error residuals. Actual target value, minus predicted target value _**_[e1= y - y\_predicted1]_**

_ **3. ** __Fit a new model on error residuals as target variable with same input variables _**_[call it e1\_predicted]_**

_ **4. ** __Add the predicted residuals to the previous predictions_
**_[y\_predicted2 = y\_predicted1 + e1\_predicted]_**

_ **5. ** __Fit another model on residuals that is still left. i.e. _**_[e2 = y - y\_predicted2] _**_and repeat steps 2 to 5 until it starts overfitting or the sum of residuals become constant. Overfitting can be controlled by consistently checking accuracy on validation data._

![](RackMultipart20210328-4-1sob42i_html_aef2a60becabbb97.gif)

