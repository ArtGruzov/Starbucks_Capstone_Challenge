# Starbucks_Capstone_Challenge

### Project Overview
This is my Capstone Udacity Project. Here For this project, I want to build an ML model, with the help of which it will be possible to make forecasts which of the clients will complete the offer and who is not. Such a model will improve the quality of offers for each of the demographic groups. 

### Description of the files 
- <b>Starbucks_Capstone_notebook.ipynb:</b> Notebook with all data cleaning, preparing, analysing and model training/testing

- <b>profile.json::</b> Rewards program users (17000 users x 5 fields) <br> Columns description:
  - <i>gender:</i> (categorical) M, F, O, or null
  - <i>age:</i> (numeric) missing value encoded as 118
  - <i>id:</i> (string/hash)
  - <i>became_member_on:</i> (date) format YYYYMMDD
  - <i>income:</i> (numeric)
  
- <b>portfolio.json:</b> Offers sent during 30-day test period (10 offers x 6 fields) <br> Columns description:
  - <i>reward:</i>  (numeric) money awarded for the amount spent
  - <i>channels:</i> (list) web, email, mobile, social
  - <i>difficulty:</i> (numeric) money required to be spent to receive reward
  - <i>duration:</i> (numeric) time for offer to be open, in days
  - <i>offer_type:</i> (string) bogo, discount, informational
  - <i>id:</i> (string/hash)
  
- <b>transcript.json:</b> Event log (306648 events x 4 fields) <br> Columns description:
  - <i>person:</i>  (string/hash)
  - <i>event:</i>  (string) offer received, offer viewed, transaction, offer completed
  - <i>value:</i>  (dictionary) different values depending on event type
    - <i>offer id:</i>  (string/hash) not associated with any "transaction"
    - <i>amount:</i>  (numeric) money awarded for the amount spent
    - <i>reward:</i>  (numeric) money gained from "offer completed"
  - <i>time:</i>  time: (numeric) hours after start of test
  
 ### Summary
A comprehensive solution to the problem consists in combining all the tables so that each row is a potentially interesting event for us. In this case, the line should contain all potentially useful information about the user and the offeror. This part of the project was the most difficult since the association of tables with the necessary images in this particular case was not trivial. Then there were quite standard steps: creating dummies columns, scaling, model selection and training. 
 
F1 score gives 80%

### Justification & Improvement
The main idea of this project was to create a useful tool, which can be used by another script to send customers offers which they almost certainly will like. The model now looks good and I think that we actually can use it for a test.

However, these results still don't look like the final tool, I think. Actually, there're still a lot of things that can be improved, I think. First of all, there's always some space for experiments, maybe we can try some other ML models, maybe we can experiment with parameters of the model to do it better, maybe we can try other methods of preparing our data. For example, we can divide people into groups by income, age and etc. I think that there's some probability that all these experiments, mentioned earlier can make our results better.

One more thing about further improvement. I think that we can improve this model if we will detect how close the customer was to completion of the offer. For example, we can have some group of people who really were interested in an offer, but for some reasons, they did not have enough time to complete it. Our current model doesn't check such things for now. I think that such improvement can make this model better, but, of course, it's not for sure, so there's also some space for experiments.
