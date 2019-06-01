# review_test_classifier
This project predicts multi-class customer sentiment using text features from labelled customer reviews of restaurants from Yelp and Google.

Business understanding  
Predictive insights of customer-related metrics can help retail establishments make decisions that improve customer experience. However, the quality of customer predictions require text data that correctly expresses the heterogeneity and salient points of customer voices in natural language, as well as performance optimization across different algorithmic options.

Data understanding  
Customer reviews for this project were sourced from: 1) an aggregated subset of seven million Yelp customer reviews made available by Yelp as a set of downloadable JSON files, as well as 2) three hundred test customer reviews queried from the Places API of Google. For project purposes, the data was stored in, and queried from, a MongoDB database.

Data preparation 
Raw strings of customer reviews were extracted, processed and represented to models through a bag-of-words approach under a variety of alternate specifications using the Scikit-learn library. Specifications of parameters included, e.g.: 
    1) alternative tokenization strategies using: 
        a) only unigrams, b) only bigrams, and c) combined unigram and bigrams, 
    2) dimensionality reduction techniques that included ANOVA F-scores, 
    3) vectorization techniques using term-frequency inverse document frequency (TFIDF) algorithms. 
The prediction target comprised three classes representing positive, neutral and negative customer sentiment, which we created by aggregating customer-defined scores on a 1 to 5 basis, where out positive sentiment class = user score of 5, neutral sentiment class = score of 4, and negative sentiment class = scores of 1, 2, or 3.

Modeling  
The basic modelling task for this project was multi-class classification using text features. Models tested included logistic regression, support vector machines, and boosting ensemble models from the XG boost library.

Evaluation  
We evaluate model performance and associated parameter specifications using log loss and accuracy score metrics. The test set evaluation results for the initial top-performing model, a logistic regression classifier, was 0.75, and the log loss was 0.56. 

Deployment
We deployed the top performing model through a flask app for the purpose of basic user testing.
