# Yelp Reviews

Connie Xiao 

**An Unsupervised/Natural Language Processing Project**


### Abstract
--- 
The purpose for this project is  to build an algorithm that extracts useful information via user reviews to help Yelp optimize their platform. Since Yelp is widey used, I narrowed my focus scope on restaurants in Boston. By analyzing user reviews, this will provide insights about the restaurant business in Boston and their areas of strength and areas of weakness, thereby restaurant owners will know what areas they must improve on and areas where they are excelling.
The goal is that by knowing what the customer base wants, businesses can cater to those needs and boost customer satisfaction. With better customer satisfaction the more positive reviews they will leave for the businesses and thereby the more customers they can attract to boost revenues.

### Data
---
Data was collected from the Yelp website. The dataset came with 5 files: users, businesses, reviews, check-ins, and photos. For the purpose of this project, only the business and reviews files were used.

There are approximately over 100,000 business and 8,000,000 reviews in these two dataset files. After extracting only restaurants in Boston, I ended up with about 2,500 businesses and 500,000 reviews. Boston has a great food scene with lots of diverse cuisines and not to mention their fresh seafood!

Out of all of the reviews, 4 stars was the most frequently assigned rating for restaurants in Boston with 1 star being the least frequent. As for text review, the lower the rating the lengthier the review was and the higher the rating the shorter the review was.

### Results
---
There are 3 main components to this project.

The first step is to extract our data and clean it, so punctuations, whitespaces, numbers, and etc. are removed, and text was converted to lowercase.
The second step is to topic model. I was able to define 9 main topics that were mentioned in all of the reviews.
The third step was to build a classification model to identify positive sentiment reviews based off the 9 main topics that were discovered.
Algorithm
The main portion of this project was unsupervised learning with topic modeling. TF-IDF was used to vectorize the reviews and NMF was used to topic model. After fine tuning the hyperparameters, the end result gave me 9 distinct topics on user reviews about restaurants in Boston. Here are the discovered topics:

- Italian Cuisine

> restaurant, meal, boston, dinner, menu, wine, end, dish, best, pasta, italian, north, dessert, steak, delicious

- Asian Cuisine

> chicken, rice, sauce, salad, dish, noodle, soup, spicy, flavor, pork, beef, meat, thai, sushi, lunch

- Pizza

> pizza, slice, crust, cheese, best, delivery, topping, boston, thin, pie, sauce, order, new, sausage, north

- Experience

> great, service, staff, friendly, atmosphere, delicious, excellent, awesome, location, spot, selection, time, price, nice, fantastic

- Seafood

> lobster, roll, chowder, clam, oyster, seafood, fresh, boston, crab, sushi, best, fish, butter, delicious, hot

- Bars

> bar, drink, bartender, beer, night, friend, nice, cocktail, music, game, area, people, menu, cool, fun

- Service

> time, order, service, minute, table, customer, hour, waitress, bad, people, rude, manager, server, terrible, experience

- Sandwich/Breakfast

> sandwich, coffee, breakfast, lunch, egg, cheese, line, bread, day, delicious, brunch, shop, pastry, bagel, bacon

- Burgers

> burger, fry, beer, cheese, onion, potato, bun, bacon, tasty, medium, ring, veggie, mac, sweet, french

To further extend my analysis, I also topic modeled based off sentimental value, which you can see in my notebook.

The last part was a supervised learning classification. My target values was the sentimental value of positive or negative (positive : 4 stars <=, negative: 3 stars >), and my features includes the 9 topics.To evaluate the performance of my model, I used F1 score as my primary metric. I used two different classifiers, Logistic Regression as a baseline, and Random Forest. Overall, Random Forest gave me my best metrics:

F1 score: 0.7711927981995499

Precision: 0.7713856928464232

Recall: 0.771

Test Accuracy: 0.77125

Since we are focusing on how a restaurant business can provide better customer satisfcation, it might be wise to care more about our F1 and precision score. It is more harmful to depict a negative review as a positive review. Overall, the scores are pretty decent with a good balance. A feature importance chart was also generated to depict the most important topic which was Service. If restaurant owners want to boost customer satisfaction they should focus on providing excellent services.

### Tools
---
- Pandas
- Numpy
- Matplotlib
- Seaborn
- spaCy
- NLTK
- Wordcloud
- Scattertext
- Scikit-learn


