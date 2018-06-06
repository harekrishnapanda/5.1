# 5.1
import numpy as np
from scipy.stats import chi2_contingency

data = {"Gender": ["Female", "Male"],
        "Highschool": [60, 40],
        "Bachelors": [54, 44],
        "Masters": [46, 53],
        "Phd": [41, 57]}
df= pd.DataFrame(data)
df.set_index('Gender', inplace=True)
male=df[1:]
female=df[0:1]
m=np.asarray(male)[0]
f=np.asarray(female)[0]
x=chi2_contingency([m,f])
print(x)
#XCritical = 7.815 (Based on DegreeOfFreedom=3 and Alpha=5%)
#Since Chisquare(8.006) value is greater than ChiCritical value we reject the Null Hypothesis
print("So the education level depends on Gender at a 5% level of significance")
