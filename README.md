# Fraud-Detection

This  project was handled to finish the Data Science Bootcamp training organized by the VBO organization. In this project we worked as a group, and it took one month. The group members are:
- Berkan ACAR
- Mert Ozan INAL
- Muhammed CIMCI
- Ismail KAYA
- Umit CEYLAN


# Scope of The Project

The aim of the project is benchmarking machine learning models on a challenging large-scale dataset to determine if transaction is fraud or not. 

# About Data Set
The data was published by the competition hosted by IEEE Computational Intelligence Society [(IEEE-CIS)](https://cis.ieee.org/) on [Kaggle](https://www.kaggle.com/) in 2019. It originates from the world’s leading payment service company, [Vesta Corporation](https://trustvesta.com/). You can read about the fraud detection competition and find the data set [here.](https://www.kaggle.com/c/ieee-fraud-detection). The train set of the merged data had initially 590.540 observations and 434 variables and the test set had 506.691 observations and 433 variables, accounting a total of 5 GB memory before pre-processing data. Hence, we applied memory reductions for the data before and during pre-processing procedure.



 #  Abstract

The data set used in this project was given as 4 different csv files, two of which are Train sets and the other two belong to the Test set. I fixed the structural errors in the column names of the files and combined the files with left join with Train and Test set. Since more than 95% of the variables given in terms of data privacy are kept confidential, I grouped the variables with different pattern determination techniques. After applying the EDA analysis to the grouped variables, I defined the userid to identify each person to whom the transactions belong. Based on Userid, I did feature engineering and got a Train set with dimension of 590540 x 284  before I entered it into the model. I predicted the Test set using tree-based models like XGBoost, LightGBM and CatBoost using this Train set I obtained. I used the GridSearch method to determine the hyperparameters of these models. Then I applied Kfold to the models and achieved higher accuracy results. The accuracy of these 3 models turned out to be very close to each other. Accuracy values of XGBoost, LightGBM and CatBoost were 92%, 91% and 90%, respectively.

# Pre-processing

There was a structural error in the test set of the two data sets (id and transaction). We corrected it by using train set columns. Then we merged the data sets.

We missing values -1 , converting data to positive

- verinini 6 aylık zaman serisi olduğu, nan değerler görselleştirildiğinde, aynı kaynaktan gelen veya farklı nedenlerden dolayı bazı değişkenlerde nan paterni yakaladık. oluşan pattern gruplarının kendi aralarındaki korelasyonlarına göre boyut azaltma işlemleri yapıldı. burada dikkatimizi tuhaf olarak v sütunlarının yanında bazı d ve id sütunlarının da bu patternlerde elendiğini gördük. bunu aynı bilgiyi taşıyan sütunları elemek (çoklu doğrusal bağlantı problemini engellemek). 


# Feature Engineering

-encoding yöntemleri (factorize used)

- mean encoding

- frequence encoding

- feature engineering (features koddan yazilacak)

kategorik değişkenlerden user id üretip bunlar üzerinden nümerik değişkenlerin aggregationları yapıldı. transectiondt gün ay ve yıla dünuştürülerek kullanıldı. ... işlemleri yapıldı.

daha sonra user idler ... nedenlerden dolayı drop edildi.

# Model

Data setindeki veri dengesiz bir veri ve featureları çok fazla NaN değer içeriyor. Featurelar arasındaki ilişkiye bakıldığında belirgin bir ilişki olmadığından ve overlapping olduğundan ağaç yöntemlerinden XGBoost, LightGBM ve CatBoost kullanmaya karar verdik. Modellerin kurulmasında ve hyperparametrelerinin belirlenmesinde gridsearch ve Kfold yöntemlerini kullandık ve bunların başarısını karşılaştırdık.

- catboost modelinde kategorik featurelara duyarlılığını test ettik. kategorik feature özelliği tercih edildiğinde sonucun her deneme yüksek başarı göstermesinden dolayı kategorik feature özelliği kullanıldı.
- Confusion matrix and Classification report are obtained. F1, Precision and Recall values are compared for different models.

Model basari metrigi olarak AUC kullanildi. doğru başarı metriğinin kullanılması gerekliydi. burada önemli olan yani hedef fraud işlemlerinin doğru tespit edilmesi. yani tp oranının artırılması.



# Conclusion

It can be useful  for online trade and banking operations.


# Further Studies

* Since the data set is big, hyperparameter tuning could not be done for a vaster intervals for the the hyperparameters. For example, the candidate values for n_estimators,max_depth, num_leaves and learning rates could be tried for much more different values.

* Group K-fold can be tried for the cross-validation accuracy calculations.

* The data can be splitted into test and train using time seris splitting. Test set ratio can be changed.

-----------------------------------------------------------------

