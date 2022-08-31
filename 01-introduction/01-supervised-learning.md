## Supervised Learning [^1]

Given a dataset for housing prices, where the price is given as a function of the size in sq. feet of the house, you can sketch a straight line through the data as a way to predict prices for square footage that is not directly indicated by the sample data.

![[NBDraggedImage 01.png|600]]

However, some datasets are not well represented by a straight line.  So, in this example we can use a quadratic line (here shown in blue) to more closely match the data.  As a result, it gives a different prediction for the size in question (in this case, predicting a price of 200k instead of 150k for 750 sq. ft.).

This is known as a “supervised learning” problem, since we are given the “right answers,” from which we can derive our guesses.

This is also known as a “regression” problem, the goal of which is to predict continuous values; this example provides prices which are considered continuous as it can be any of a number of values along a number line..  This is in contrast to a "classification" problem where the dataset predicts discrete valued outputs; e.g. whether a tumor is malignant or not, or what type of cancer a given tumor is.

These examples illustrate prediciting an answer given a small number of features (e.g. "tumor size", "square footage", etc.) from which we estimate an answer ("price", "benign vs malignant") using regression or classification.

This course is about supervised learning, where we're given a dataset of "correct" answers and based on them be able to predict an answer.
