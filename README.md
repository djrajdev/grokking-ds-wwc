## Grokking Data Science with Women Who Code
@Author: DJ Rajdev  
@LastUpdate: Sept 3, 2019  
@Purpose: slides for WWC presentation and supporting code stubs  

### How do I make the most of this project?
- Check the sources in pdf, a lot of them have detailed tutorials  
- Refer to Speaker notes section below for some more talking points around the slides  
- Most code is snippet form or uses academic sample data, I encourage you to expand it with real world data and send me a PR if you do  

### Questions and staying in touch
I can be reached by
- Twitter: @DivjyotiRajdev  
- Email: dj@djrajdev.com  
- **Biweekly Data Science Meetup** [link](https://www.meetup.com/DSCaseStudies/)
- **Monthly Data Viz Meetup** [link](https://www.meetup.com/SVDataVizMeetup/)

### Video walkthrough
[Link](https://www.youtube.com/watch?v=7Dm8-cCNRHo). Some of the above topics may be covered in a different but related presentation as a Data Scientist at TIBCO Software.

### Speaker notes:
#### Should I even solve it?
- **black swans:** events that don’t have enough data to be predictable. Eg natural calamities. Recent bitcoin surge was a self-fulfilling prophecy  
- **right problem:** customer is unhappy about service disruptions due to failures you can have 2 solutions. 1) fix the product to have lower failures 2) create backups to reduce disruption. #2 is better but doesn't need data science  
- **ideal solution:** how will it be used? real time vs offline, dashboard vs spreadsheet vs script, core or edge. This affects model selection  
- **prediction or insight:** what are you trying to find? eg. if stock market up or down? by how much? to what accuracy?  
- **representative data:** if time dependent target, do you have time in dataset? correctness from domain perspective (ph >14)? check to ensure no bias in collection.  
- **goal post for success:** if your goal is to increase conversion rate, for how long? 2 weeks, 30days, 6months? 

#### Data or dirt?
- **data summary:** look through measures like %missing, invariant, extreme variation, entropy, (visual) distribution, mean median  
- **data relationships:** remove redundant columns, use this for feature selection. 
- **featurization:** transformations, scaling, one-hot encoding, frequency encoding, aggregation (eg. amazon collects data as 1 row per transactions but the models usually work on 1 row per customer)  
- **outliers:** filter them? what about fraud.  
- **imputing missing values:** choose the unbiased estimator (often median, but also prev value, next value, knn based imputation)  
- **decompose time series:** pollution example. How would you forecast given series? or find trend? or correlate.   

#### Is the model good enough?
- **baseline model:** accuracy vs interpretation. Interpretation focus post GDPR. What is the cost of incorrect / large error prediction  
- **error metric:** default is mse. if your estimator is better suited by median vs mean, mae is better. similarly for categorical consider precision, recall etc.  
- **sampling:** prototype on 5% for big data, oversample for unbalanced class, 0/1 sampling (eg only customers who bought pants)   
- **algo family:** many techniques to accomplish the same result. eg customer segmentation using clustering or multiclass classification. neural nets have holes in param space RF does not  
- **model breaking point:** LM assumes linear dependence. RF doesn’t work with sparse data. centering + scaling for svm  
- **domain methods:** Often specialized of a particular type of problem that's not trivially solvavble by the usual ensemble / NN methods. eg. A/B test for experimentation, graph methods, linear programming multi constraint optimization, autoencoders for unsupervised anomaly  
- **stats intuition:** CNN used for image classification. for detecting damage either classify but easier to use sobel filter (intermediate step in CNN). stats.stackexchange 'intuitive' tag.  

#### What is driving my model?  
- **var imp:** relative influence look for bias  
- **var imp with noise:** where does the significance drop off  
- **cheating algo:** date the most imp feature? 90% variation by one feature?  
- **time split:** random sampling looks into the future  
- **local interpretation:** fit weak learners to understand behavior at row level. H2O, k-lime example  
- **sensitivity analysis:** for each imp variable how much perturbation is too much?  

#### What's the long term plan?
- **accessible:** how will you distribute your model or results? scheduled job & write to table, api & real time query, streaming analytics  
- **testing:** similar to software engineering track functional, security, specially for APIs  
- **rule based:** most fraud models begin with rules that have been derived using complex ML models. this is due to ease of deployment, speed. Same for control charts  
- **right audience:** technical deepdive & filters vs OKRs for executives  
- **model retrain:** based on residual drift for machine data, seasonally for human data  
- **side effects:** boosting sale of chanel noir might draw customers away from chanel no 5. cannibalisation and survival analysis  
