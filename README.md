# ToreroKWIK
a Keyword in Context (KWIC) tool created for the USD Applied Data Science Program's text mining course.

## Assumptions
ToreroKWIK has one function: kwik()
```
kwik(doc_series, keyword, window=35, print_samples=5,case_sensitive=False)
```

<ol>
  <li>doc_series: a pandas series object containing a series of documents.<b>This function will not work if doc_series does not contain a field called 'text'.</b></li>
  <li>keyword: a string of characters. examples include "Pope","Potato",and "Sustainable".</li>
  <li>window: an integer representing how many charaacters around the keyword you'd like to print for context.</li>
  <li>print_samples: an integer representing how many instances you'd like to print. If the function finds fewer results than request samples, the request sample size will be automatically constrained by the sample size.</li>
  <li>case_sensitive: a boolean indicating whether or not capitalization matters. By default, this function coerces all documents to lowercase.</li>
</ol>

## Implementation
```
#import the UN GA Debate Transcripts
import pandas as pd
import numpy as np
import nltk
import re 
import kwic
df = pd.read_csv('ungd.csv.gz')

df.head()
```
![image](https://user-images.githubusercontent.com/36943200/169202474-429b793b-c81c-451b-a30d-866460e607fb.png)

```
#try out the kwic function on the 'text' field.
kwic.kwic(df['text'],'coincidence',35,5)
```
![image](https://user-images.githubusercontent.com/36943200/169202637-7ee39243-6c2f-4e31-ac12-838b9371495a.png)
