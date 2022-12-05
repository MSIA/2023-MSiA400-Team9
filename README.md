# 2023-MSiA400-Team9

Project topic: 
The exploration of certain products that are unpopular/ only sell when discounted.

Project description:
Design and build a model that predicts the discount rate needed on specific products for maximizing profit, 
or a model that classifies products as more desirable/ less desirable. 

Weekly update:

Update, w/o 12/2:
This week, we made some pretty big changes:
   > Our "discount" is now the mean percentage per SKU
   > We are now using ~1.5 million rows of data from SKU, such as color, brand, department, etc. to predict the expected percentage discount for these products
We have also done a lot of new cleaning / feature engineering:
   > Grouping colors
   > Creating quintiles to better identify brands / reduce length of dummy variables
We are currently in the process of wrapping up modeling, and will begin preparing our report and presentation.

Our plan for the next few weeks:
12/2 - wrap up modeling
12/9 - submit project

Update, w/o 11/11:
This week, we wrapped up EDA. We will be using factors from the transactions table and the sku + store table, 
with the target variable being the new binary variable we created (the one that compares original price and retail price, 
with situations where orgprice > retail = 1). We have fetched the data from the server, loaded it into an ipynb, 
and saved it as a csv (because querying from the server takes hours each time).
More feature engineering might be necessary, dependent upon the model types we choose, as well as performance. We aim to start building preliminary classification models next week.

Our plan for the next few weeks:
11/11 - wrap up EDA, continue feature engineering, connect server data to ipynb
11/18 - wrap up feature engineering, begin building models
11/25 - begin model assessment / selection

Update, w/o 11/4:
This week, we continued EDA in search of potentials variables / tables to used for our model. 
At the moment, we expect to use data from the transactions table and the sku + store table. 
We are interested in the sales of items at discount, so we have created a new binary variable that compares original 
price and retail price, with situations where orgprice > retail = 1. 
There were some cases in which orgprice = 0, ~1%, which didn't make much sense, so we will do some more EDA to see if we could find a reason or solution.
We expect to continue EDA and feature engineering into next week, and hopefully start some preliminary modeling. 
At the moment, with our binary variable, we are considering a classification model where we aim to predict whether or not 
a product needs to go on discount for it to sell.

Our plan for the next few weeks:
11/4 - continue EDA, begin feature engineering
11/11 - wrap up EDA, wrap up feature engineering, begin building model
11/18 - begin (hopefully) model assessment / selection

Update, w/o 10/28:
Our data should now be just about ready for use. 
We have a few small issues with the transact table (unknown columns, etc.), but that shouldn't be too hard to overcome. 
If we don't need a column, we can just not include it in the model recipe. We will also likely have to do a decent amount of feature engineering.
We have also decided to focus on the third business problem we brainstormed last week, the one on certain products being unpopular / only selling when discounted. 
We think it would be interesting to build a model that predicts the discount rate needed on specific products 
for maximizing profit, or perhaps a model that classifies products as more desirable / less desirable. 
Does this sound like a good question or model to pursue?

We have also figured out how to run SQL commands from python to get data from the server, so EDA is in process. 
A few things we have discovered so far:
   + mean transaction cost is 24.62, which seems a little low for an "upscale" department store
   
Our plan for the next few weeks:
10/28 - continue cleaning / tidying data, explore / finalize business questions, begin EDA
11/4 - continue EDA
11/11 - wrap up EDA, begin building model

Update, w/o 10/21:
This week, we finished reading in the trnsact table. We are still considering appending those rows in the SKU table with two colors, 
but will first move forward with considering business questions to investigate. A few questions we might explore:
   + Can we anticipate demand in order to optimize stocking?
   + Are there certain products that are often sold together?
   + Are there certain products that are unpopular / only sell when discounted?
   + Can we find best performing stores and replicate their performance?
   + Can we optimize inventory to better represent the proportions of what people buy?
   
Our plan for the next few weeks:
10/21 - complete reading in tables, begin brainstorming business questions
10/28 - continue cleaning / tidying data, explore / finalize business questions
11/4 - begin EDA
11/11 - continue EDA

Update, w/o 10/10:
This week, we began the process of reading in tables to the PostgreSQL server. At the moment, we have 
somewhat successfully loaded most tables (deptinfo, skuinfo, sksinfo, and strinfo). We ran into some issues with the SKU table, 
due to some rows/products having two colors separated by a comma. This resulted in an extra column in those rows when delimiting with commas, 
but we were able to overcome this by first excluding those rows. In the future, we might fix those rows (by removing the comma and space separating each of the two colors, ex: “red, blue” becomes “redblue”) and then appending them to the current tables. We expect to finish reading in that last transactions (trnsact) table in the next few days.

Our plan for the next few weeks:
10/14 - begin reading in tables, set up GitHub repository
10/ 21 - complete reading in tables, continue cleaning data
10/28 - continue cleaning / tidying data
11/4 - complete cleaning / tidying data, begin EDA



