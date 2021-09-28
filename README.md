# MeLi_Data_Challange

Every day, Mercadolibre's shipping unit (MercadoEnvíos) delivers thousands of products across Latin America.

In order to provide customers with the best experience throughout the shipping process, it is critical to have accurate sales forecasts.

At the core of this business problem, lies the Data Challenge task: given the historical sales time-series for a subset of the martketplace's listings, we challenge you to predict how long will it take for a given item to run out of stock.


## Metric

Submissions will be scored using the Ranked Probability Score (RPS) metric.


## Task
Your task is to predict how long it will take for the inventory of a certain item to be sold completely. In inventory management theory this concept is known as inventory days.

In the evaluation set you will be given the item target stock, and you will have to provide a prediction for the number of days it will take to run out. Possible values range from 1 to 30. Rather than giving a point estimate, you are expected to provide a score for each the possible outcomes.

To put it simply, you need to answer the following question:

'What are the odds that the target stock will be sold out in one day?', 'What about in two days?' and so on until day 30.


## Submissions
Results should be submitted in a .gzip file. The compressed file should be a csv with 30 values per row, separated by commas, with no header. Each value in a row should represent the estimated probability of each possible outcome from 1 to 30.

Each row in the submission file is expected to provide a forecast for the corresponding row number in the evaluation set. (Yes, we will assume that your predictions are sorted in the same way as the original test dataset).

Keep in mind that the way you sort the probabilities within each row matters: the first value is expected to be the probability of running out of inventory in one day, the second value is the probability of running out on the second day and so on.

All values MUST lie on the interval [0,1], as they represent probabilities. Any submission violating this criteria will be considered invalid.

Moreover, all the values in one row should add up to one, as the possible outcomes 1-30 are mutually exclusive and exhaustive events for the target variable. If you submit a file where some rows violate this criteria, values within each row will be scaled to enforce this property.

Last but not least, all numbers in the submission file must have a maximum precision of 4 decimal places.

Together with the Challenge Data, we are providing a sample submission file to illustrate the expected format and make sure that you don’t miss a detail!
