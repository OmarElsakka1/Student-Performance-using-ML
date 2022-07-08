# Problem definition and Motivation.

We are working on the student performance dataset provided by UCI. The dataset deals with students who are in secondary school; two Portuguese schools. And it states some attributes for some students like father and mother education in order to predict final exam grades. 

In our schooling systems nowadays, it’s really important to create some models that can predict student performance, to make some conclusions based on them. Now schools can predict if students will pass a course or not, and based on it, they can define how much extra support they have to give to students. And help them create a unique and custom plan for each student

Basically, the website states that the aim of this dataset is to predict the final exam grade(G3) given first-period exam(G1) and second-period exam (G2). and in addition to that, we could make a pretty good model predicting G3 without G1, nor G2; to help schools predict G3, even before the start of the semester.

We created models that might help schools to know their students better, based on their grades; schools will be able to determine mother and father education, in addition to parents' status; if they are apart or not, that might help them give special support for some students. We also provided a model to predict how many days students will be absent given all grades in different exams. That might be useful, if the sheet of attendance is somehow lost, and they might need to estimate how many days each student came to school.

Moreover, we did great exploratory data analysis, to examine some interesting questions; for example, we did an EDA on interesting features related to students who failed at least once, and many many more.


And at the end of our project, we aim to give some tips to parents, for how to take care of their children, tips for getting high grades, all of these tips will be based on detailed analysis and hypothesis testing, they can examine themselves.

# Dataset

### Description
The data set is in tabular form with many features regarding some students in secondary education of two Portuguese schools. And it records their performance in two different subjects; Mathematics (mat) and Portuguese language (por). 

The data has no missing values at all. In addition, it was correctly encoded by an ordinal encoder. Although, we made more cleaning which we will explain in the cleaning section.
### Models
We did many models to see which one will perform better. We firstly did our modeling on our raw data frame, then tried only columns produced by PCA, and tried data frame after dropping all uncorrelated columns.


Models for predicting G3, given G1, and G2.

We used many models here
1-Linear regression

2-Ridge regression

3-Lasso regression

4-Elastic regression

5-KNN regressor

6-Tree regressor

7-XGBoost

8-Gradient boosting

9-Stacked models

![image](https://user-images.githubusercontent.com/69484554/147394230-046fcf51-e97c-4545-9be8-01f6770e80e6.png)


![image](https://user-images.githubusercontent.com/69484554/147394232-3fe7b1c9-3877-4532-a906-85c6c461392b.png)


### Models for predicting G3 not given G1, nor G2

Here we tried to predict the final grade, but we didn’t include G1, not G2 column. We used multiple algorithms here. And here’s the summary


![image](https://user-images.githubusercontent.com/69484554/147394237-6ad90b32-3534-4299-ac18-3d9924fa9b37.png)

![image](https://user-images.githubusercontent.com/69484554/147394240-383ca67c-9fa1-4baf-ae12-7aacf50deb98.png)


We also find here that gradient boosting, and XGBoost are the best ones, with RMSE for training set 2.55 and test set 3.56 for gradient boosting, and for XGBoost, it got 3.49 for testing sample.

It’s a little worse than the last model. But sacrificed G1 and G2 columns which are the most important columns.

### Classification

We tried to discretize our target variable and then classify it.
Final grade between 0-9 	Bad
Final grade between 10-14 	Good
Final grade between 15-20 	Very good

We tried many classification algorithms including

1-SVC

2-Naive bayes

3-Knn classifier

4-Decision tree classifier

5-Random forest

6-Gradient boosting classifier

![image](https://user-images.githubusercontent.com/69484554/147394253-3d96e25d-c98d-4d36-9b5f-a11f72b9e9ad.png)

![image](https://user-images.githubusercontent.com/69484554/147394256-cb92c5a8-aac5-402d-b8e2-671efdda5266.png)

Also, we used this interesting  data to predict extra information about parent state, mother education, father education, and absence of students
For parent state:
1.1) we used decision tree that gives a score 86.6%
1.2) Meanwhile KNN classifier that gives a score 88.5%
For mother education:
 2.1) decision tree bring a score of 48.8%
For father education:
3.1) decision tree gives a score of 31.1%
For absence of student:
4.1) using decision regressor, we got root mean square error 5.5
         4.2) using grid search (elastic net), we got root mean square error 5.45



### Conclusion
  Helping schools to know what is better for their students, was a major challenge for us in that research. But we also focused on tips for parents that will help them raise a good student. But we strongly believe that grades are not everything in life; even a bad student at grades is certainly intelligent in some other field.

In conclusion, here are our final results found by our EDA.

1-There is no major difference between being a male and female in education. And it’s all due to effort.

2-As the age increase, the performance of students decreases

3-For the student who failed at least once, their average grades is more inverse proportional to the number of failures.

4-We found out that students who have their parents apart have the same average grade same as a student who has their parents together

5-We found that students having one of their parents as a teacher, are having fewer failures, and they fail at most once. 

6-If school is near to their hometown, it’s much better for students, it helps them to get higher grades.

6-No major difference between living in urban or rural areas at all.

7-We found as parents get higher education, their parents get higher grades on average.

7-Women are better guardians than men regarding their child’s grades.

8-Family size does not affect student performance

9-Students might need to study on aver for more than 2.5 hours to get grades greater than 19 out of 20, but it’s also noted it’s based on their abilities, some might need less than 2 hours, and up to five hours to get the same grade

10-It’s pretty clear that family support is important for student spirit.

11-Half of the students who failed once are having extra activities. So it might put some extra burden on students.

12-Grades are affected by romantic relationships, in negative correlation.

13-Alcohol consumption decreases student performance. 

14-Wanting to go to high school is a pretty good motivation for students to get high school.

  ### final tips for parent
1-Don’t make your child have alcohol
2-Don’t make your child have romantic relationships
3-It’s better to have both parents as teachers, but the value is more important, so if parents are more familiar with their child's education system that shall help their child a lot.
4-It’s much better to register your child to a nearby school
5-If parents are having a great family issue, they don’t have to worry about their child's performance in school, as it’s not affected by their divorce.
6-It’s a pretty good motivation to motivate your child to go to high school.
7-To get your child to get high grades, you need to understand them, you need to make a custom number of hours to study to satisfy his/her needs


  ### limitations
 1-The data set was concentrated on Portuguese schools, we assume our models will have different values for test error when used with different cultures.

2-Columns were encoded in ordinal. We were hoping we did it ourselves, to see which is better for our models. And I can not know if any other encoders will behave differently or not.

 3-Website didn’t provide which student they collected their data. And we wanted to make sure how randomly students were selected. And what criterion did they use, was it stratified or what? Does the percentage of each category of students in our dataset is really representative of the real distribution? There was not enough information about that. And that might affect our model in different regions
 
 More details in notebook and report
