# Directing-Customers-to-Subscription-Products-through-App-Behavior-Analysis
### ==> A Fintech Case Study
![animated-globe](https://user-images.githubusercontent.com/47801267/71056411-298ea980-217f-11ea-9c57-751c845c5388.gif)
In today's market many companies have a mobile presence. Often, these companies provide free products/services in their mobile apps in an attempt to transition their customers to a paid membership. Some examples of paid products, which originate from free ones, are ***YouTube Red, Pandora Premium, Audible Subscription, YouTube Premium***, and You Need a Budget. Since marketing efforts are never free, these companies need to know exactly who to target with offers and promotions.
- **Market:** The target audience is customers who use a company's free products. In this case study, this refers to users who installed (and used) the companies free mobile app.
- **Product:** The paid memberships often provide enhanced versions of the free products already given for free, alongside new features. For example, ***`Youtube Red allows you to leave the app while still listening to a video.`***
- **Goal:** The objective of this model is to predict which users will not subscribe to the paid membership, so that greater marketing efforts can go into trying to ***`convert`*** them to paid users.
![User-Behavior](https://user-images.githubusercontent.com/47801267/71056513-8b4f1380-217f-11ea-8ee7-77d3dd18b336.gif)
---
###  Business Challenge
- In this Case Study we will be working for a fintech company that wants to provide its customers with a paid mobile app subscription that will allow them to track all of their finances in one place. To attract customers, the company releases a free version of their app with some of the main features unlocked.
- The company has tasked you to identify which users will mostly likely NOT enroll in paid products, so that additional offers can be given to them. Because of the costs of these offers, the company does not want to offer them to everybody, especially customers who were going to enroll anyways.
![dd3899043b8f39dd7cbb301db09a19b3](https://user-images.githubusercontent.com/47801267/71056559-bf2a3900-217f-11ea-8bc6-713a2954e7d0.gif)
----
### DATA
- By working for the company. We have access to each customer's app behavior data. This data allows us to see the date & time of app installation, as well as the features the users engaged with within the app. App behavior is characterized as the list of app screens the user looked at, and whether the user played the financial mini-games available.
- The app usage data is only from the user's first day in the app. This limitation exists because users can enjoy a 24-hour free trial of the premium features, and the company wants to target them with new offers shortly after the trail is over.
- The Data for this project is from manufacturing fields based on trends found in real world case studies. The fields  describe what companies usually track from their users.
**Data Description**
- **User** : this is Unique id of each perticuter user of app
- **first_open** : this is the date/month/year, time the user frist time open the app
- **dayofweek** : this shows the day out of 7 days a week an user join the app where 0:Sunday & 6:Saturday
- **hour** : This is outoff 24 hour of day the user 1st open the app
- **age** : This is simply the age of the user
- **screen_list** : This describe the every single screen name the user visited in that 1st 24-hour (screen name seperated by comma)
- **numscreens** : The Number of screen the user visited in 1st 24 hour
- **minigame** : The app has minigame feature, this shows whether the player played any minigame of Not (1:Played, 0: Not Played)
- **liked** : There are like button for each feature in the app, shows whether the user cliked any like button of any feature in app or NOT (1: click like button, 0: Not clicked)
- **used_premium_feature** : This shows whether the user used any premium feature (that is for free in 1st 24 hour) or not in 1st 24 hour (1: used, 0: not used)
- **enrolled** : This is target that shows whether the user enrolled to premium after the free trial (1: enrolled, 0: not enrolled)
- **enrolled_date** : date & time of enrollment to premium product if they enrolled to premium
![agifcolossaltd2opt](https://user-images.githubusercontent.com/47801267/71056602-e2ed7f00-217f-11ea-9eb2-99c7e7238597.gif)
---
### Libraries & Data-sets
![image](https://user-images.githubusercontent.com/47801267/71056944-082ebd00-2181-11ea-8bef-d9032016fd2c.png)
![image](https://user-images.githubusercontent.com/47801267/71057001-36140180-2181-11ea-9dd5-c7c45405ff87.png)
![image](https://user-images.githubusercontent.com/47801267/71057032-4f1cb280-2181-11ea-9ade-f66a1323a68e.png)
![image](https://user-images.githubusercontent.com/47801267/71057047-580d8400-2181-11ea-8d4e-0281a7de6307.png)
Observations:
- Most of the users join app during weekends
- Most of the users 1st open the app around 15 that is around 3PM
- Most of users are aged around 30 Years
- Most of users visited around 20 screens of app
- Not many users played any minigames
- Not many users press the like button
- Not many user used premium feature in 1st 24 hours
![image](https://user-images.githubusercontent.com/47801267/71057087-812e1480-2181-11ea-9c4b-29a0bb76785b.png)
![image](https://user-images.githubusercontent.com/47801267/71058534-2a770980-2186-11ea-8176-13682cc17e3e.png)
Observarions:
- dayofweek is least positively correlated & says that if you join the app in day 0(sunday) then their is most likely to get enrolled to the premium features
- Hour is negatively correlated with target variable shows the earlier the hour(in night) the most likely to get enrolled
- age is also negatively correlated reflects that the younger users are most likely to get enrolled
- Numscreen is positively correlated with target shows that more the no. of screen user visits more chances of getting enrolled
- minigame also shows that more the minigame user play more chances of getting enrolled
- liked is very least negative which does not have much impact in target
- interestingly used_premium_feature is negatively correlated with response meaning that if user used the premium feature in 1st 24 hour that he/she might not enroll after the trial version of premium features
![image](https://user-images.githubusercontent.com/47801267/71057146-b9355780-2181-11ea-8c56-ccd7690401ea.png)
![image](https://user-images.githubusercontent.com/47801267/71057159-c18d9280-2181-11ea-8350-ca313c6edb96.png)
All the independent features are having very less correlation among themselves, so their is very less chance of multicollinearity problem
---
### Feature Engineering - Response variable
![image](https://user-images.githubusercontent.com/47801267/71057221-fac60280-2181-11ea-9452-a9a1568170d7.png)
![image](https://user-images.githubusercontent.com/47801267/71057235-0b767880-2182-11ea-8c6f-789422a10460.png)
![image](https://user-images.githubusercontent.com/47801267/71057245-1af5c180-2182-11ea-9fe1-f0597881624d.png)
- Here we observe that most of users enrolled in 1st 2000 Hour but their might be case that most enrollment is in 1st 100 or 500 hours, lets zoom the plot
![image](https://user-images.githubusercontent.com/47801267/71057284-35c83600-2182-11ea-8982-5449934c8ecf.png)
![image](https://user-images.githubusercontent.com/47801267/71057298-3f519e00-2182-11ea-9a74-f59901d4c9a7.png)
- Here we observe that most of users enrolled in 1st 100 Hour but let's zoom the plot again

![image](https://user-images.githubusercontent.com/47801267/71057351-69a35b80-2182-11ea-93ad-72c35dc48a9e.png)
![image](https://user-images.githubusercontent.com/47801267/71057367-72942d00-2182-11ea-865d-0e66006c2ba0.png)
- Here we observe that most of users enrolled in 1st 10 Hour but let's zoom the plot a bit more

![image](https://user-images.githubusercontent.com/47801267/71057392-88a1ed80-2182-11ea-9605-4addbe05096c.png)
![image](https://user-images.githubusercontent.com/47801267/71057399-8cce0b00-2182-11ea-91fc-224d12f69271.png)
- Here we observe that most of users enrolled in 1st 1 Hour but let's zoom the plot one more time.

![image](https://user-images.githubusercontent.com/47801267/71057419-9eafae00-2182-11ea-8b18-508a6ae10636.png)
![image](https://user-images.githubusercontent.com/47801267/71057426-a7a07f80-2182-11ea-9414-1c9fc3ae7d1d.png)
- Here we observe that most of users enrolled in 1st 10% of hour that is in 1st 6 minutes but let's zoom again

![image](https://user-images.githubusercontent.com/47801267/71057449-bd15a980-2182-11ea-8180-db3d5889ffd6.png)
![image](https://user-images.githubusercontent.com/47801267/71057454-c141c700-2182-11ea-88c3-8bfc3bfdcfbc.png)
- ***Here we conclude that most of users (more that 20000 out-off total 50000 users) do not used the 1st 24 hour premium free trial & infact they direcly jumped to the premium at the time of they 1st open the app***
- We choose cut-off as 48 hours that is whoever difference is less than 48 is classified as enrolled else not

![image](https://user-images.githubusercontent.com/47801267/71057521-f817dd00-2182-11ea-8118-72068fb92204.png)

---
### Feature Engineering - Independent variables
![image](https://user-images.githubusercontent.com/47801267/71057561-1c73b980-2183-11ea-9371-a2164f8c0924.png)
- **`Funnels : Funnels are group of screens that belong to same set There are many screens that are correlated with eachother, and
we don''t want correlated screens coz it's not good idea for the model`**
![image](https://user-images.githubusercontent.com/47801267/71057618-4dec8500-2183-11ea-84f6-02ae59b92788.png)
![image](https://user-images.githubusercontent.com/47801267/71057660-76747f00-2183-11ea-90cb-c2d01e7e7c0f.png)
---
### Data Preprocessing & Feature Scaling
![image](https://user-images.githubusercontent.com/47801267/71057671-84c29b00-2183-11ea-8d24-04ba7b77fc77.png)
![image](https://user-images.githubusercontent.com/47801267/71057732-b9365700-2183-11ea-9e31-2439f58be4c4.png)
---
### Logistic Regression Model
#### Model Training
![image](https://user-images.githubusercontent.com/47801267/71057753-c81d0980-2183-11ea-8e99-9c8355791572.png)
![image](https://user-images.githubusercontent.com/47801267/71057776-df5bf700-2183-11ea-8cd5-7efb4ad8f3b7.png)
***we will use 'L1' penalty as we might have correlated features like screens & 'L1' penalises any such fields that are strongly
correlated with response variable, this is because there will always be one screen that is just before the enrollment screen which imply that the correlation will be higher for that screen with enrollment screen ==> higher weight to that screen***
![image](https://user-images.githubusercontent.com/47801267/71057880-1a5e2a80-2184-11ea-9ef9-19d39a83d0e5.png)
![image](https://user-images.githubusercontent.com/47801267/71057892-221dcf00-2184-11ea-825b-5e6e7f701ffa.png)
![image](https://user-images.githubusercontent.com/47801267/71057918-2e099100-2184-11ea-8977-e0843e71f310.png)
![image](https://user-images.githubusercontent.com/47801267/71057924-319d1800-2184-11ea-801f-7e3c27abf4b7.png)
![image](https://user-images.githubusercontent.com/47801267/71057975-57c2b800-2184-11ea-9343-cecfe78df3e6.png)
- Model Accuracy = sum of diagonal value of cm/sum of all values of cm(confusion matrix)
- We also look for Precision to insure that model accuracy is inceased not because of some overfitting issues
- Precision Score = True Positive / (True Positive + False Positive), meaning that out-of all predicted positives what percentage are Actual positives
- Recall Score = True Positives / (True Positives + False Negatives, meaning that out-of all Actual Positives What Percentage are predicted to be positives
- We will also calculate f1-score as it creates a balance between Precision & Recall coz it is weighted average of Precision & Recall thereby it considers both False Positives & Flase Negative Intuitively f1-score is not easy to understand as accuracy but it is much better metric in case of class imbalanced data as in our case
- F1-Score = Precision*Recall / (Precision+Recall)
![image](https://user-images.githubusercontent.com/47801267/71058019-745ef000-2184-11ea-8a76-111b1f671e08.png)
**Sensitivity or TPR = TP/(TP+FN)**      
**Specificity = TN/(TN+FP),  (1-Specificity)=FPR**
![image](https://user-images.githubusercontent.com/47801267/71058028-79bc3a80-2184-11ea-85b0-1dda70b54c9e.png)
![image](https://user-images.githubusercontent.com/47801267/71058092-b25c1400-2184-11ea-9551-bf03adbe6f90.png)
**Here Area under ROC curve covers 85% which implies that the 85% of time model distinguish the 2 classes correctly**
---
**Predictions**
![image](https://user-images.githubusercontent.com/47801267/71058097-b6883180-2184-11ea-8b7e-22b8996255d3.png)
![image](https://user-images.githubusercontent.com/47801267/71058107-be47d600-2184-11ea-989b-1580b99e515d.png)
![image](https://user-images.githubusercontent.com/47801267/71058113-c1db5d00-2184-11ea-9ba0-56bb7696bc89.png)
![image](https://user-images.githubusercontent.com/47801267/71058168-eb948400-2184-11ea-8442-2b758985ca22.png)
`From both the plots we can conclude that both Actual & Predicted values follows same class distribution`
---
**Feature Importance**
![image](https://user-images.githubusercontent.com/47801267/71058172-f0f1ce80-2184-11ea-8b5c-6267b563840c.png)
![image](https://user-images.githubusercontent.com/47801267/71058177-f9e2a000-2184-11ea-81b8-19a64ce160e5.png)
![image](https://user-images.githubusercontent.com/47801267/71058182-fcdd9080-2184-11ea-916d-51c4ac20754b.png)
![image](https://user-images.githubusercontent.com/47801267/71058275-4201c280-2185-11ea-89c0-f141d27bf92e.png)
---
## Conclusion & Final Results
![tenor](https://user-images.githubusercontent.com/47801267/71058235-17176e80-2185-11ea-81ef-e1c381c7a760.gif)
- **Positively Affecting features to enrollment:** Other_sceens, VerifyPhone, CMCount, VerifyMobile, VerifyDateOfBirth, Rewards, EditProfile, etc, without any doubt all above features are situated to moving towards the enrollment screens.
- **Negatively Affecting features to enrollment:** LoanCount, VerifyCountry, Alerts, age, numscreens, Login, ResendToken, etc, if we see all these features are irritating & no user want to do this.
![image](https://user-images.githubusercontent.com/47801267/71058295-5e056400-2185-11ea-89e9-ddeadecd27ed.png)
![image](https://user-images.githubusercontent.com/47801267/71058399-bd637400-2185-11ea-9d65-49e17d8c91a0.png)
