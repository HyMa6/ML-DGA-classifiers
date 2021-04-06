# ML-of-DGA-classifiers<br />
Importance of diversity of DGA domain name data in ML modelling of DGA classifiers<br />

**Problem setting**<br />
I followed online lecture of ‘Supervised machine learning in security applications 2018, Charles Givre, O’Reilly’. He showed very high accuracy above 0.99 of Domain Generating Algorithm (DGA) classifier. I wanted replicate his experiment with one family of DGA. In addition, I was curious.  
- how does accuracy of the DGA classifier change if DGA data are used from various (six) DGA families instead of only one family of DGA?    
- Does use of diversified DGA data affect feature importances?

**Data**    <br />
Benign domain names from Cisco Umbrella (/Data/top-1m.csv.zip)<br />
Malicious domain names from data.netlab.360.com (/Data/dga.txt.zip)<br />

**Feature engineering** <br />
/Codes/DGA_feature_engineering-1DGAfamily.ipynb<br />
/Codes/DGA_feature_engineering-6DGAfamilies.ipynb<br />

**Data after feature engineering**<br />
Data with one DGA family (Data/domain_final_features.csv.zip)<br /> 
- DGA malicious damain names 179991 instances<br />
- Benign domain names 179991 instances<br />

Data with 6 DGA families (Data/domain_final_features_moredata.csv.zip)<br />
- DGA malicious damains 213695 instances<br />
- Benign domains 213695 instances<br />

**Approaches**<br />
![GitHub Logo](/images/workflow1_2-3.png)

**Supervised machine learning**<br />
/Codes/DGA_ML-1DGAfamily.ipynb<br />
/Codes/DGA_ML-6DGAfamily.ipynb<br />

**Results**<br />
Result1. Generating a realistic ML model by increasing diversity of the DGA data<br />
- Data from one DGA family: Accuracy 0.99
- Data form six  DGA families: Accuracy 0.87

Result 2. A rank and % of feature importance were changed upon increasing diversity of the DGA data<br />
- Data from one DGA family:<br />
  entropy (37%)> the length of domain (33 %) > a number of digits (28%)<br />
- Data from six DGA families<br />
 the length of domain (44 %) > entropy (36%)> vowels to consonant ratio (18%)<br />
 
Result 3. Random Forest (RF) & Decision Trees (DT) outperformed Support Vector Classification (SVC)<br />
	     Accuracy (%)<br />
	RF	86.7 <br />
	DF	86.7 <br />
	SVC	83.2<br />

**Quality of the results**<br />
My result is in line with previous findings achieving relatively low accuracy using the RF approach. <br />

**What did I learn?**<br />
A diversity of DGA data is crucial in ML modelling of DGA classifiers and to obtain correct information about feature importances. <br />

**How would I improve?**<br />
- To apply the deep learning approach like Long Short-Term Memory (LSTM) which has been shown to achieve higher accuracy <br />
- To incorporate side information such as rrlength and country to improve performance and robustness in modelling DGA classifiers<br />
- Assessing models by exposing them to real-traffic data<br />


