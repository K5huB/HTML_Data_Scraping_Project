# Kabir Sinha
## CMP 262
## Project 2
### Web Scraping Data Analysis - scrape 5 pages from a site for html data to analyze/answer questions concerning the data


```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

## Brooklyn Nets Data Scraping

### Initial Team Analysis


```python
url1 = 'https://www.espn.com/nba/team/stats/_/name/bkn/'
```


```python
table1 = pd.io.html.read_html(url1) # read in Brooklyn Nets data
table1
```




    [                      Name
     0            Cam Thomas SG
     1         Mikal Bridges SF
     2     Dennis Schroder PG *
     3       Cameron Johnson SF
     4   Spencer Dinwiddie PG *
     5            Nic Claxton C
     6       Lonnie Walker IV G
     7   Dorian Finney-Smith PF
     8       Royce O'Neale PF *
     9           Keon Johnson G
     10        Day'Ron Sharpe C
     11     Dennis Smith Jr. PG
     12      Trendon Watford PF
     13          Ben Simmons PG
     14          Jalen Wilson F
     15         Armoni Brooks G
     16          Noah Clowney F
     17     Harry Giles III F *
     18   Keita Bates-Diop SF *
     19       Dariq Whitehead F
     20       Jacob Gilyard G *
     21                   Total,
         GP    GS   MIN    PTS    OR    DR   REB   AST  STL  BLK    TO    PF  \
     0   61  46.0  31.1   22.1   0.4   2.8   3.2   2.9  0.7  0.2   1.8   2.1   
     1   77  77.0  35.4   20.3   0.9   3.8   4.7   3.7  1.0  0.4   2.1   1.4   
     2   26  22.0  31.7   14.4   0.5   2.7   3.2   5.9  0.6  0.3   2.5   2.0   
     3   57  47.0  27.6   13.4   1.0   3.4   4.4   2.4  0.8  0.3   1.0   1.8   
     4   48  48.0  30.7   12.6   0.5   2.8   3.3   6.0  0.8  0.2   1.3   1.8   
     5   67  67.0  29.8   12.0   2.8   7.2   9.9   2.0  0.7  2.0   1.3   2.5   
     6   54   0.0  16.9    9.8   0.2   1.9   2.1   1.2  0.5  0.3   0.9   1.2   
     7   67  55.0  28.5    8.6   1.6   3.0   4.6   1.6  0.8  0.6   0.8   2.2   
     8   49   6.0  24.5    7.4   0.8   3.7   4.5   2.8  0.7  0.6   1.0   2.4   
     9    4   0.0  12.8    7.0   0.8   0.5   1.3   0.8  0.8  0.3   1.0   1.0   
     10  58   1.0  15.1    7.0   2.6   3.8   6.4   1.4  0.4  0.7   1.1   2.2   
     11  56   2.0  18.9    6.6   0.9   2.0   2.9   3.6  1.2  0.2   1.2   2.2   
     12  58   0.0  12.4    6.4   0.8   1.9   2.7   1.1  0.4  0.3   0.8   1.6   
     13  15  12.0  23.9    6.1   2.1   5.9   7.9   5.7  0.8  0.6   1.8   2.4   
     14  38   2.0  13.9    4.5   1.0   1.6   2.6   1.0  0.2  0.0   0.4   1.0   
     15  10   0.0  10.4    4.2   0.7   1.1   1.8   0.5  0.1  0.1   0.3   0.3   
     16  18   0.0  11.3    4.1   0.9   1.8   2.7   0.7  0.3  0.2   0.5   1.0   
     17  16   0.0   5.1    3.4   0.8   0.9   1.6   0.4  0.1  0.2   0.4   0.9   
     18  14   0.0   4.9    1.6   0.1   0.6   0.6   0.3  0.2  0.1   0.1   0.1   
     19   2   0.0  12.0    1.5   0.0   2.0   2.0   1.5  0.0  0.5   0.0   0.0   
     20   2   0.0   7.5    0.0   0.0   0.0   0.0   1.0  0.5  0.0   0.0   1.0   
     21  77   NaN   NaN  111.2  11.5  32.3  43.8  26.0  6.9  5.0  12.2  18.7   
     
         AST/TO  
     0      1.6  
     1      1.8  
     2      2.4  
     3      2.5  
     4      4.6  
     5      1.6  
     6      1.4  
     7      1.9  
     8      2.7  
     9      0.8  
     10     1.2  
     11     3.0  
     12     1.4  
     13     3.2  
     14     2.5  
     15     1.7  
     16     1.3  
     17     1.0  
     18     2.0  
     19     inf  
     20     inf  
     21     2.1  ,
                           Name
     0            Cam Thomas SG
     1         Mikal Bridges SF
     2     Dennis Schroder PG *
     3       Cameron Johnson SF
     4   Spencer Dinwiddie PG *
     5            Nic Claxton C
     6       Lonnie Walker IV G
     7   Dorian Finney-Smith PF
     8       Royce O'Neale PF *
     9           Keon Johnson G
     10        Day'Ron Sharpe C
     11     Dennis Smith Jr. PG
     12      Trendon Watford PF
     13          Ben Simmons PG
     14          Jalen Wilson F
     15         Armoni Brooks G
     16          Noah Clowney F
     17     Harry Giles III F *
     18   Keita Bates-Diop SF *
     19       Dariq Whitehead F
     20       Jacob Gilyard G *
     21                   Total,
          FGM   FGA   FG%   3PM   3PA   3P%   FTM   FTA    FT%   2PM   2PA   2P%  \
     0    7.9  17.8  44.3   2.1   5.8  36.1   4.2   5.0   84.8   5.8  12.0  48.2   
     1    7.1  16.3  43.7   2.7   7.3  37.0   3.3   4.1   81.3   4.4   8.9  49.3   
     2    5.4  12.6  42.7   2.2   5.1  43.9   1.4   1.9   75.5   3.2   7.5  41.8   
     3    4.8  10.7  44.5   2.4   6.1  39.3   1.4   1.8   78.1   2.4   4.6  51.5   
     4    4.1  10.4  39.1   1.9   5.8  32.0   2.6   3.3   78.1   2.2   4.6  48.0   
     5    5.2   8.3  63.0   0.0   0.1  20.0   1.6   2.8   55.9   5.2   8.2  63.4   
     6    3.6   8.4  42.8   1.9   4.6  39.8   0.8   1.1   75.4   1.7   3.7  46.5   
     7    3.2   7.6  42.3   1.7   5.0  35.1   0.5   0.7   71.7   1.4   2.6  56.1   
     8    2.6   6.6  38.8   2.0   5.4  36.6   0.3   0.4   68.2   0.6   1.2  48.3   
     9    1.8   4.8  36.8   1.0   2.3  44.4   2.5   2.5  100.0   0.8   2.5  30.0   
     10   2.8   4.9  57.8   0.1   0.2  28.6   1.3   2.1   61.0   2.7   4.6  59.3   
     11   2.6   6.0  43.5   0.6   1.9  29.4   0.8   1.0   74.1   2.1   4.1  50.2   
     12   2.4   4.5  54.2   0.4   1.0  40.4   1.1   1.3   83.3   2.1   3.5  58.0   
     13   2.9   4.9  58.1   0.0   0.0   0.0   0.4   1.0   40.0   2.9   4.9  58.1   
     14   1.6   3.7  43.2   0.5   1.5  33.9   0.8   0.9   88.9   1.1   2.2  49.4   
     15   1.5   4.6  32.6   1.1   3.2  34.4   0.1   0.2   50.0   0.4   1.4  28.6   
     16   1.5   2.9  50.9   0.4   1.1  35.0   0.7   1.1   68.4   1.1   1.8  60.6   
     17   1.4   2.8  50.0   0.2   0.7  27.3   0.4   0.8   53.8   1.2   2.1  57.6   
     18   0.6   1.1  50.0   0.1   0.4  20.0   0.4   0.4  100.0   0.5   0.8  63.6   
     19   0.5   2.5  20.0   0.0   1.5   0.0   0.5   1.0   50.0   0.5   1.0  50.0   
     20   0.0   1.0   0.0   0.0   1.0   0.0   0.0   0.0    0.0   0.0   0.0   0.0   
     21  41.0  89.6  45.7  13.5  37.0  36.5  15.7  20.8   75.5  27.5  52.5  52.3   
     
         SC-EFF  SH-EFF  
     0    1.239    0.50  
     1    1.246    0.52  
     2    1.143    0.52  
     3    1.249    0.56  
     4    1.210    0.48  
     5    1.449    0.63  
     6    1.173    0.54  
     7    1.142    0.54  
     8    1.120    0.54  
     9    1.474    0.47  
     10   1.436    0.59  
     11   1.092    0.48  
     12   1.420    0.59  
     13   1.243    0.58  
     14   1.230    0.50  
     15   0.913    0.45  
     16   1.396    0.58  
     17   1.227    0.53  
     18   1.438    0.53  
     19   0.600    0.20  
     20   0.000    0.00  
     21   1.241    0.53  ]




```python
bkstats = table1[0]
bkstats1 = table1[1]
bkstats2 = table1[3] # assign the data I want to analyze to a variable
```


```python
bk = pd.merge(bkstats, bkstats1, right_index = True, left_index = True)
bkTable = pd.merge(bk, bkstats2, right_index = True, left_index = True)
bkTable # print the data table in horizontal format (it's broken into 2 sections on the website)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Cam Thomas SG</td>
      <td>61</td>
      <td>46.0</td>
      <td>31.1</td>
      <td>22.1</td>
      <td>0.4</td>
      <td>2.8</td>
      <td>3.2</td>
      <td>2.9</td>
      <td>0.7</td>
      <td>...</td>
      <td>5.8</td>
      <td>36.1</td>
      <td>4.2</td>
      <td>5.0</td>
      <td>84.8</td>
      <td>5.8</td>
      <td>12.0</td>
      <td>48.2</td>
      <td>1.239</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Mikal Bridges SF</td>
      <td>77</td>
      <td>77.0</td>
      <td>35.4</td>
      <td>20.3</td>
      <td>0.9</td>
      <td>3.8</td>
      <td>4.7</td>
      <td>3.7</td>
      <td>1.0</td>
      <td>...</td>
      <td>7.3</td>
      <td>37.0</td>
      <td>3.3</td>
      <td>4.1</td>
      <td>81.3</td>
      <td>4.4</td>
      <td>8.9</td>
      <td>49.3</td>
      <td>1.246</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Dennis Schroder PG *</td>
      <td>26</td>
      <td>22.0</td>
      <td>31.7</td>
      <td>14.4</td>
      <td>0.5</td>
      <td>2.7</td>
      <td>3.2</td>
      <td>5.9</td>
      <td>0.6</td>
      <td>...</td>
      <td>5.1</td>
      <td>43.9</td>
      <td>1.4</td>
      <td>1.9</td>
      <td>75.5</td>
      <td>3.2</td>
      <td>7.5</td>
      <td>41.8</td>
      <td>1.143</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Cameron Johnson SF</td>
      <td>57</td>
      <td>47.0</td>
      <td>27.6</td>
      <td>13.4</td>
      <td>1.0</td>
      <td>3.4</td>
      <td>4.4</td>
      <td>2.4</td>
      <td>0.8</td>
      <td>...</td>
      <td>6.1</td>
      <td>39.3</td>
      <td>1.4</td>
      <td>1.8</td>
      <td>78.1</td>
      <td>2.4</td>
      <td>4.6</td>
      <td>51.5</td>
      <td>1.249</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Spencer Dinwiddie PG *</td>
      <td>48</td>
      <td>48.0</td>
      <td>30.7</td>
      <td>12.6</td>
      <td>0.5</td>
      <td>2.8</td>
      <td>3.3</td>
      <td>6.0</td>
      <td>0.8</td>
      <td>...</td>
      <td>5.8</td>
      <td>32.0</td>
      <td>2.6</td>
      <td>3.3</td>
      <td>78.1</td>
      <td>2.2</td>
      <td>4.6</td>
      <td>48.0</td>
      <td>1.210</td>
      <td>0.48</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Nic Claxton C</td>
      <td>67</td>
      <td>67.0</td>
      <td>29.8</td>
      <td>12.0</td>
      <td>2.8</td>
      <td>7.2</td>
      <td>9.9</td>
      <td>2.0</td>
      <td>0.7</td>
      <td>...</td>
      <td>0.1</td>
      <td>20.0</td>
      <td>1.6</td>
      <td>2.8</td>
      <td>55.9</td>
      <td>5.2</td>
      <td>8.2</td>
      <td>63.4</td>
      <td>1.449</td>
      <td>0.63</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Lonnie Walker IV G</td>
      <td>54</td>
      <td>0.0</td>
      <td>16.9</td>
      <td>9.8</td>
      <td>0.2</td>
      <td>1.9</td>
      <td>2.1</td>
      <td>1.2</td>
      <td>0.5</td>
      <td>...</td>
      <td>4.6</td>
      <td>39.8</td>
      <td>0.8</td>
      <td>1.1</td>
      <td>75.4</td>
      <td>1.7</td>
      <td>3.7</td>
      <td>46.5</td>
      <td>1.173</td>
      <td>0.54</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Dorian Finney-Smith PF</td>
      <td>67</td>
      <td>55.0</td>
      <td>28.5</td>
      <td>8.6</td>
      <td>1.6</td>
      <td>3.0</td>
      <td>4.6</td>
      <td>1.6</td>
      <td>0.8</td>
      <td>...</td>
      <td>5.0</td>
      <td>35.1</td>
      <td>0.5</td>
      <td>0.7</td>
      <td>71.7</td>
      <td>1.4</td>
      <td>2.6</td>
      <td>56.1</td>
      <td>1.142</td>
      <td>0.54</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Royce O'Neale PF *</td>
      <td>49</td>
      <td>6.0</td>
      <td>24.5</td>
      <td>7.4</td>
      <td>0.8</td>
      <td>3.7</td>
      <td>4.5</td>
      <td>2.8</td>
      <td>0.7</td>
      <td>...</td>
      <td>5.4</td>
      <td>36.6</td>
      <td>0.3</td>
      <td>0.4</td>
      <td>68.2</td>
      <td>0.6</td>
      <td>1.2</td>
      <td>48.3</td>
      <td>1.120</td>
      <td>0.54</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Keon Johnson G</td>
      <td>4</td>
      <td>0.0</td>
      <td>12.8</td>
      <td>7.0</td>
      <td>0.8</td>
      <td>0.5</td>
      <td>1.3</td>
      <td>0.8</td>
      <td>0.8</td>
      <td>...</td>
      <td>2.3</td>
      <td>44.4</td>
      <td>2.5</td>
      <td>2.5</td>
      <td>100.0</td>
      <td>0.8</td>
      <td>2.5</td>
      <td>30.0</td>
      <td>1.474</td>
      <td>0.47</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Day'Ron Sharpe C</td>
      <td>58</td>
      <td>1.0</td>
      <td>15.1</td>
      <td>7.0</td>
      <td>2.6</td>
      <td>3.8</td>
      <td>6.4</td>
      <td>1.4</td>
      <td>0.4</td>
      <td>...</td>
      <td>0.2</td>
      <td>28.6</td>
      <td>1.3</td>
      <td>2.1</td>
      <td>61.0</td>
      <td>2.7</td>
      <td>4.6</td>
      <td>59.3</td>
      <td>1.436</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Dennis Smith Jr. PG</td>
      <td>56</td>
      <td>2.0</td>
      <td>18.9</td>
      <td>6.6</td>
      <td>0.9</td>
      <td>2.0</td>
      <td>2.9</td>
      <td>3.6</td>
      <td>1.2</td>
      <td>...</td>
      <td>1.9</td>
      <td>29.4</td>
      <td>0.8</td>
      <td>1.0</td>
      <td>74.1</td>
      <td>2.1</td>
      <td>4.1</td>
      <td>50.2</td>
      <td>1.092</td>
      <td>0.48</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Trendon Watford PF</td>
      <td>58</td>
      <td>0.0</td>
      <td>12.4</td>
      <td>6.4</td>
      <td>0.8</td>
      <td>1.9</td>
      <td>2.7</td>
      <td>1.1</td>
      <td>0.4</td>
      <td>...</td>
      <td>1.0</td>
      <td>40.4</td>
      <td>1.1</td>
      <td>1.3</td>
      <td>83.3</td>
      <td>2.1</td>
      <td>3.5</td>
      <td>58.0</td>
      <td>1.420</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Ben Simmons PG</td>
      <td>15</td>
      <td>12.0</td>
      <td>23.9</td>
      <td>6.1</td>
      <td>2.1</td>
      <td>5.9</td>
      <td>7.9</td>
      <td>5.7</td>
      <td>0.8</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.4</td>
      <td>1.0</td>
      <td>40.0</td>
      <td>2.9</td>
      <td>4.9</td>
      <td>58.1</td>
      <td>1.243</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Jalen Wilson F</td>
      <td>38</td>
      <td>2.0</td>
      <td>13.9</td>
      <td>4.5</td>
      <td>1.0</td>
      <td>1.6</td>
      <td>2.6</td>
      <td>1.0</td>
      <td>0.2</td>
      <td>...</td>
      <td>1.5</td>
      <td>33.9</td>
      <td>0.8</td>
      <td>0.9</td>
      <td>88.9</td>
      <td>1.1</td>
      <td>2.2</td>
      <td>49.4</td>
      <td>1.230</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Armoni Brooks G</td>
      <td>10</td>
      <td>0.0</td>
      <td>10.4</td>
      <td>4.2</td>
      <td>0.7</td>
      <td>1.1</td>
      <td>1.8</td>
      <td>0.5</td>
      <td>0.1</td>
      <td>...</td>
      <td>3.2</td>
      <td>34.4</td>
      <td>0.1</td>
      <td>0.2</td>
      <td>50.0</td>
      <td>0.4</td>
      <td>1.4</td>
      <td>28.6</td>
      <td>0.913</td>
      <td>0.45</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Noah Clowney F</td>
      <td>18</td>
      <td>0.0</td>
      <td>11.3</td>
      <td>4.1</td>
      <td>0.9</td>
      <td>1.8</td>
      <td>2.7</td>
      <td>0.7</td>
      <td>0.3</td>
      <td>...</td>
      <td>1.1</td>
      <td>35.0</td>
      <td>0.7</td>
      <td>1.1</td>
      <td>68.4</td>
      <td>1.1</td>
      <td>1.8</td>
      <td>60.6</td>
      <td>1.396</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Harry Giles III F *</td>
      <td>16</td>
      <td>0.0</td>
      <td>5.1</td>
      <td>3.4</td>
      <td>0.8</td>
      <td>0.9</td>
      <td>1.6</td>
      <td>0.4</td>
      <td>0.1</td>
      <td>...</td>
      <td>0.7</td>
      <td>27.3</td>
      <td>0.4</td>
      <td>0.8</td>
      <td>53.8</td>
      <td>1.2</td>
      <td>2.1</td>
      <td>57.6</td>
      <td>1.227</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Keita Bates-Diop SF *</td>
      <td>14</td>
      <td>0.0</td>
      <td>4.9</td>
      <td>1.6</td>
      <td>0.1</td>
      <td>0.6</td>
      <td>0.6</td>
      <td>0.3</td>
      <td>0.2</td>
      <td>...</td>
      <td>0.4</td>
      <td>20.0</td>
      <td>0.4</td>
      <td>0.4</td>
      <td>100.0</td>
      <td>0.5</td>
      <td>0.8</td>
      <td>63.6</td>
      <td>1.438</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Dariq Whitehead F</td>
      <td>2</td>
      <td>0.0</td>
      <td>12.0</td>
      <td>1.5</td>
      <td>0.0</td>
      <td>2.0</td>
      <td>2.0</td>
      <td>1.5</td>
      <td>0.0</td>
      <td>...</td>
      <td>1.5</td>
      <td>0.0</td>
      <td>0.5</td>
      <td>1.0</td>
      <td>50.0</td>
      <td>0.5</td>
      <td>1.0</td>
      <td>50.0</td>
      <td>0.600</td>
      <td>0.20</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Jacob Gilyard G *</td>
      <td>2</td>
      <td>0.0</td>
      <td>7.5</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.5</td>
      <td>...</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.000</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Total</td>
      <td>77</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>111.2</td>
      <td>11.5</td>
      <td>32.3</td>
      <td>43.8</td>
      <td>26.0</td>
      <td>6.9</td>
      <td>...</td>
      <td>37.0</td>
      <td>36.5</td>
      <td>15.7</td>
      <td>20.8</td>
      <td>75.5</td>
      <td>27.5</td>
      <td>52.5</td>
      <td>52.3</td>
      <td>1.241</td>
      <td>0.53</td>
    </tr>
  </tbody>
</table>
<p>22 rows × 28 columns</p>
</div>




```python
bkTable.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>BLK</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>22.000000</td>
      <td>21.000000</td>
      <td>21.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>...</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
      <td>22.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>39.727273</td>
      <td>18.333333</td>
      <td>19.257143</td>
      <td>12.918182</td>
      <td>1.404545</td>
      <td>3.895455</td>
      <td>5.281818</td>
      <td>3.295455</td>
      <td>0.840909</td>
      <td>0.595455</td>
      <td>...</td>
      <td>4.409091</td>
      <td>29.531818</td>
      <td>1.854545</td>
      <td>2.463636</td>
      <td>68.818182</td>
      <td>3.172727</td>
      <td>6.122727</td>
      <td>48.672727</td>
      <td>1.167318</td>
      <td>0.493636</td>
    </tr>
    <tr>
      <th>std</th>
      <td>25.648135</td>
      <td>26.159766</td>
      <td>9.699050</td>
      <td>22.677693</td>
      <td>2.376568</td>
      <td>6.567777</td>
      <td>8.907762</td>
      <td>5.372281</td>
      <td>1.389299</td>
      <td>1.065689</td>
      <td>...</td>
      <td>7.646905</td>
      <td>13.553505</td>
      <td>3.274974</td>
      <td>4.290471</td>
      <td>21.864009</td>
      <td>5.650805</td>
      <td>10.776957</td>
      <td>14.150894</td>
      <td>0.326001</td>
      <td>0.138204</td>
    </tr>
    <tr>
      <th>min</th>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>4.900000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.300000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>15.250000</td>
      <td>0.000000</td>
      <td>12.000000</td>
      <td>4.275000</td>
      <td>0.500000</td>
      <td>1.650000</td>
      <td>2.025000</td>
      <td>1.000000</td>
      <td>0.325000</td>
      <td>0.200000</td>
      <td>...</td>
      <td>1.000000</td>
      <td>27.625000</td>
      <td>0.425000</td>
      <td>0.825000</td>
      <td>57.175000</td>
      <td>0.875000</td>
      <td>1.875000</td>
      <td>48.050000</td>
      <td>1.142250</td>
      <td>0.485000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>48.500000</td>
      <td>2.000000</td>
      <td>16.900000</td>
      <td>7.000000</td>
      <td>0.800000</td>
      <td>2.350000</td>
      <td>3.050000</td>
      <td>1.550000</td>
      <td>0.650000</td>
      <td>0.300000</td>
      <td>...</td>
      <td>2.100000</td>
      <td>34.700000</td>
      <td>0.800000</td>
      <td>1.100000</td>
      <td>74.750000</td>
      <td>1.900000</td>
      <td>3.600000</td>
      <td>50.100000</td>
      <td>1.234500</td>
      <td>0.530000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>58.000000</td>
      <td>46.000000</td>
      <td>28.500000</td>
      <td>12.450000</td>
      <td>1.000000</td>
      <td>3.625000</td>
      <td>4.575000</td>
      <td>3.425000</td>
      <td>0.800000</td>
      <td>0.575000</td>
      <td>...</td>
      <td>5.325000</td>
      <td>36.900000</td>
      <td>1.550000</td>
      <td>2.400000</td>
      <td>80.500000</td>
      <td>2.850000</td>
      <td>4.825000</td>
      <td>57.900000</td>
      <td>1.359250</td>
      <td>0.555000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>77.000000</td>
      <td>77.000000</td>
      <td>35.400000</td>
      <td>111.200000</td>
      <td>11.500000</td>
      <td>32.300000</td>
      <td>43.800000</td>
      <td>26.000000</td>
      <td>6.900000</td>
      <td>5.000000</td>
      <td>...</td>
      <td>37.000000</td>
      <td>44.400000</td>
      <td>15.700000</td>
      <td>20.800000</td>
      <td>100.000000</td>
      <td>27.500000</td>
      <td>52.500000</td>
      <td>63.600000</td>
      <td>1.474000</td>
      <td>0.630000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 27 columns</p>
</div>




```python
bkTable.columns
```




    Index(['Name', 'GP', 'GS', 'MIN', 'PTS', 'OR', 'DR', 'REB', 'AST', 'STL',
           'BLK', 'TO', 'PF', 'AST/TO', 'FGM', 'FGA', 'FG%', '3PM', '3PA', '3P%',
           'FTM', 'FTA', 'FT%', '2PM', '2PA', '2P%', 'SC-EFF', 'SH-EFF'],
          dtype='object')




```python
bkTable.shape
```




    (22, 28)




```python
bkTable.dtypes
```




    Name       object
    GP          int64
    GS        float64
    MIN       float64
    PTS       float64
    OR        float64
    DR        float64
    REB       float64
    AST       float64
    STL       float64
    BLK       float64
    TO        float64
    PF        float64
    AST/TO    float64
    FGM       float64
    FGA       float64
    FG%       float64
    3PM       float64
    3PA       float64
    3P%       float64
    FTM       float64
    FTA       float64
    FT%       float64
    2PM       float64
    2PA       float64
    2P%       float64
    SC-EFF    float64
    SH-EFF    float64
    dtype: object



### Only ranking these teams based on the top 15 players since that is the size of the smallest team


```python
bkTable = bkTable.drop(bkTable.index[16:])
```


```python
bkTable.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Cam Thomas SG</td>
      <td>61</td>
      <td>46.0</td>
      <td>31.1</td>
      <td>22.1</td>
      <td>0.4</td>
      <td>2.8</td>
      <td>3.2</td>
      <td>2.9</td>
      <td>0.7</td>
      <td>...</td>
      <td>5.8</td>
      <td>36.1</td>
      <td>4.2</td>
      <td>5.0</td>
      <td>84.8</td>
      <td>5.8</td>
      <td>12.0</td>
      <td>48.2</td>
      <td>1.239</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Mikal Bridges SF</td>
      <td>77</td>
      <td>77.0</td>
      <td>35.4</td>
      <td>20.3</td>
      <td>0.9</td>
      <td>3.8</td>
      <td>4.7</td>
      <td>3.7</td>
      <td>1.0</td>
      <td>...</td>
      <td>7.3</td>
      <td>37.0</td>
      <td>3.3</td>
      <td>4.1</td>
      <td>81.3</td>
      <td>4.4</td>
      <td>8.9</td>
      <td>49.3</td>
      <td>1.246</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Dennis Schroder PG *</td>
      <td>26</td>
      <td>22.0</td>
      <td>31.7</td>
      <td>14.4</td>
      <td>0.5</td>
      <td>2.7</td>
      <td>3.2</td>
      <td>5.9</td>
      <td>0.6</td>
      <td>...</td>
      <td>5.1</td>
      <td>43.9</td>
      <td>1.4</td>
      <td>1.9</td>
      <td>75.5</td>
      <td>3.2</td>
      <td>7.5</td>
      <td>41.8</td>
      <td>1.143</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Cameron Johnson SF</td>
      <td>57</td>
      <td>47.0</td>
      <td>27.6</td>
      <td>13.4</td>
      <td>1.0</td>
      <td>3.4</td>
      <td>4.4</td>
      <td>2.4</td>
      <td>0.8</td>
      <td>...</td>
      <td>6.1</td>
      <td>39.3</td>
      <td>1.4</td>
      <td>1.8</td>
      <td>78.1</td>
      <td>2.4</td>
      <td>4.6</td>
      <td>51.5</td>
      <td>1.249</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Spencer Dinwiddie PG *</td>
      <td>48</td>
      <td>48.0</td>
      <td>30.7</td>
      <td>12.6</td>
      <td>0.5</td>
      <td>2.8</td>
      <td>3.3</td>
      <td>6.0</td>
      <td>0.8</td>
      <td>...</td>
      <td>5.8</td>
      <td>32.0</td>
      <td>2.6</td>
      <td>3.3</td>
      <td>78.1</td>
      <td>2.2</td>
      <td>4.6</td>
      <td>48.0</td>
      <td>1.210</td>
      <td>0.48</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
bkTable.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>Dennis Smith Jr. PG</td>
      <td>56</td>
      <td>2.0</td>
      <td>18.9</td>
      <td>6.6</td>
      <td>0.9</td>
      <td>2.0</td>
      <td>2.9</td>
      <td>3.6</td>
      <td>1.2</td>
      <td>...</td>
      <td>1.9</td>
      <td>29.4</td>
      <td>0.8</td>
      <td>1.0</td>
      <td>74.1</td>
      <td>2.1</td>
      <td>4.1</td>
      <td>50.2</td>
      <td>1.092</td>
      <td>0.48</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Trendon Watford PF</td>
      <td>58</td>
      <td>0.0</td>
      <td>12.4</td>
      <td>6.4</td>
      <td>0.8</td>
      <td>1.9</td>
      <td>2.7</td>
      <td>1.1</td>
      <td>0.4</td>
      <td>...</td>
      <td>1.0</td>
      <td>40.4</td>
      <td>1.1</td>
      <td>1.3</td>
      <td>83.3</td>
      <td>2.1</td>
      <td>3.5</td>
      <td>58.0</td>
      <td>1.420</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Ben Simmons PG</td>
      <td>15</td>
      <td>12.0</td>
      <td>23.9</td>
      <td>6.1</td>
      <td>2.1</td>
      <td>5.9</td>
      <td>7.9</td>
      <td>5.7</td>
      <td>0.8</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.4</td>
      <td>1.0</td>
      <td>40.0</td>
      <td>2.9</td>
      <td>4.9</td>
      <td>58.1</td>
      <td>1.243</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Jalen Wilson F</td>
      <td>38</td>
      <td>2.0</td>
      <td>13.9</td>
      <td>4.5</td>
      <td>1.0</td>
      <td>1.6</td>
      <td>2.6</td>
      <td>1.0</td>
      <td>0.2</td>
      <td>...</td>
      <td>1.5</td>
      <td>33.9</td>
      <td>0.8</td>
      <td>0.9</td>
      <td>88.9</td>
      <td>1.1</td>
      <td>2.2</td>
      <td>49.4</td>
      <td>1.230</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Armoni Brooks G</td>
      <td>10</td>
      <td>0.0</td>
      <td>10.4</td>
      <td>4.2</td>
      <td>0.7</td>
      <td>1.1</td>
      <td>1.8</td>
      <td>0.5</td>
      <td>0.1</td>
      <td>...</td>
      <td>3.2</td>
      <td>34.4</td>
      <td>0.1</td>
      <td>0.2</td>
      <td>50.0</td>
      <td>0.4</td>
      <td>1.4</td>
      <td>28.6</td>
      <td>0.913</td>
      <td>0.45</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
bkTable.sample()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>14</th>
      <td>Jalen Wilson F</td>
      <td>38</td>
      <td>2.0</td>
      <td>13.9</td>
      <td>4.5</td>
      <td>1.0</td>
      <td>1.6</td>
      <td>2.6</td>
      <td>1.0</td>
      <td>0.2</td>
      <td>...</td>
      <td>1.5</td>
      <td>33.9</td>
      <td>0.8</td>
      <td>0.9</td>
      <td>88.9</td>
      <td>1.1</td>
      <td>2.2</td>
      <td>49.4</td>
      <td>1.23</td>
      <td>0.5</td>
    </tr>
  </tbody>
</table>
<p>1 rows × 28 columns</p>
</div>




```python
bkTable.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 16 entries, 0 to 15
    Data columns (total 28 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   Name    16 non-null     object 
     1   GP      16 non-null     int64  
     2   GS      16 non-null     float64
     3   MIN     16 non-null     float64
     4   PTS     16 non-null     float64
     5   OR      16 non-null     float64
     6   DR      16 non-null     float64
     7   REB     16 non-null     float64
     8   AST     16 non-null     float64
     9   STL     16 non-null     float64
     10  BLK     16 non-null     float64
     11  TO      16 non-null     float64
     12  PF      16 non-null     float64
     13  AST/TO  16 non-null     float64
     14  FGM     16 non-null     float64
     15  FGA     16 non-null     float64
     16  FG%     16 non-null     float64
     17  3PM     16 non-null     float64
     18  3PA     16 non-null     float64
     19  3P%     16 non-null     float64
     20  FTM     16 non-null     float64
     21  FTA     16 non-null     float64
     22  FT%     16 non-null     float64
     23  2PM     16 non-null     float64
     24  2PA     16 non-null     float64
     25  2P%     16 non-null     float64
     26  SC-EFF  16 non-null     float64
     27  SH-EFF  16 non-null     float64
    dtypes: float64(26), int64(1), object(1)
    memory usage: 3.6+ KB


### Additional Data Analysis

#### Total of average player PPG's for Brooklyn


```python
bk_totAvgPlyrPts = bkTable['PTS'].sum()
bk_totAvgPlyrPts
```




    162.39999999999998



#### Players with most/least games played


```python
bkGames = bkTable['GP'].max()
print(bkTable.loc[bkTable['GP'] == bkGames, 'Name'], bkGames)
```

    1    Mikal Bridges SF
    Name: Name, dtype: object 77



```python
bkGames1 = bkTable['GP'].min()
print(bkTable.loc[bkTable['GP'] == bkGames1, 'Name'], bkGames1)
```

    9    Keon Johnson G
    Name: Name, dtype: object 4


#### Players with most/least fouls averaged per game


```python
bkFouls = bkTable['PF'].max()
print(bkTable.loc[bkTable['PF'] == bkFouls, 'Name'], bkFouls)
```

    5    Nic Claxton C
    Name: Name, dtype: object 2.5



```python
bkFouls1 = bkTable['PF'].min()
print(bkTable.loc[bkTable['PF'] == bkFouls1, 'Name'], bkFouls1)
```

    15    Armoni Brooks G
    Name: Name, dtype: object 0.3



```python
bkBar = plt.bar(bkTable['Name'], bkTable['PF'])
plt.title('Players and Their Avg Fouls/Game')
plt.xlabel('Players')
plt.ylabel('Avg Fouls/Game')
plt.xticks(rotation = 90)
bkBar
```




    <BarContainer object of 16 artists>




    
![png](output_27_1.png)
    


#### Player averaging the most 3's


```python
bkThrees = bkTable['3PM'].max()
print(bkTable.loc[bkTable['3PM'] == bkThrees, 'Name'], bkThrees)
```

    1    Mikal Bridges SF
    Name: Name, dtype: object 2.7


#### Player(s) averaging the least 3's


```python
bkThrees1 = bkTable['3PM'].min()
print(bkTable.loc[bkTable['3PM'] == bkThrees1, 'Name'], bkThrees1)
```

    5      Nic Claxton C
    13    Ben Simmons PG
    Name: Name, dtype: object 0.0


#### Total Defensive Stats: Def Rebounds + Blocks + Steals


```python
DefReb = bkTable['DR'].sum()
Blocks = bkTable['BLK'].sum()
Steals = bkTable['STL'].sum()
DefStats = (DefReb + Blocks + Steals)
DefStats
```




    65.7



## Denver Nuggets Data Scraping

### Initial Team Analysis


```python
url2 = 'https://www.espn.com/nba/team/stats/_/name/den/'
```


```python
table2 = pd.io.html.read_html(url2)
table2
```




    [                           Name
     0                Nikola Jokic C
     1               Jamal Murray PG
     2         Michael Porter Jr. SF
     3               Aaron Gordon PF
     4             Reggie Jackson PG
     5   Kentavious Caldwell-Pope SG
     6             Christian Braun G
     7               Peyton Watson F
     8            Julian Strawther G
     9              DeAndre Jordan C
     10            Justin Holiday SF
     11           Collin Gillespie G
     12                Zeke Nnaji PF
     13              Jalen Pickett G
     14               Hunter Tyson F
     15                   Jay Huff C
     16                Braxton Key F
     17                        Total,
         GP    GS   MIN    PTS    OR    DR   REB   AST  STL  BLK    TO    PF  \
     0   74  74.0  34.6   26.5   2.8   9.6  12.4   9.0  1.3  0.9   3.0   2.4   
     1   54  54.0  32.1   20.9   0.7   3.4   4.1   6.7  1.0  0.6   2.1   1.8   
     2   76  76.0  31.8   16.8   1.3   5.8   7.1   1.5  0.5  0.7   1.1   1.8   
     3   70  70.0  31.6   14.0   2.4   4.1   6.5   3.4  0.8  0.6   1.5   2.0   
     4   77  23.0  22.2   10.1   0.4   1.5   1.9   3.8  0.5  0.1   1.3   1.8   
     5   71  71.0  31.9   10.0   0.4   2.0   2.4   2.4  1.3  0.5   1.0   2.0   
     6   77   2.0  19.8    7.1   0.9   2.8   3.7   1.5  0.5  0.4   0.7   1.7   
     7   75   4.0  18.2    6.6   0.7   2.4   3.1   1.0  0.5  1.0   0.7   1.8   
     8   46   0.0  11.5    4.8   0.1   1.1   1.2   1.0  0.4  0.2   0.4   1.1   
     9   36   2.0  11.0    3.9   1.5   2.9   4.4   0.7  0.2  0.4   0.6   1.6   
     10  53   9.0  14.7    3.9   0.2   1.1   1.3   1.1  0.6  0.2   0.2   1.2   
     11  24   0.0   9.4    3.6   0.0   0.8   0.9   1.1  0.5  0.0   0.6   1.0   
     12  53   0.0   9.8    3.2   1.1   1.0   2.1   0.6  0.2  0.7   0.5   1.4   
     13  24   0.0   4.8    1.6   0.0   0.5   0.5   0.8  0.1  0.0   0.4   0.5   
     14  14   0.0   2.9    1.3   0.1   0.6   0.6   0.1  0.0  0.0   0.1   0.7   
     15  17   0.0   2.6    1.1   0.1   0.5   0.6   0.1  0.1  0.1   0.1   0.5   
     16  19   0.0   3.1    1.1   0.2   0.7   0.8   0.5  0.1  0.1   0.1   0.3   
     17  77   NaN   NaN  114.3  10.8  33.7  44.4  29.3  7.0  5.5  11.8  18.2   
     
         AST/TO  
     0      3.0  
     1      3.2  
     2      1.3  
     3      2.4  
     4      2.9  
     5      2.5  
     6      2.3  
     7      1.4  
     8      2.3  
     9      1.1  
     10     4.7  
     11     1.9  
     12     1.1  
     13     2.0  
     14     1.0  
     15     2.0  
     16     9.0  
     17     2.5  ,
                                Name
     0                Nikola Jokic C
     1               Jamal Murray PG
     2         Michael Porter Jr. SF
     3               Aaron Gordon PF
     4             Reggie Jackson PG
     5   Kentavious Caldwell-Pope SG
     6             Christian Braun G
     7               Peyton Watson F
     8            Julian Strawther G
     9              DeAndre Jordan C
     10            Justin Holiday SF
     11           Collin Gillespie G
     12                Zeke Nnaji PF
     13              Jalen Pickett G
     14               Hunter Tyson F
     15                   Jay Huff C
     16                Braxton Key F
     17                        Total,
          FGM   FGA   FG%   3PM   3PA   3P%   FTM   FTA    FT%   2PM   2PA    2P%  \
     0   10.4  18.0  57.9   1.0   3.0  34.2   4.6   5.6   82.3   9.4  15.0   62.6   
     1    7.9  16.7  47.5   2.4   5.6  41.9   2.7   3.2   85.5   5.6  11.1   50.3   
     2    6.5  13.3  48.6   2.8   6.9  40.0   1.1   1.4   82.5   3.7   6.5   57.7   
     3    5.5  10.0  55.4   0.6   1.9  29.1   2.4   3.7   65.3   5.0   8.0   61.6   
     4    4.0   9.1  43.5   1.2   3.4  36.4   0.9   1.2   80.2   2.7   5.7   47.7   
     5    3.5   7.7  45.0   1.6   4.0  40.6   1.4   1.6   90.2   1.8   3.7   49.8   
     6    2.6   5.8  45.3   0.7   1.9  37.2   1.1   1.6   69.6   1.9   3.9   49.3   
     7    2.5   5.5  46.0   0.6   2.0  29.7   0.9   1.3   68.0   2.0   3.6   55.1   
     8    1.8   4.7  37.3   0.9   2.9  29.6   0.4   0.6   74.1   0.9   1.8   50.0   
     9    1.6   2.6  62.4   0.0   0.0   0.0   0.7   1.5   49.1   1.6   2.6   62.4   
     10   1.5   3.3  45.1   0.9   2.2  39.8   0.1   0.1   75.0   0.6   1.0   56.4   
     11   1.3   2.9  46.4   0.6   1.6  39.5   0.3   0.5   66.7   0.7   1.3   54.8   
     12   1.2   2.6  44.9   0.1   0.4  23.8   0.8   1.1   71.2   1.1   2.2   48.7   
     13   0.6   1.4  42.4   0.3   1.0  34.8   0.1   0.2   75.0   0.3   0.4   60.0   
     14   0.5   1.2  41.2   0.3   0.9  33.3   0.0   0.0    0.0   0.2   0.4   60.0   
     15   0.4   0.8  53.8   0.2   0.5  33.3   0.1   0.1  100.0   0.2   0.2  100.0   
     16   0.4   0.9  41.2   0.1   0.3  40.0   0.2   0.3   66.7   0.3   0.6   41.7   
     17  43.8  88.7  49.4  11.5  31.0  37.1  15.3  20.0   76.4  32.3  57.7   55.9   
     
         SC-EFF  SH-EFF  
     0    1.469    0.61  
     1    1.253    0.54  
     2    1.262    0.59  
     3    1.406    0.58  
     4    1.110    0.50  
     5    1.295    0.56  
     6    1.224    0.51  
     7    1.190    0.51  
     8    1.023    0.47  
     9    1.527    0.62  
     10   1.191    0.59  
     11   1.261    0.57  
     12   1.243    0.47  
     13   1.182    0.55  
     14   1.059    0.53  
     15   1.462    0.65  
     16   1.176    0.47  
     17   1.289    0.56  ]




```python
denstats = table2[0]
denstats1 = table2[1]
denstats2 = table2[3]
```


```python
den = pd.merge(denstats, denstats1, right_index = True, left_index = True)
denTable = pd.merge(den, denstats2, right_index = True, left_index = True)
denTable
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Nikola Jokic C</td>
      <td>74</td>
      <td>74.0</td>
      <td>34.6</td>
      <td>26.5</td>
      <td>2.8</td>
      <td>9.6</td>
      <td>12.4</td>
      <td>9.0</td>
      <td>1.3</td>
      <td>...</td>
      <td>3.0</td>
      <td>34.2</td>
      <td>4.6</td>
      <td>5.6</td>
      <td>82.3</td>
      <td>9.4</td>
      <td>15.0</td>
      <td>62.6</td>
      <td>1.469</td>
      <td>0.61</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jamal Murray PG</td>
      <td>54</td>
      <td>54.0</td>
      <td>32.1</td>
      <td>20.9</td>
      <td>0.7</td>
      <td>3.4</td>
      <td>4.1</td>
      <td>6.7</td>
      <td>1.0</td>
      <td>...</td>
      <td>5.6</td>
      <td>41.9</td>
      <td>2.7</td>
      <td>3.2</td>
      <td>85.5</td>
      <td>5.6</td>
      <td>11.1</td>
      <td>50.3</td>
      <td>1.253</td>
      <td>0.54</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Michael Porter Jr. SF</td>
      <td>76</td>
      <td>76.0</td>
      <td>31.8</td>
      <td>16.8</td>
      <td>1.3</td>
      <td>5.8</td>
      <td>7.1</td>
      <td>1.5</td>
      <td>0.5</td>
      <td>...</td>
      <td>6.9</td>
      <td>40.0</td>
      <td>1.1</td>
      <td>1.4</td>
      <td>82.5</td>
      <td>3.7</td>
      <td>6.5</td>
      <td>57.7</td>
      <td>1.262</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Aaron Gordon PF</td>
      <td>70</td>
      <td>70.0</td>
      <td>31.6</td>
      <td>14.0</td>
      <td>2.4</td>
      <td>4.1</td>
      <td>6.5</td>
      <td>3.4</td>
      <td>0.8</td>
      <td>...</td>
      <td>1.9</td>
      <td>29.1</td>
      <td>2.4</td>
      <td>3.7</td>
      <td>65.3</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>61.6</td>
      <td>1.406</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Reggie Jackson PG</td>
      <td>77</td>
      <td>23.0</td>
      <td>22.2</td>
      <td>10.1</td>
      <td>0.4</td>
      <td>1.5</td>
      <td>1.9</td>
      <td>3.8</td>
      <td>0.5</td>
      <td>...</td>
      <td>3.4</td>
      <td>36.4</td>
      <td>0.9</td>
      <td>1.2</td>
      <td>80.2</td>
      <td>2.7</td>
      <td>5.7</td>
      <td>47.7</td>
      <td>1.110</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Kentavious Caldwell-Pope SG</td>
      <td>71</td>
      <td>71.0</td>
      <td>31.9</td>
      <td>10.0</td>
      <td>0.4</td>
      <td>2.0</td>
      <td>2.4</td>
      <td>2.4</td>
      <td>1.3</td>
      <td>...</td>
      <td>4.0</td>
      <td>40.6</td>
      <td>1.4</td>
      <td>1.6</td>
      <td>90.2</td>
      <td>1.8</td>
      <td>3.7</td>
      <td>49.8</td>
      <td>1.295</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Christian Braun G</td>
      <td>77</td>
      <td>2.0</td>
      <td>19.8</td>
      <td>7.1</td>
      <td>0.9</td>
      <td>2.8</td>
      <td>3.7</td>
      <td>1.5</td>
      <td>0.5</td>
      <td>...</td>
      <td>1.9</td>
      <td>37.2</td>
      <td>1.1</td>
      <td>1.6</td>
      <td>69.6</td>
      <td>1.9</td>
      <td>3.9</td>
      <td>49.3</td>
      <td>1.224</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Peyton Watson F</td>
      <td>75</td>
      <td>4.0</td>
      <td>18.2</td>
      <td>6.6</td>
      <td>0.7</td>
      <td>2.4</td>
      <td>3.1</td>
      <td>1.0</td>
      <td>0.5</td>
      <td>...</td>
      <td>2.0</td>
      <td>29.7</td>
      <td>0.9</td>
      <td>1.3</td>
      <td>68.0</td>
      <td>2.0</td>
      <td>3.6</td>
      <td>55.1</td>
      <td>1.190</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Julian Strawther G</td>
      <td>46</td>
      <td>0.0</td>
      <td>11.5</td>
      <td>4.8</td>
      <td>0.1</td>
      <td>1.1</td>
      <td>1.2</td>
      <td>1.0</td>
      <td>0.4</td>
      <td>...</td>
      <td>2.9</td>
      <td>29.6</td>
      <td>0.4</td>
      <td>0.6</td>
      <td>74.1</td>
      <td>0.9</td>
      <td>1.8</td>
      <td>50.0</td>
      <td>1.023</td>
      <td>0.47</td>
    </tr>
    <tr>
      <th>9</th>
      <td>DeAndre Jordan C</td>
      <td>36</td>
      <td>2.0</td>
      <td>11.0</td>
      <td>3.9</td>
      <td>1.5</td>
      <td>2.9</td>
      <td>4.4</td>
      <td>0.7</td>
      <td>0.2</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.7</td>
      <td>1.5</td>
      <td>49.1</td>
      <td>1.6</td>
      <td>2.6</td>
      <td>62.4</td>
      <td>1.527</td>
      <td>0.62</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Justin Holiday SF</td>
      <td>53</td>
      <td>9.0</td>
      <td>14.7</td>
      <td>3.9</td>
      <td>0.2</td>
      <td>1.1</td>
      <td>1.3</td>
      <td>1.1</td>
      <td>0.6</td>
      <td>...</td>
      <td>2.2</td>
      <td>39.8</td>
      <td>0.1</td>
      <td>0.1</td>
      <td>75.0</td>
      <td>0.6</td>
      <td>1.0</td>
      <td>56.4</td>
      <td>1.191</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Collin Gillespie G</td>
      <td>24</td>
      <td>0.0</td>
      <td>9.4</td>
      <td>3.6</td>
      <td>0.0</td>
      <td>0.8</td>
      <td>0.9</td>
      <td>1.1</td>
      <td>0.5</td>
      <td>...</td>
      <td>1.6</td>
      <td>39.5</td>
      <td>0.3</td>
      <td>0.5</td>
      <td>66.7</td>
      <td>0.7</td>
      <td>1.3</td>
      <td>54.8</td>
      <td>1.261</td>
      <td>0.57</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Zeke Nnaji PF</td>
      <td>53</td>
      <td>0.0</td>
      <td>9.8</td>
      <td>3.2</td>
      <td>1.1</td>
      <td>1.0</td>
      <td>2.1</td>
      <td>0.6</td>
      <td>0.2</td>
      <td>...</td>
      <td>0.4</td>
      <td>23.8</td>
      <td>0.8</td>
      <td>1.1</td>
      <td>71.2</td>
      <td>1.1</td>
      <td>2.2</td>
      <td>48.7</td>
      <td>1.243</td>
      <td>0.47</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Jalen Pickett G</td>
      <td>24</td>
      <td>0.0</td>
      <td>4.8</td>
      <td>1.6</td>
      <td>0.0</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.8</td>
      <td>0.1</td>
      <td>...</td>
      <td>1.0</td>
      <td>34.8</td>
      <td>0.1</td>
      <td>0.2</td>
      <td>75.0</td>
      <td>0.3</td>
      <td>0.4</td>
      <td>60.0</td>
      <td>1.182</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Hunter Tyson F</td>
      <td>14</td>
      <td>0.0</td>
      <td>2.9</td>
      <td>1.3</td>
      <td>0.1</td>
      <td>0.6</td>
      <td>0.6</td>
      <td>0.1</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.9</td>
      <td>33.3</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.2</td>
      <td>0.4</td>
      <td>60.0</td>
      <td>1.059</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Jay Huff C</td>
      <td>17</td>
      <td>0.0</td>
      <td>2.6</td>
      <td>1.1</td>
      <td>0.1</td>
      <td>0.5</td>
      <td>0.6</td>
      <td>0.1</td>
      <td>0.1</td>
      <td>...</td>
      <td>0.5</td>
      <td>33.3</td>
      <td>0.1</td>
      <td>0.1</td>
      <td>100.0</td>
      <td>0.2</td>
      <td>0.2</td>
      <td>100.0</td>
      <td>1.462</td>
      <td>0.65</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Braxton Key F</td>
      <td>19</td>
      <td>0.0</td>
      <td>3.1</td>
      <td>1.1</td>
      <td>0.2</td>
      <td>0.7</td>
      <td>0.8</td>
      <td>0.5</td>
      <td>0.1</td>
      <td>...</td>
      <td>0.3</td>
      <td>40.0</td>
      <td>0.2</td>
      <td>0.3</td>
      <td>66.7</td>
      <td>0.3</td>
      <td>0.6</td>
      <td>41.7</td>
      <td>1.176</td>
      <td>0.47</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Total</td>
      <td>77</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>114.3</td>
      <td>10.8</td>
      <td>33.7</td>
      <td>44.4</td>
      <td>29.3</td>
      <td>7.0</td>
      <td>...</td>
      <td>31.0</td>
      <td>37.1</td>
      <td>15.3</td>
      <td>20.0</td>
      <td>76.4</td>
      <td>32.3</td>
      <td>57.7</td>
      <td>55.9</td>
      <td>1.289</td>
      <td>0.56</td>
    </tr>
  </tbody>
</table>
<p>18 rows × 28 columns</p>
</div>




```python
denTable.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>BLK</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>18.000000</td>
      <td>17.000000</td>
      <td>17.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>...</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>52.055556</td>
      <td>22.647059</td>
      <td>17.176471</td>
      <td>13.933333</td>
      <td>1.316667</td>
      <td>4.138889</td>
      <td>5.444444</td>
      <td>3.588889</td>
      <td>0.866667</td>
      <td>0.666667</td>
      <td>...</td>
      <td>3.861111</td>
      <td>33.350000</td>
      <td>1.838889</td>
      <td>2.444444</td>
      <td>70.988889</td>
      <td>3.905556</td>
      <td>6.983333</td>
      <td>56.888889</td>
      <td>1.256778</td>
      <td>0.548889</td>
    </tr>
    <tr>
      <th>std</th>
      <td>23.976636</td>
      <td>31.646369</td>
      <td>11.611230</td>
      <td>26.084275</td>
      <td>2.501823</td>
      <td>7.727654</td>
      <td>10.183679</td>
      <td>6.838377</td>
      <td>1.578905</td>
      <td>1.247114</td>
      <td>...</td>
      <td>7.018978</td>
      <td>9.651044</td>
      <td>3.555301</td>
      <td>4.615603</td>
      <td>20.914838</td>
      <td>7.479263</td>
      <td>13.281001</td>
      <td>12.255750</td>
      <td>0.137729</td>
      <td>0.053456</td>
    </tr>
    <tr>
      <th>min</th>
      <td>14.000000</td>
      <td>0.000000</td>
      <td>2.600000</td>
      <td>1.100000</td>
      <td>0.000000</td>
      <td>0.500000</td>
      <td>0.500000</td>
      <td>0.100000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.200000</td>
      <td>0.200000</td>
      <td>41.700000</td>
      <td>1.023000</td>
      <td>0.470000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>27.000000</td>
      <td>0.000000</td>
      <td>9.400000</td>
      <td>3.300000</td>
      <td>0.125000</td>
      <td>0.850000</td>
      <td>0.975000</td>
      <td>0.725000</td>
      <td>0.200000</td>
      <td>0.100000</td>
      <td>...</td>
      <td>0.925000</td>
      <td>30.600000</td>
      <td>0.225000</td>
      <td>0.350000</td>
      <td>67.025000</td>
      <td>0.625000</td>
      <td>1.075000</td>
      <td>49.850000</td>
      <td>1.184000</td>
      <td>0.510000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>53.500000</td>
      <td>2.000000</td>
      <td>14.700000</td>
      <td>5.700000</td>
      <td>0.550000</td>
      <td>1.750000</td>
      <td>2.250000</td>
      <td>1.100000</td>
      <td>0.500000</td>
      <td>0.400000</td>
      <td>...</td>
      <td>1.950000</td>
      <td>35.600000</td>
      <td>0.850000</td>
      <td>1.250000</td>
      <td>74.550000</td>
      <td>1.700000</td>
      <td>3.100000</td>
      <td>55.500000</td>
      <td>1.248000</td>
      <td>0.555000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>74.750000</td>
      <td>54.000000</td>
      <td>31.600000</td>
      <td>13.025000</td>
      <td>1.250000</td>
      <td>3.275000</td>
      <td>4.325000</td>
      <td>3.150000</td>
      <td>0.750000</td>
      <td>0.675000</td>
      <td>...</td>
      <td>3.300000</td>
      <td>39.725000</td>
      <td>1.325000</td>
      <td>1.600000</td>
      <td>81.775000</td>
      <td>3.450000</td>
      <td>6.300000</td>
      <td>60.000000</td>
      <td>1.293500</td>
      <td>0.587500</td>
    </tr>
    <tr>
      <th>max</th>
      <td>77.000000</td>
      <td>76.000000</td>
      <td>34.600000</td>
      <td>114.300000</td>
      <td>10.800000</td>
      <td>33.700000</td>
      <td>44.400000</td>
      <td>29.300000</td>
      <td>7.000000</td>
      <td>5.500000</td>
      <td>...</td>
      <td>31.000000</td>
      <td>41.900000</td>
      <td>15.300000</td>
      <td>20.000000</td>
      <td>100.000000</td>
      <td>32.300000</td>
      <td>57.700000</td>
      <td>100.000000</td>
      <td>1.527000</td>
      <td>0.650000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 27 columns</p>
</div>




```python
denTable.columns
```




    Index(['Name', 'GP', 'GS', 'MIN', 'PTS', 'OR', 'DR', 'REB', 'AST', 'STL',
           'BLK', 'TO', 'PF', 'AST/TO', 'FGM', 'FGA', 'FG%', '3PM', '3PA', '3P%',
           'FTM', 'FTA', 'FT%', '2PM', '2PA', '2P%', 'SC-EFF', 'SH-EFF'],
          dtype='object')




```python
denTable.shape
```




    (18, 28)




```python
denTable.dtypes
```




    Name       object
    GP          int64
    GS        float64
    MIN       float64
    PTS       float64
    OR        float64
    DR        float64
    REB       float64
    AST       float64
    STL       float64
    BLK       float64
    TO        float64
    PF        float64
    AST/TO    float64
    FGM       float64
    FGA       float64
    FG%       float64
    3PM       float64
    3PA       float64
    3P%       float64
    FTM       float64
    FTA       float64
    FT%       float64
    2PM       float64
    2PA       float64
    2P%       float64
    SC-EFF    float64
    SH-EFF    float64
    dtype: object



### Only ranking these teams based on the top 15 players since that is the size of the smallest team


```python
denTable = denTable.drop(denTable.index[16:])
```


```python
denTable.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Nikola Jokic C</td>
      <td>74</td>
      <td>74.0</td>
      <td>34.6</td>
      <td>26.5</td>
      <td>2.8</td>
      <td>9.6</td>
      <td>12.4</td>
      <td>9.0</td>
      <td>1.3</td>
      <td>...</td>
      <td>3.0</td>
      <td>34.2</td>
      <td>4.6</td>
      <td>5.6</td>
      <td>82.3</td>
      <td>9.4</td>
      <td>15.0</td>
      <td>62.6</td>
      <td>1.469</td>
      <td>0.61</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jamal Murray PG</td>
      <td>54</td>
      <td>54.0</td>
      <td>32.1</td>
      <td>20.9</td>
      <td>0.7</td>
      <td>3.4</td>
      <td>4.1</td>
      <td>6.7</td>
      <td>1.0</td>
      <td>...</td>
      <td>5.6</td>
      <td>41.9</td>
      <td>2.7</td>
      <td>3.2</td>
      <td>85.5</td>
      <td>5.6</td>
      <td>11.1</td>
      <td>50.3</td>
      <td>1.253</td>
      <td>0.54</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Michael Porter Jr. SF</td>
      <td>76</td>
      <td>76.0</td>
      <td>31.8</td>
      <td>16.8</td>
      <td>1.3</td>
      <td>5.8</td>
      <td>7.1</td>
      <td>1.5</td>
      <td>0.5</td>
      <td>...</td>
      <td>6.9</td>
      <td>40.0</td>
      <td>1.1</td>
      <td>1.4</td>
      <td>82.5</td>
      <td>3.7</td>
      <td>6.5</td>
      <td>57.7</td>
      <td>1.262</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Aaron Gordon PF</td>
      <td>70</td>
      <td>70.0</td>
      <td>31.6</td>
      <td>14.0</td>
      <td>2.4</td>
      <td>4.1</td>
      <td>6.5</td>
      <td>3.4</td>
      <td>0.8</td>
      <td>...</td>
      <td>1.9</td>
      <td>29.1</td>
      <td>2.4</td>
      <td>3.7</td>
      <td>65.3</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>61.6</td>
      <td>1.406</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Reggie Jackson PG</td>
      <td>77</td>
      <td>23.0</td>
      <td>22.2</td>
      <td>10.1</td>
      <td>0.4</td>
      <td>1.5</td>
      <td>1.9</td>
      <td>3.8</td>
      <td>0.5</td>
      <td>...</td>
      <td>3.4</td>
      <td>36.4</td>
      <td>0.9</td>
      <td>1.2</td>
      <td>80.2</td>
      <td>2.7</td>
      <td>5.7</td>
      <td>47.7</td>
      <td>1.110</td>
      <td>0.50</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
denTable.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>Collin Gillespie G</td>
      <td>24</td>
      <td>0.0</td>
      <td>9.4</td>
      <td>3.6</td>
      <td>0.0</td>
      <td>0.8</td>
      <td>0.9</td>
      <td>1.1</td>
      <td>0.5</td>
      <td>...</td>
      <td>1.6</td>
      <td>39.5</td>
      <td>0.3</td>
      <td>0.5</td>
      <td>66.7</td>
      <td>0.7</td>
      <td>1.3</td>
      <td>54.8</td>
      <td>1.261</td>
      <td>0.57</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Zeke Nnaji PF</td>
      <td>53</td>
      <td>0.0</td>
      <td>9.8</td>
      <td>3.2</td>
      <td>1.1</td>
      <td>1.0</td>
      <td>2.1</td>
      <td>0.6</td>
      <td>0.2</td>
      <td>...</td>
      <td>0.4</td>
      <td>23.8</td>
      <td>0.8</td>
      <td>1.1</td>
      <td>71.2</td>
      <td>1.1</td>
      <td>2.2</td>
      <td>48.7</td>
      <td>1.243</td>
      <td>0.47</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Jalen Pickett G</td>
      <td>24</td>
      <td>0.0</td>
      <td>4.8</td>
      <td>1.6</td>
      <td>0.0</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.8</td>
      <td>0.1</td>
      <td>...</td>
      <td>1.0</td>
      <td>34.8</td>
      <td>0.1</td>
      <td>0.2</td>
      <td>75.0</td>
      <td>0.3</td>
      <td>0.4</td>
      <td>60.0</td>
      <td>1.182</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Hunter Tyson F</td>
      <td>14</td>
      <td>0.0</td>
      <td>2.9</td>
      <td>1.3</td>
      <td>0.1</td>
      <td>0.6</td>
      <td>0.6</td>
      <td>0.1</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.9</td>
      <td>33.3</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.2</td>
      <td>0.4</td>
      <td>60.0</td>
      <td>1.059</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Jay Huff C</td>
      <td>17</td>
      <td>0.0</td>
      <td>2.6</td>
      <td>1.1</td>
      <td>0.1</td>
      <td>0.5</td>
      <td>0.6</td>
      <td>0.1</td>
      <td>0.1</td>
      <td>...</td>
      <td>0.5</td>
      <td>33.3</td>
      <td>0.1</td>
      <td>0.1</td>
      <td>100.0</td>
      <td>0.2</td>
      <td>0.2</td>
      <td>100.0</td>
      <td>1.462</td>
      <td>0.65</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
denTable.sample()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>15</th>
      <td>Jay Huff C</td>
      <td>17</td>
      <td>0.0</td>
      <td>2.6</td>
      <td>1.1</td>
      <td>0.1</td>
      <td>0.5</td>
      <td>0.6</td>
      <td>0.1</td>
      <td>0.1</td>
      <td>...</td>
      <td>0.5</td>
      <td>33.3</td>
      <td>0.1</td>
      <td>0.1</td>
      <td>100.0</td>
      <td>0.2</td>
      <td>0.2</td>
      <td>100.0</td>
      <td>1.462</td>
      <td>0.65</td>
    </tr>
  </tbody>
</table>
<p>1 rows × 28 columns</p>
</div>




```python
denTable.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 16 entries, 0 to 15
    Data columns (total 28 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   Name    16 non-null     object 
     1   GP      16 non-null     int64  
     2   GS      16 non-null     float64
     3   MIN     16 non-null     float64
     4   PTS     16 non-null     float64
     5   OR      16 non-null     float64
     6   DR      16 non-null     float64
     7   REB     16 non-null     float64
     8   AST     16 non-null     float64
     9   STL     16 non-null     float64
     10  BLK     16 non-null     float64
     11  TO      16 non-null     float64
     12  PF      16 non-null     float64
     13  AST/TO  16 non-null     float64
     14  FGM     16 non-null     float64
     15  FGA     16 non-null     float64
     16  FG%     16 non-null     float64
     17  3PM     16 non-null     float64
     18  3PA     16 non-null     float64
     19  3P%     16 non-null     float64
     20  FTM     16 non-null     float64
     21  FTA     16 non-null     float64
     22  FT%     16 non-null     float64
     23  2PM     16 non-null     float64
     24  2PA     16 non-null     float64
     25  2P%     16 non-null     float64
     26  SC-EFF  16 non-null     float64
     27  SH-EFF  16 non-null     float64
    dtypes: float64(26), int64(1), object(1)
    memory usage: 3.6+ KB


### Additional Data Analysis

#### Total of average player PPG's for Denver


```python
den_totAvgPts = (denTable['PTS'].sum())
den_totAvgPts
```




    135.39999999999998



#### Players with most/least games played


```python
denGames = denTable['GP'].max()
print(denTable.loc[denTable['GP'] == denGames, 'Name'], denGames)
```

    4    Reggie Jackson PG
    6    Christian Braun G
    Name: Name, dtype: object 77



```python
denGames1 = denTable['GP'].min()
print(denTable.loc[denTable['GP'] == denGames1, 'Name'], denGames1)
```

    14    Hunter Tyson F
    Name: Name, dtype: object 14


#### Players with most/least fouls averaged per game


```python
denFouls = denTable['PF'].max()
print(denTable.loc[denTable['PF'] == denFouls, 'Name'], denFouls)
```

    0    Nikola Jokic C
    Name: Name, dtype: object 2.4



```python
denFouls1 = denTable['PF'].min()
print(denTable.loc[denTable['PF'] == denFouls1, 'Name'], denFouls1)
```

    13    Jalen Pickett G
    15         Jay Huff C
    Name: Name, dtype: object 0.5



```python
denBar = plt.bar(denTable['Name'], denTable['PF'])
plt.title('Players/Their Avg Fouls/Game')
plt.xlabel('Players')
plt.ylabel('Avg Fouls/Game')
plt.xticks(rotation = 90)
denBar
```




    <BarContainer object of 16 artists>




    
![png](output_59_1.png)
    


#### Player averaging the most 3's


```python
denThrees = denTable['3PM'].max()
print(denTable.loc[denTable['3PM'] == denThrees, 'Name'], denThrees)
```

    2    Michael Porter Jr. SF
    Name: Name, dtype: object 2.8


#### Player averaging the least 3's


```python
denThrees1 = denTable['3PM'].min()
print(denTable.loc[denTable['3PM'] == denThrees1, 'Name'], denThrees1)
```

    9    DeAndre Jordan C
    Name: Name, dtype: object 0.0


#### Total Defensive Stats: Def Rebounds + Blocks + Steals


```python
DefReb1 = denTable['DR'].sum()
Blocks1 = denTable['BLK'].sum()
Steals1 = denTable['STL'].sum()
DefStats1 = (DefReb1 + Blocks1 + Steals1)
DefStats
```




    65.7



## Boston Celtics Data Scraping

### Initial Team Analysis


```python
url3 = 'https://www.espn.com/nba/team/stats/_/name/bos'
```


```python
table3 = pd.io.html.read_html(url3)
table3
```




    [                    Name
     0        Jayson Tatum SF
     1        Jaylen Brown SG
     2   Kristaps Porzingis C
     3       Derrick White PG
     4        Jrue Holiday PG
     5          Sam Hauser SF
     6           Al Horford C
     7    Payton Pritchard PG
     8          Luke Kornet C
     9        Neemias Queta C
     10     Oshae Brissett SF
     11    Xavier Tillman F *
     12       Drew Peterson F
     13     Svi Mykhailiuk SG
     14    Lamar Stevens PF *
     15     Dalano Banton G *
     16         JD Davison SG
     17    Jaden Springer G *
     18        Jordan Walsh G
     19                 Total,
         GP    GS   MIN    PTS    OR    DR   REB   AST  STL  BLK    TO    PF  \
     0   71  71.0  35.8   27.2   0.9   7.3   8.3   4.9  1.0  0.6   2.5   2.0   
     1   67  67.0  33.6   23.2   1.2   4.4   5.5   3.6  1.2  0.5   2.3   2.6   
     2   54  54.0  29.9   20.4   1.7   5.3   7.0   2.0  0.7  1.9   1.6   2.8   
     3   70  70.0  32.7   15.4   0.7   3.6   4.3   5.2  1.0  1.2   1.5   2.1   
     4   65  65.0  33.1   12.6   1.2   4.3   5.5   4.9  0.9  0.8   1.8   1.6   
     5   73  10.0  21.4    8.8   0.5   2.9   3.4   0.9  0.5  0.3   0.4   1.3   
     6   62  31.0  27.1    8.7   1.3   5.1   6.4   2.6  0.6  1.0   0.7   1.5   
     7   76   3.0  21.7    8.6   0.9   2.3   3.2   3.1  0.4  0.1   0.7   1.3   
     8   57   5.0  15.2    5.1   1.8   2.2   4.0   1.0  0.4  1.0   0.4   1.3   
     9   26   0.0  11.4    4.6   1.8   2.3   4.1   0.5  0.4  0.6   0.4   1.8   
     10  50   1.0  11.5    3.6   1.0   1.8   2.8   0.8  0.3  0.1   0.3   1.0   
     11  14   1.0  13.9    3.1   0.8   2.1   2.9   0.9  0.4  0.4   0.2   0.8   
     12   1   0.0   3.0    3.0   0.0   0.0   0.0   1.0  0.0  0.0   0.0   1.0   
     13  35   0.0   8.5    3.0   0.2   0.8   1.0   0.7  0.3  0.0   0.3   0.4   
     14  19   1.0   6.4    2.8   0.6   1.0   1.6   0.4  0.3  0.3   0.5   0.7   
     15  24   1.0   7.1    2.3   0.5   1.0   1.5   0.8  0.2  0.1   0.4   0.8   
     16   6   0.0   1.8    1.3   0.2   0.3   0.5   0.2  0.0  0.0   0.0   0.2   
     17  13   0.0   5.5    1.1   0.6   0.2   0.8   0.4  0.2  0.2   0.3   0.8   
     18   6   0.0   6.7    1.0   0.5   1.7   2.2   0.7  0.3  0.2   0.3   1.0   
     19  76   NaN   NaN  121.0  10.7  35.8  46.5  26.8  6.6  6.5  11.3  16.4   
     
         AST/TO  
     0      1.9  
     1      1.6  
     2      1.3  
     3      3.4  
     4      2.7  
     5      2.2  
     6      3.5  
     7      4.5  
     8      2.8  
     9      1.4  
     10     2.7  
     11     4.3  
     12     inf  
     13     2.7  
     14     0.9  
     15     1.9  
     16     inf  
     17     1.3  
     18     2.0  
     19     2.4  ,
                         Name
     0        Jayson Tatum SF
     1        Jaylen Brown SG
     2   Kristaps Porzingis C
     3       Derrick White PG
     4        Jrue Holiday PG
     5          Sam Hauser SF
     6           Al Horford C
     7    Payton Pritchard PG
     8          Luke Kornet C
     9        Neemias Queta C
     10     Oshae Brissett SF
     11    Xavier Tillman F *
     12       Drew Peterson F
     13     Svi Mykhailiuk SG
     14    Lamar Stevens PF *
     15     Dalano Banton G *
     16         JD Davison SG
     17    Jaden Springer G *
     18        Jordan Walsh G
     19                 Total,
          FGM   FGA    FG%   3PM   3PA    3P%   FTM   FTA    FT%   2PM   2PA   2P%  \
     0    9.2  19.4   47.4   3.1   8.3   38.0   5.6   6.8   83.5   6.1  11.2  54.3   
     1    9.0  18.0   50.1   2.1   5.9   35.8   3.1   4.4   70.1   6.9  12.1  57.1   
     2    6.9  13.4   51.6   1.9   5.2   37.1   4.6   5.3   86.1   5.0   8.1  60.9   
     3    5.4  11.6   46.6   2.7   6.8   40.2   1.9   2.1   90.0   2.7   4.8  55.6   
     4    4.8  10.0   47.9   2.0   4.7   43.3   0.9   1.1   83.3   2.8   5.3  52.0   
     5    3.1   6.6   46.6   2.5   5.7   43.8   0.2   0.2   88.2   0.6   0.9  63.2   
     6    3.3   6.5   51.1   1.7   4.0   42.3   0.4   0.5   89.3   1.6   2.5  65.0   
     7    3.2   7.1   44.7   1.7   4.5   37.7   0.6   0.7   80.8   1.5   2.6  56.8   
     8    2.2   3.1   69.1   0.0   0.0    0.0   0.8   0.9   89.8   2.2   3.1  69.1   
     9    2.0   3.2   61.4   0.0   0.0    0.0   0.7   0.9   70.8   2.0   3.2  61.4   
     10   1.2   2.6   45.0   0.3   1.0   28.8   0.9   1.4   64.8   0.9   1.6  55.7   
     11   1.3   2.6   48.6   0.2   1.2   17.6   0.3   0.4   66.7   1.1   1.4  75.0   
     12   1.0   1.0  100.0   1.0   1.0  100.0   0.0   0.0    0.0   0.0   0.0   0.0   
     13   1.0   2.8   37.1   0.8   2.3   35.0   0.1   0.2   57.1   0.2   0.5  47.1   
     14   1.1   2.4   46.7   0.2   0.4   37.5   0.4   0.6   72.7   0.9   1.9  48.6   
     15   0.8   2.1   37.3   0.1   0.7   12.5   0.7   0.8   80.0   0.7   1.5  48.6   
     16   0.3   0.5   66.7   0.3   0.5   66.7   0.3   0.3  100.0   0.0   0.0   0.0   
     17   0.5   1.4   33.3   0.0   0.5    0.0   0.2   0.2  100.0   0.5   0.8  54.5   
     18   0.5   1.3   37.5   0.0   0.7    0.0   0.0   0.0    0.0   0.5   0.7  75.0   
     19  43.8  90.1   48.7  16.6  42.5   39.0  16.8  20.7   81.1  27.3  47.6  57.3   
     
         SC-EFF  SH-EFF  
     0    1.400    0.55  
     1    1.290    0.56  
     2    1.520    0.59  
     3    1.333    0.58  
     4    1.254    0.58  
     5    1.339    0.65  
     6    1.342    0.64  
     7    1.211    0.57  
     8    1.629    0.69  
     9    1.434    0.61  
     10   1.366    0.51  
     11   1.162    0.53  
     12   3.000    1.50  
     13   1.072    0.52  
     14   1.178    0.50  
     15   1.098    0.39  
     16   2.667    1.00  
     17   0.778    0.33  
     18   0.750    0.38  
     19   1.343    0.58  ]




```python
celtstats = table3[0]
celtstats1 = table3[1]
celtstats2 = table3[3]
```


```python
celt = pd.merge(celtstats, celtstats1, right_index = True, left_index = True)
celtTable = pd.merge(celt, celtstats2, right_index = True, left_index = True)
celtTable
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jayson Tatum SF</td>
      <td>71</td>
      <td>71.0</td>
      <td>35.8</td>
      <td>27.2</td>
      <td>0.9</td>
      <td>7.3</td>
      <td>8.3</td>
      <td>4.9</td>
      <td>1.0</td>
      <td>...</td>
      <td>8.3</td>
      <td>38.0</td>
      <td>5.6</td>
      <td>6.8</td>
      <td>83.5</td>
      <td>6.1</td>
      <td>11.2</td>
      <td>54.3</td>
      <td>1.400</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jaylen Brown SG</td>
      <td>67</td>
      <td>67.0</td>
      <td>33.6</td>
      <td>23.2</td>
      <td>1.2</td>
      <td>4.4</td>
      <td>5.5</td>
      <td>3.6</td>
      <td>1.2</td>
      <td>...</td>
      <td>5.9</td>
      <td>35.8</td>
      <td>3.1</td>
      <td>4.4</td>
      <td>70.1</td>
      <td>6.9</td>
      <td>12.1</td>
      <td>57.1</td>
      <td>1.290</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kristaps Porzingis C</td>
      <td>54</td>
      <td>54.0</td>
      <td>29.9</td>
      <td>20.4</td>
      <td>1.7</td>
      <td>5.3</td>
      <td>7.0</td>
      <td>2.0</td>
      <td>0.7</td>
      <td>...</td>
      <td>5.2</td>
      <td>37.1</td>
      <td>4.6</td>
      <td>5.3</td>
      <td>86.1</td>
      <td>5.0</td>
      <td>8.1</td>
      <td>60.9</td>
      <td>1.520</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Derrick White PG</td>
      <td>70</td>
      <td>70.0</td>
      <td>32.7</td>
      <td>15.4</td>
      <td>0.7</td>
      <td>3.6</td>
      <td>4.3</td>
      <td>5.2</td>
      <td>1.0</td>
      <td>...</td>
      <td>6.8</td>
      <td>40.2</td>
      <td>1.9</td>
      <td>2.1</td>
      <td>90.0</td>
      <td>2.7</td>
      <td>4.8</td>
      <td>55.6</td>
      <td>1.333</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jrue Holiday PG</td>
      <td>65</td>
      <td>65.0</td>
      <td>33.1</td>
      <td>12.6</td>
      <td>1.2</td>
      <td>4.3</td>
      <td>5.5</td>
      <td>4.9</td>
      <td>0.9</td>
      <td>...</td>
      <td>4.7</td>
      <td>43.3</td>
      <td>0.9</td>
      <td>1.1</td>
      <td>83.3</td>
      <td>2.8</td>
      <td>5.3</td>
      <td>52.0</td>
      <td>1.254</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Sam Hauser SF</td>
      <td>73</td>
      <td>10.0</td>
      <td>21.4</td>
      <td>8.8</td>
      <td>0.5</td>
      <td>2.9</td>
      <td>3.4</td>
      <td>0.9</td>
      <td>0.5</td>
      <td>...</td>
      <td>5.7</td>
      <td>43.8</td>
      <td>0.2</td>
      <td>0.2</td>
      <td>88.2</td>
      <td>0.6</td>
      <td>0.9</td>
      <td>63.2</td>
      <td>1.339</td>
      <td>0.65</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Al Horford C</td>
      <td>62</td>
      <td>31.0</td>
      <td>27.1</td>
      <td>8.7</td>
      <td>1.3</td>
      <td>5.1</td>
      <td>6.4</td>
      <td>2.6</td>
      <td>0.6</td>
      <td>...</td>
      <td>4.0</td>
      <td>42.3</td>
      <td>0.4</td>
      <td>0.5</td>
      <td>89.3</td>
      <td>1.6</td>
      <td>2.5</td>
      <td>65.0</td>
      <td>1.342</td>
      <td>0.64</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Payton Pritchard PG</td>
      <td>76</td>
      <td>3.0</td>
      <td>21.7</td>
      <td>8.6</td>
      <td>0.9</td>
      <td>2.3</td>
      <td>3.2</td>
      <td>3.1</td>
      <td>0.4</td>
      <td>...</td>
      <td>4.5</td>
      <td>37.7</td>
      <td>0.6</td>
      <td>0.7</td>
      <td>80.8</td>
      <td>1.5</td>
      <td>2.6</td>
      <td>56.8</td>
      <td>1.211</td>
      <td>0.57</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Luke Kornet C</td>
      <td>57</td>
      <td>5.0</td>
      <td>15.2</td>
      <td>5.1</td>
      <td>1.8</td>
      <td>2.2</td>
      <td>4.0</td>
      <td>1.0</td>
      <td>0.4</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.8</td>
      <td>0.9</td>
      <td>89.8</td>
      <td>2.2</td>
      <td>3.1</td>
      <td>69.1</td>
      <td>1.629</td>
      <td>0.69</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Neemias Queta C</td>
      <td>26</td>
      <td>0.0</td>
      <td>11.4</td>
      <td>4.6</td>
      <td>1.8</td>
      <td>2.3</td>
      <td>4.1</td>
      <td>0.5</td>
      <td>0.4</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.7</td>
      <td>0.9</td>
      <td>70.8</td>
      <td>2.0</td>
      <td>3.2</td>
      <td>61.4</td>
      <td>1.434</td>
      <td>0.61</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Oshae Brissett SF</td>
      <td>50</td>
      <td>1.0</td>
      <td>11.5</td>
      <td>3.6</td>
      <td>1.0</td>
      <td>1.8</td>
      <td>2.8</td>
      <td>0.8</td>
      <td>0.3</td>
      <td>...</td>
      <td>1.0</td>
      <td>28.8</td>
      <td>0.9</td>
      <td>1.4</td>
      <td>64.8</td>
      <td>0.9</td>
      <td>1.6</td>
      <td>55.7</td>
      <td>1.366</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Xavier Tillman F *</td>
      <td>14</td>
      <td>1.0</td>
      <td>13.9</td>
      <td>3.1</td>
      <td>0.8</td>
      <td>2.1</td>
      <td>2.9</td>
      <td>0.9</td>
      <td>0.4</td>
      <td>...</td>
      <td>1.2</td>
      <td>17.6</td>
      <td>0.3</td>
      <td>0.4</td>
      <td>66.7</td>
      <td>1.1</td>
      <td>1.4</td>
      <td>75.0</td>
      <td>1.162</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Drew Peterson F</td>
      <td>1</td>
      <td>0.0</td>
      <td>3.0</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>1.0</td>
      <td>100.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>3.000</td>
      <td>1.50</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Svi Mykhailiuk SG</td>
      <td>35</td>
      <td>0.0</td>
      <td>8.5</td>
      <td>3.0</td>
      <td>0.2</td>
      <td>0.8</td>
      <td>1.0</td>
      <td>0.7</td>
      <td>0.3</td>
      <td>...</td>
      <td>2.3</td>
      <td>35.0</td>
      <td>0.1</td>
      <td>0.2</td>
      <td>57.1</td>
      <td>0.2</td>
      <td>0.5</td>
      <td>47.1</td>
      <td>1.072</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Lamar Stevens PF *</td>
      <td>19</td>
      <td>1.0</td>
      <td>6.4</td>
      <td>2.8</td>
      <td>0.6</td>
      <td>1.0</td>
      <td>1.6</td>
      <td>0.4</td>
      <td>0.3</td>
      <td>...</td>
      <td>0.4</td>
      <td>37.5</td>
      <td>0.4</td>
      <td>0.6</td>
      <td>72.7</td>
      <td>0.9</td>
      <td>1.9</td>
      <td>48.6</td>
      <td>1.178</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Dalano Banton G *</td>
      <td>24</td>
      <td>1.0</td>
      <td>7.1</td>
      <td>2.3</td>
      <td>0.5</td>
      <td>1.0</td>
      <td>1.5</td>
      <td>0.8</td>
      <td>0.2</td>
      <td>...</td>
      <td>0.7</td>
      <td>12.5</td>
      <td>0.7</td>
      <td>0.8</td>
      <td>80.0</td>
      <td>0.7</td>
      <td>1.5</td>
      <td>48.6</td>
      <td>1.098</td>
      <td>0.39</td>
    </tr>
    <tr>
      <th>16</th>
      <td>JD Davison SG</td>
      <td>6</td>
      <td>0.0</td>
      <td>1.8</td>
      <td>1.3</td>
      <td>0.2</td>
      <td>0.3</td>
      <td>0.5</td>
      <td>0.2</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.5</td>
      <td>66.7</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>100.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>2.667</td>
      <td>1.00</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Jaden Springer G *</td>
      <td>13</td>
      <td>0.0</td>
      <td>5.5</td>
      <td>1.1</td>
      <td>0.6</td>
      <td>0.2</td>
      <td>0.8</td>
      <td>0.4</td>
      <td>0.2</td>
      <td>...</td>
      <td>0.5</td>
      <td>0.0</td>
      <td>0.2</td>
      <td>0.2</td>
      <td>100.0</td>
      <td>0.5</td>
      <td>0.8</td>
      <td>54.5</td>
      <td>0.778</td>
      <td>0.33</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Jordan Walsh G</td>
      <td>6</td>
      <td>0.0</td>
      <td>6.7</td>
      <td>1.0</td>
      <td>0.5</td>
      <td>1.7</td>
      <td>2.2</td>
      <td>0.7</td>
      <td>0.3</td>
      <td>...</td>
      <td>0.7</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.5</td>
      <td>0.7</td>
      <td>75.0</td>
      <td>0.750</td>
      <td>0.38</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Total</td>
      <td>76</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>121.0</td>
      <td>10.7</td>
      <td>35.8</td>
      <td>46.5</td>
      <td>26.8</td>
      <td>6.6</td>
      <td>...</td>
      <td>42.5</td>
      <td>39.0</td>
      <td>16.8</td>
      <td>20.7</td>
      <td>81.1</td>
      <td>27.3</td>
      <td>47.6</td>
      <td>57.3</td>
      <td>1.343</td>
      <td>0.58</td>
    </tr>
  </tbody>
</table>
<p>20 rows × 28 columns</p>
</div>




```python
celtTable.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>BLK</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>20.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>...</td>
      <td>20.000000</td>
      <td>20.00000</td>
      <td>20.00000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
      <td>20.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>43.250000</td>
      <td>20.000000</td>
      <td>17.173684</td>
      <td>13.840000</td>
      <td>1.355000</td>
      <td>4.220000</td>
      <td>5.575000</td>
      <td>3.070000</td>
      <td>0.785000</td>
      <td>0.790000</td>
      <td>...</td>
      <td>4.795000</td>
      <td>32.76500</td>
      <td>1.92500</td>
      <td>2.375000</td>
      <td>72.715000</td>
      <td>3.175000</td>
      <td>5.490000</td>
      <td>52.860000</td>
      <td>1.408300</td>
      <td>0.613000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>27.057201</td>
      <td>28.934793</td>
      <td>11.705784</td>
      <td>26.389898</td>
      <td>2.259594</td>
      <td>7.680502</td>
      <td>9.896511</td>
      <td>5.824729</td>
      <td>1.407975</td>
      <td>1.430458</td>
      <td>...</td>
      <td>9.246876</td>
      <td>24.22231</td>
      <td>3.82552</td>
      <td>4.705414</td>
      <td>27.259789</td>
      <td>6.010944</td>
      <td>10.505582</td>
      <td>19.692489</td>
      <td>0.534648</td>
      <td>0.249211</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>1.800000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.200000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.00000</td>
      <td>0.00000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.750000</td>
      <td>0.330000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>17.750000</td>
      <td>0.000000</td>
      <td>6.900000</td>
      <td>2.950000</td>
      <td>0.500000</td>
      <td>1.000000</td>
      <td>1.575000</td>
      <td>0.700000</td>
      <td>0.300000</td>
      <td>0.100000</td>
      <td>...</td>
      <td>0.650000</td>
      <td>16.32500</td>
      <td>0.27500</td>
      <td>0.275000</td>
      <td>69.250000</td>
      <td>0.575000</td>
      <td>0.875000</td>
      <td>51.150000</td>
      <td>1.174000</td>
      <td>0.517500</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>52.000000</td>
      <td>1.000000</td>
      <td>13.900000</td>
      <td>4.850000</td>
      <td>0.850000</td>
      <td>2.250000</td>
      <td>3.300000</td>
      <td>0.950000</td>
      <td>0.400000</td>
      <td>0.350000</td>
      <td>...</td>
      <td>1.750000</td>
      <td>37.30000</td>
      <td>0.65000</td>
      <td>0.750000</td>
      <td>80.950000</td>
      <td>1.300000</td>
      <td>2.200000</td>
      <td>56.250000</td>
      <td>1.336000</td>
      <td>0.575000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>67.750000</td>
      <td>42.500000</td>
      <td>28.500000</td>
      <td>13.300000</td>
      <td>1.225000</td>
      <td>4.325000</td>
      <td>5.500000</td>
      <td>3.225000</td>
      <td>0.750000</td>
      <td>0.850000</td>
      <td>...</td>
      <td>5.325000</td>
      <td>40.72500</td>
      <td>1.15000</td>
      <td>1.575000</td>
      <td>88.475000</td>
      <td>2.725000</td>
      <td>4.925000</td>
      <td>61.850000</td>
      <td>1.408500</td>
      <td>0.617500</td>
    </tr>
    <tr>
      <th>max</th>
      <td>76.000000</td>
      <td>71.000000</td>
      <td>35.800000</td>
      <td>121.000000</td>
      <td>10.700000</td>
      <td>35.800000</td>
      <td>46.500000</td>
      <td>26.800000</td>
      <td>6.600000</td>
      <td>6.500000</td>
      <td>...</td>
      <td>42.500000</td>
      <td>100.00000</td>
      <td>16.80000</td>
      <td>20.700000</td>
      <td>100.000000</td>
      <td>27.300000</td>
      <td>47.600000</td>
      <td>75.000000</td>
      <td>3.000000</td>
      <td>1.500000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 27 columns</p>
</div>




```python
celtTable.columns
```




    Index(['Name', 'GP', 'GS', 'MIN', 'PTS', 'OR', 'DR', 'REB', 'AST', 'STL',
           'BLK', 'TO', 'PF', 'AST/TO', 'FGM', 'FGA', 'FG%', '3PM', '3PA', '3P%',
           'FTM', 'FTA', 'FT%', '2PM', '2PA', '2P%', 'SC-EFF', 'SH-EFF'],
          dtype='object')




```python
celtTable.shape
```




    (20, 28)




```python
celtTable.dtypes
```




    Name       object
    GP          int64
    GS        float64
    MIN       float64
    PTS       float64
    OR        float64
    DR        float64
    REB       float64
    AST       float64
    STL       float64
    BLK       float64
    TO        float64
    PF        float64
    AST/TO    float64
    FGM       float64
    FGA       float64
    FG%       float64
    3PM       float64
    3PA       float64
    3P%       float64
    FTM       float64
    FTA       float64
    FT%       float64
    2PM       float64
    2PA       float64
    2P%       float64
    SC-EFF    float64
    SH-EFF    float64
    dtype: object



### Only ranking these teams based on the top 15 players since that is the size of the smallest team


```python
celtTable = celtTable.drop(celtTable.index[16:])
```


```python
celtTable.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jayson Tatum SF</td>
      <td>71</td>
      <td>71.0</td>
      <td>35.8</td>
      <td>27.2</td>
      <td>0.9</td>
      <td>7.3</td>
      <td>8.3</td>
      <td>4.9</td>
      <td>1.0</td>
      <td>...</td>
      <td>8.3</td>
      <td>38.0</td>
      <td>5.6</td>
      <td>6.8</td>
      <td>83.5</td>
      <td>6.1</td>
      <td>11.2</td>
      <td>54.3</td>
      <td>1.400</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jaylen Brown SG</td>
      <td>67</td>
      <td>67.0</td>
      <td>33.6</td>
      <td>23.2</td>
      <td>1.2</td>
      <td>4.4</td>
      <td>5.5</td>
      <td>3.6</td>
      <td>1.2</td>
      <td>...</td>
      <td>5.9</td>
      <td>35.8</td>
      <td>3.1</td>
      <td>4.4</td>
      <td>70.1</td>
      <td>6.9</td>
      <td>12.1</td>
      <td>57.1</td>
      <td>1.290</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kristaps Porzingis C</td>
      <td>54</td>
      <td>54.0</td>
      <td>29.9</td>
      <td>20.4</td>
      <td>1.7</td>
      <td>5.3</td>
      <td>7.0</td>
      <td>2.0</td>
      <td>0.7</td>
      <td>...</td>
      <td>5.2</td>
      <td>37.1</td>
      <td>4.6</td>
      <td>5.3</td>
      <td>86.1</td>
      <td>5.0</td>
      <td>8.1</td>
      <td>60.9</td>
      <td>1.520</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Derrick White PG</td>
      <td>70</td>
      <td>70.0</td>
      <td>32.7</td>
      <td>15.4</td>
      <td>0.7</td>
      <td>3.6</td>
      <td>4.3</td>
      <td>5.2</td>
      <td>1.0</td>
      <td>...</td>
      <td>6.8</td>
      <td>40.2</td>
      <td>1.9</td>
      <td>2.1</td>
      <td>90.0</td>
      <td>2.7</td>
      <td>4.8</td>
      <td>55.6</td>
      <td>1.333</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jrue Holiday PG</td>
      <td>65</td>
      <td>65.0</td>
      <td>33.1</td>
      <td>12.6</td>
      <td>1.2</td>
      <td>4.3</td>
      <td>5.5</td>
      <td>4.9</td>
      <td>0.9</td>
      <td>...</td>
      <td>4.7</td>
      <td>43.3</td>
      <td>0.9</td>
      <td>1.1</td>
      <td>83.3</td>
      <td>2.8</td>
      <td>5.3</td>
      <td>52.0</td>
      <td>1.254</td>
      <td>0.58</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
celtTable.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>Xavier Tillman F *</td>
      <td>14</td>
      <td>1.0</td>
      <td>13.9</td>
      <td>3.1</td>
      <td>0.8</td>
      <td>2.1</td>
      <td>2.9</td>
      <td>0.9</td>
      <td>0.4</td>
      <td>...</td>
      <td>1.2</td>
      <td>17.6</td>
      <td>0.3</td>
      <td>0.4</td>
      <td>66.7</td>
      <td>1.1</td>
      <td>1.4</td>
      <td>75.0</td>
      <td>1.162</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Drew Peterson F</td>
      <td>1</td>
      <td>0.0</td>
      <td>3.0</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>1.0</td>
      <td>100.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>3.000</td>
      <td>1.50</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Svi Mykhailiuk SG</td>
      <td>35</td>
      <td>0.0</td>
      <td>8.5</td>
      <td>3.0</td>
      <td>0.2</td>
      <td>0.8</td>
      <td>1.0</td>
      <td>0.7</td>
      <td>0.3</td>
      <td>...</td>
      <td>2.3</td>
      <td>35.0</td>
      <td>0.1</td>
      <td>0.2</td>
      <td>57.1</td>
      <td>0.2</td>
      <td>0.5</td>
      <td>47.1</td>
      <td>1.072</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Lamar Stevens PF *</td>
      <td>19</td>
      <td>1.0</td>
      <td>6.4</td>
      <td>2.8</td>
      <td>0.6</td>
      <td>1.0</td>
      <td>1.6</td>
      <td>0.4</td>
      <td>0.3</td>
      <td>...</td>
      <td>0.4</td>
      <td>37.5</td>
      <td>0.4</td>
      <td>0.6</td>
      <td>72.7</td>
      <td>0.9</td>
      <td>1.9</td>
      <td>48.6</td>
      <td>1.178</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Dalano Banton G *</td>
      <td>24</td>
      <td>1.0</td>
      <td>7.1</td>
      <td>2.3</td>
      <td>0.5</td>
      <td>1.0</td>
      <td>1.5</td>
      <td>0.8</td>
      <td>0.2</td>
      <td>...</td>
      <td>0.7</td>
      <td>12.5</td>
      <td>0.7</td>
      <td>0.8</td>
      <td>80.0</td>
      <td>0.7</td>
      <td>1.5</td>
      <td>48.6</td>
      <td>1.098</td>
      <td>0.39</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
celtTable.sample()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10</th>
      <td>Oshae Brissett SF</td>
      <td>50</td>
      <td>1.0</td>
      <td>11.5</td>
      <td>3.6</td>
      <td>1.0</td>
      <td>1.8</td>
      <td>2.8</td>
      <td>0.8</td>
      <td>0.3</td>
      <td>...</td>
      <td>1.0</td>
      <td>28.8</td>
      <td>0.9</td>
      <td>1.4</td>
      <td>64.8</td>
      <td>0.9</td>
      <td>1.6</td>
      <td>55.7</td>
      <td>1.366</td>
      <td>0.51</td>
    </tr>
  </tbody>
</table>
<p>1 rows × 28 columns</p>
</div>




```python
celtTable.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 16 entries, 0 to 15
    Data columns (total 28 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   Name    16 non-null     object 
     1   GP      16 non-null     int64  
     2   GS      16 non-null     float64
     3   MIN     16 non-null     float64
     4   PTS     16 non-null     float64
     5   OR      16 non-null     float64
     6   DR      16 non-null     float64
     7   REB     16 non-null     float64
     8   AST     16 non-null     float64
     9   STL     16 non-null     float64
     10  BLK     16 non-null     float64
     11  TO      16 non-null     float64
     12  PF      16 non-null     float64
     13  AST/TO  16 non-null     float64
     14  FGM     16 non-null     float64
     15  FGA     16 non-null     float64
     16  FG%     16 non-null     float64
     17  3PM     16 non-null     float64
     18  3PA     16 non-null     float64
     19  3P%     16 non-null     float64
     20  FTM     16 non-null     float64
     21  FTA     16 non-null     float64
     22  FT%     16 non-null     float64
     23  2PM     16 non-null     float64
     24  2PA     16 non-null     float64
     25  2P%     16 non-null     float64
     26  SC-EFF  16 non-null     float64
     27  SH-EFF  16 non-null     float64
    dtypes: float64(26), int64(1), object(1)
    memory usage: 3.6+ KB


### Additional Data Analysis

#### Total of average player PPG's for Denver


```python
celt_totAvgPts = celtTable['PTS'].sum()
celt_totAvgPts
```




    152.39999999999998



#### Players with most/least games played


```python
celtGames = celtTable['GP'].max()
print(celtTable.loc[celtTable['GP'] == celtGames, 'Name'], celtGames)
```

    7    Payton Pritchard PG
    Name: Name, dtype: object 76



```python
celtGames1 = celtTable['GP'].min()
print(celtTable.loc[celtTable['GP'] == celtGames1, 'Name'], celtGames1)
```

    12    Drew Peterson F
    Name: Name, dtype: object 1


#### Players with most/least fouls averaged per game


```python
celtFouls = celtTable['PF'].max()
print(celtTable.loc[celtTable['PF'] == celtFouls, 'Name'], celtFouls)
```

    2    Kristaps Porzingis C
    Name: Name, dtype: object 2.8



```python
celtFouls1 = celtTable['PF'].min()
print(celtTable.loc[celtTable['PF'] == celtFouls1, 'Name'], celtFouls1)
```

    13    Svi Mykhailiuk SG
    Name: Name, dtype: object 0.4



```python
celtBar = plt.bar(celtTable['Name'], celtTable['PF'])
plt.title('Players/Their Avg Fouls/Game')
plt.xlabel('Players')
plt.ylabel('Avg Fouls/Game')
plt.xticks(rotation = 90)
celtBar
```




    <BarContainer object of 16 artists>




    
![png](output_91_1.png)
    


#### Player averaging the most 3's


```python
celtThrees = celtTable['3PM'].max()
print(celtTable.loc[celtTable['3PM'] == celtThrees, 'Name'], celtThrees)
```

    0    Jayson Tatum SF
    Name: Name, dtype: object 3.1


#### Player averaging the least 3's


```python
celtThrees1 = celtTable['3PM'].min()
print(celtTable.loc[celtTable['3PM'] == celtThrees1, 'Name'], celtThrees1)
```

    8      Luke Kornet C
    9    Neemias Queta C
    Name: Name, dtype: object 0.0


#### Total Defensive Stats: Def Rebounds + Blocks + Steals


```python
DefReb2 = denTable['DR'].sum()
Blocks2 = denTable['BLK'].sum()
Steals2 = denTable['STL'].sum()
DefStats2 = (DefReb2 + Blocks2 + Steals2)
DefStats2
```




    55.0



## Golden State Warriors Data Scraping

### Initial Team Analysis


```python
url4 = 'https://www.espn.com/nba/team/stats/_/name/gs'
```


```python
table4 = pd.io.html.read_html(url4)
table4
```




    [                      Name
     0         Stephen Curry PG
     1         Klay Thompson SG
     2      Jonathan Kuminga PF
     3        Andrew Wiggins SF
     4            Chris Paul PG
     5     Brandin Podziemski G
     6        Draymond Green PF
     7           Moses Moody SG
     8           Dario Saric PF
     9   Trayce Jackson-Davis F
     10       Gary Payton II SG
     11          Kevon Looney F
     12       Lester Quinones G
     13            Gui Santos F
     14          Cory Joseph PG
     15      Jerome Robinson SG
     16           Pat Spencer G
     17         Usman Garuba PF
     18                   Total,
         GP    GS   MIN    PTS    OR    DR   REB   AST  STL  BLK    TO    PF  \
     0   70  70.0  32.6   26.4   0.5   3.9   4.4   5.0  0.7  0.3   2.8   1.6   
     1   72  58.0  29.6   17.4   0.4   2.8   3.3   2.3  0.6  0.4   1.5   1.7   
     2   70  44.0  26.3   16.3   1.3   3.5   4.8   2.1  0.7  0.5   1.7   2.3   
     3   67  55.0  27.0   13.0   1.6   3.0   4.5   1.7  0.6  0.5   1.2   2.0   
     4   52  15.0  26.1    9.2   0.3   3.5   3.9   6.8  1.1  0.1   1.2   1.8   
     5   68  27.0  26.7    9.1   1.6   4.2   5.8   3.7  0.9  0.2   1.2   1.7   
     6   51  48.0  26.8    8.8   1.4   5.8   7.3   6.0  1.0  0.8   2.4   3.0   
     7   60   8.0  17.4    8.2   1.0   2.0   3.0   0.8  0.7  0.4   0.7   1.3   
     8   62   9.0  17.4    8.1   1.1   3.3   4.5   2.3  0.5  0.1   1.2   1.8   
     9   62  10.0  16.0    7.8   1.9   2.9   4.8   1.2  0.4  1.0   0.7   1.6   
     10  41   0.0  15.3    5.2   1.1   1.5   2.6   1.1  0.9  0.4   0.6   1.7   
     11  69  36.0  16.3    4.5   2.0   3.8   5.7   1.9  0.4  0.3   0.7   2.2   
     12  34   0.0  11.0    4.4   0.6   1.5   2.1   1.0  0.2  0.1   0.5   1.2   
     13  20   0.0   7.9    3.4   0.8   1.5   2.2   0.6  0.2  0.1   0.4   1.0   
     14  26   0.0  11.4    2.4   0.2   0.9   1.2   1.6  0.2  0.1   0.5   1.0   
     15  20   0.0   3.7    1.3   0.1   0.3   0.3   0.3  0.0  0.2   0.1   0.3   
     16   3   0.0   2.0    0.7   0.0   0.0   0.0   0.7  0.0  0.0   0.0   0.0   
     17   3   0.0   2.7    0.0   0.3   0.0   0.3   0.3  0.3  0.0   0.0   0.7   
     18  76   NaN   NaN  118.0  12.3  34.5  46.8  29.2  6.9  4.3  13.7  19.7   
     
         AST/TO  
     0      1.8  
     1      1.5  
     2      1.3  
     3      1.4  
     4      5.6  
     5      3.0  
     6      2.5  
     7      1.2  
     8      1.9  
     9      1.8  
     10     1.8  
     11     2.7  
     12     2.1  
     13     1.6  
     14     3.5  
     15     2.5  
     16     inf  
     17     inf  
     18     2.1  ,
                           Name
     0         Stephen Curry PG
     1         Klay Thompson SG
     2      Jonathan Kuminga PF
     3        Andrew Wiggins SF
     4            Chris Paul PG
     5     Brandin Podziemski G
     6        Draymond Green PF
     7           Moses Moody SG
     8           Dario Saric PF
     9   Trayce Jackson-Davis F
     10       Gary Payton II SG
     11          Kevon Looney F
     12       Lester Quinones G
     13            Gui Santos F
     14          Cory Joseph PG
     15      Jerome Robinson SG
     16           Pat Spencer G
     17         Usman Garuba PF
     18                   Total,
          FGM   FGA    FG%   3PM   3PA   3P%   FTM   FTA   FT%   2PM   2PA    2P%  \
     0    8.8  19.5   44.9   4.8  11.8  40.4   4.1   4.4  92.6   4.0   7.7   51.8   
     1    6.2  14.5   42.9   3.4   8.9  38.4   1.6   1.7  91.9   2.8   5.6   49.9   
     2    6.3  11.8   52.9   0.7   2.3  31.6   3.1   4.1  74.0   5.5   9.6   57.9   
     3    4.9  10.9   45.1   1.2   3.5  35.8   1.9   2.6  74.3   3.7   7.4   49.5   
     4    3.5   7.9   44.4   1.4   3.5  38.6   0.8   1.0  82.0   2.2   4.4   49.1   
     5    3.6   8.1   44.5   1.2   3.2  37.2   0.7   1.1  61.8   2.4   4.9   49.4   
     6    3.5   6.9   50.0   0.9   2.3  38.1   1.1   1.4  75.0   2.6   4.6   56.0   
     7    3.0   6.4   46.9   1.1   3.1  35.9   1.1   1.4  80.5   1.9   3.3   57.1   
     8    2.9   6.1   46.5   1.2   3.1  37.6   1.2   1.4  85.4   1.7   3.0   55.6   
     9    3.4   4.7   70.7   0.0   0.0   0.0   1.0   1.9  56.5   3.4   4.7   71.0   
     10   2.2   4.1   54.8   0.4   1.2  34.0   0.3   0.5  60.0   1.8   2.9   63.6   
     11   1.9   3.1   59.8   0.0   0.0   0.0   0.8   1.1  68.8   1.9   3.1   60.1   
     12   1.5   3.7   40.2   0.9   2.4  37.5   0.5   0.8  66.7   0.6   1.4   44.7   
     13   1.1   2.2   50.0   0.5   1.1  40.9   0.7   0.8  93.3   0.7   1.1   59.1   
     14   0.9   2.5   35.9   0.5   1.6  31.0   0.2   0.3  57.1   0.4   0.8   45.5   
     15   0.5   1.6   29.0   0.1   0.9  11.8   0.3   0.5  60.0   0.4   0.7   50.0   
     16   0.3   0.3  100.0   0.0   0.0   0.0   0.0   0.0   0.0   0.3   0.3  100.0   
     17   0.0   0.3    0.0   0.0   0.0   0.0   0.0   0.0   0.0   0.0   0.3    0.0   
     18  43.7  92.0   47.5  14.7  39.1  37.7  15.8  20.2  78.1  29.0  53.0   54.8   
     
         SC-EFF  SH-EFF  
     0    1.352    0.57  
     1    1.202    0.55  
     2    1.377    0.56  
     3    1.190    0.51  
     4    1.160    0.53  
     5    1.124    0.52  
     6    1.281    0.56  
     7    1.283    0.55  
     8    1.320    0.56  
     9    1.636    0.71  
     10   1.268    0.60  
     11   1.444    0.60  
     12   1.181    0.52  
     13   1.523    0.60  
     14   0.984    0.46  
     15   0.839    0.32  
     16   2.000    1.00  
     17   0.000    0.00  
     18   1.282    0.56  ]




```python
warstats = table4[0]
warstats1 = table4[1]
warstats2 = table4[3]
```


```python
war = pd.merge(warstats, warstats1, right_index = True, left_index = True)
warTable = pd.merge(war, warstats2, right_index = True, left_index = True)
warTable
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Stephen Curry PG</td>
      <td>70</td>
      <td>70.0</td>
      <td>32.6</td>
      <td>26.4</td>
      <td>0.5</td>
      <td>3.9</td>
      <td>4.4</td>
      <td>5.0</td>
      <td>0.7</td>
      <td>...</td>
      <td>11.8</td>
      <td>40.4</td>
      <td>4.1</td>
      <td>4.4</td>
      <td>92.6</td>
      <td>4.0</td>
      <td>7.7</td>
      <td>51.8</td>
      <td>1.352</td>
      <td>0.57</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Klay Thompson SG</td>
      <td>72</td>
      <td>58.0</td>
      <td>29.6</td>
      <td>17.4</td>
      <td>0.4</td>
      <td>2.8</td>
      <td>3.3</td>
      <td>2.3</td>
      <td>0.6</td>
      <td>...</td>
      <td>8.9</td>
      <td>38.4</td>
      <td>1.6</td>
      <td>1.7</td>
      <td>91.9</td>
      <td>2.8</td>
      <td>5.6</td>
      <td>49.9</td>
      <td>1.202</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jonathan Kuminga PF</td>
      <td>70</td>
      <td>44.0</td>
      <td>26.3</td>
      <td>16.3</td>
      <td>1.3</td>
      <td>3.5</td>
      <td>4.8</td>
      <td>2.1</td>
      <td>0.7</td>
      <td>...</td>
      <td>2.3</td>
      <td>31.6</td>
      <td>3.1</td>
      <td>4.1</td>
      <td>74.0</td>
      <td>5.5</td>
      <td>9.6</td>
      <td>57.9</td>
      <td>1.377</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Andrew Wiggins SF</td>
      <td>67</td>
      <td>55.0</td>
      <td>27.0</td>
      <td>13.0</td>
      <td>1.6</td>
      <td>3.0</td>
      <td>4.5</td>
      <td>1.7</td>
      <td>0.6</td>
      <td>...</td>
      <td>3.5</td>
      <td>35.8</td>
      <td>1.9</td>
      <td>2.6</td>
      <td>74.3</td>
      <td>3.7</td>
      <td>7.4</td>
      <td>49.5</td>
      <td>1.190</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Chris Paul PG</td>
      <td>52</td>
      <td>15.0</td>
      <td>26.1</td>
      <td>9.2</td>
      <td>0.3</td>
      <td>3.5</td>
      <td>3.9</td>
      <td>6.8</td>
      <td>1.1</td>
      <td>...</td>
      <td>3.5</td>
      <td>38.6</td>
      <td>0.8</td>
      <td>1.0</td>
      <td>82.0</td>
      <td>2.2</td>
      <td>4.4</td>
      <td>49.1</td>
      <td>1.160</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Brandin Podziemski G</td>
      <td>68</td>
      <td>27.0</td>
      <td>26.7</td>
      <td>9.1</td>
      <td>1.6</td>
      <td>4.2</td>
      <td>5.8</td>
      <td>3.7</td>
      <td>0.9</td>
      <td>...</td>
      <td>3.2</td>
      <td>37.2</td>
      <td>0.7</td>
      <td>1.1</td>
      <td>61.8</td>
      <td>2.4</td>
      <td>4.9</td>
      <td>49.4</td>
      <td>1.124</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Draymond Green PF</td>
      <td>51</td>
      <td>48.0</td>
      <td>26.8</td>
      <td>8.8</td>
      <td>1.4</td>
      <td>5.8</td>
      <td>7.3</td>
      <td>6.0</td>
      <td>1.0</td>
      <td>...</td>
      <td>2.3</td>
      <td>38.1</td>
      <td>1.1</td>
      <td>1.4</td>
      <td>75.0</td>
      <td>2.6</td>
      <td>4.6</td>
      <td>56.0</td>
      <td>1.281</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Moses Moody SG</td>
      <td>60</td>
      <td>8.0</td>
      <td>17.4</td>
      <td>8.2</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>0.8</td>
      <td>0.7</td>
      <td>...</td>
      <td>3.1</td>
      <td>35.9</td>
      <td>1.1</td>
      <td>1.4</td>
      <td>80.5</td>
      <td>1.9</td>
      <td>3.3</td>
      <td>57.1</td>
      <td>1.283</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Dario Saric PF</td>
      <td>62</td>
      <td>9.0</td>
      <td>17.4</td>
      <td>8.1</td>
      <td>1.1</td>
      <td>3.3</td>
      <td>4.5</td>
      <td>2.3</td>
      <td>0.5</td>
      <td>...</td>
      <td>3.1</td>
      <td>37.6</td>
      <td>1.2</td>
      <td>1.4</td>
      <td>85.4</td>
      <td>1.7</td>
      <td>3.0</td>
      <td>55.6</td>
      <td>1.320</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Trayce Jackson-Davis F</td>
      <td>62</td>
      <td>10.0</td>
      <td>16.0</td>
      <td>7.8</td>
      <td>1.9</td>
      <td>2.9</td>
      <td>4.8</td>
      <td>1.2</td>
      <td>0.4</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.9</td>
      <td>56.5</td>
      <td>3.4</td>
      <td>4.7</td>
      <td>71.0</td>
      <td>1.636</td>
      <td>0.71</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Gary Payton II SG</td>
      <td>41</td>
      <td>0.0</td>
      <td>15.3</td>
      <td>5.2</td>
      <td>1.1</td>
      <td>1.5</td>
      <td>2.6</td>
      <td>1.1</td>
      <td>0.9</td>
      <td>...</td>
      <td>1.2</td>
      <td>34.0</td>
      <td>0.3</td>
      <td>0.5</td>
      <td>60.0</td>
      <td>1.8</td>
      <td>2.9</td>
      <td>63.6</td>
      <td>1.268</td>
      <td>0.60</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Kevon Looney F</td>
      <td>69</td>
      <td>36.0</td>
      <td>16.3</td>
      <td>4.5</td>
      <td>2.0</td>
      <td>3.8</td>
      <td>5.7</td>
      <td>1.9</td>
      <td>0.4</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.8</td>
      <td>1.1</td>
      <td>68.8</td>
      <td>1.9</td>
      <td>3.1</td>
      <td>60.1</td>
      <td>1.444</td>
      <td>0.60</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Lester Quinones G</td>
      <td>34</td>
      <td>0.0</td>
      <td>11.0</td>
      <td>4.4</td>
      <td>0.6</td>
      <td>1.5</td>
      <td>2.1</td>
      <td>1.0</td>
      <td>0.2</td>
      <td>...</td>
      <td>2.4</td>
      <td>37.5</td>
      <td>0.5</td>
      <td>0.8</td>
      <td>66.7</td>
      <td>0.6</td>
      <td>1.4</td>
      <td>44.7</td>
      <td>1.181</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Gui Santos F</td>
      <td>20</td>
      <td>0.0</td>
      <td>7.9</td>
      <td>3.4</td>
      <td>0.8</td>
      <td>1.5</td>
      <td>2.2</td>
      <td>0.6</td>
      <td>0.2</td>
      <td>...</td>
      <td>1.1</td>
      <td>40.9</td>
      <td>0.7</td>
      <td>0.8</td>
      <td>93.3</td>
      <td>0.7</td>
      <td>1.1</td>
      <td>59.1</td>
      <td>1.523</td>
      <td>0.60</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Cory Joseph PG</td>
      <td>26</td>
      <td>0.0</td>
      <td>11.4</td>
      <td>2.4</td>
      <td>0.2</td>
      <td>0.9</td>
      <td>1.2</td>
      <td>1.6</td>
      <td>0.2</td>
      <td>...</td>
      <td>1.6</td>
      <td>31.0</td>
      <td>0.2</td>
      <td>0.3</td>
      <td>57.1</td>
      <td>0.4</td>
      <td>0.8</td>
      <td>45.5</td>
      <td>0.984</td>
      <td>0.46</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Jerome Robinson SG</td>
      <td>20</td>
      <td>0.0</td>
      <td>3.7</td>
      <td>1.3</td>
      <td>0.1</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.9</td>
      <td>11.8</td>
      <td>0.3</td>
      <td>0.5</td>
      <td>60.0</td>
      <td>0.4</td>
      <td>0.7</td>
      <td>50.0</td>
      <td>0.839</td>
      <td>0.32</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Pat Spencer G</td>
      <td>3</td>
      <td>0.0</td>
      <td>2.0</td>
      <td>0.7</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.7</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>100.0</td>
      <td>2.000</td>
      <td>1.00</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Usman Garuba PF</td>
      <td>3</td>
      <td>0.0</td>
      <td>2.7</td>
      <td>0.0</td>
      <td>0.3</td>
      <td>0.0</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.3</td>
      <td>0.0</td>
      <td>0.000</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Total</td>
      <td>76</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>118.0</td>
      <td>12.3</td>
      <td>34.5</td>
      <td>46.8</td>
      <td>29.2</td>
      <td>6.9</td>
      <td>...</td>
      <td>39.1</td>
      <td>37.7</td>
      <td>15.8</td>
      <td>20.2</td>
      <td>78.1</td>
      <td>29.0</td>
      <td>53.0</td>
      <td>54.8</td>
      <td>1.282</td>
      <td>0.56</td>
    </tr>
  </tbody>
</table>
<p>19 rows × 28 columns</p>
</div>




```python
warTable.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>BLK</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>19.000000</td>
      <td>18.000000</td>
      <td>18.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>...</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
      <td>19.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>48.736842</td>
      <td>21.111111</td>
      <td>17.566667</td>
      <td>13.905263</td>
      <td>1.500000</td>
      <td>4.152632</td>
      <td>5.657895</td>
      <td>3.610526</td>
      <td>0.857895</td>
      <td>0.515789</td>
      <td>...</td>
      <td>4.631579</td>
      <td>27.710526</td>
      <td>1.852632</td>
      <td>2.378947</td>
      <td>66.210526</td>
      <td>3.436842</td>
      <td>6.252632</td>
      <td>53.952632</td>
      <td>1.234000</td>
      <td>0.541053</td>
    </tr>
    <tr>
      <th>std</th>
      <td>24.068980</td>
      <td>24.255718</td>
      <td>9.752888</td>
      <td>26.044161</td>
      <td>2.687213</td>
      <td>7.512313</td>
      <td>10.165591</td>
      <td>6.477559</td>
      <td>1.498635</td>
      <td>0.953510</td>
      <td>...</td>
      <td>8.869426</td>
      <td>15.954619</td>
      <td>3.532448</td>
      <td>4.479035</td>
      <td>26.146126</td>
      <td>6.359089</td>
      <td>11.625564</td>
      <td>17.904325</td>
      <td>0.386612</td>
      <td>0.182905</td>
    </tr>
    <tr>
      <th>min</th>
      <td>3.000000</td>
      <td>0.000000</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.300000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.300000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>30.000000</td>
      <td>0.000000</td>
      <td>11.100000</td>
      <td>3.900000</td>
      <td>0.350000</td>
      <td>1.500000</td>
      <td>2.150000</td>
      <td>0.900000</td>
      <td>0.250000</td>
      <td>0.100000</td>
      <td>...</td>
      <td>1.000000</td>
      <td>21.400000</td>
      <td>0.400000</td>
      <td>0.650000</td>
      <td>60.000000</td>
      <td>0.650000</td>
      <td>1.250000</td>
      <td>49.450000</td>
      <td>1.170500</td>
      <td>0.520000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>60.000000</td>
      <td>9.500000</td>
      <td>16.850000</td>
      <td>8.100000</td>
      <td>1.000000</td>
      <td>2.900000</td>
      <td>3.900000</td>
      <td>1.700000</td>
      <td>0.600000</td>
      <td>0.300000</td>
      <td>...</td>
      <td>2.300000</td>
      <td>35.900000</td>
      <td>0.800000</td>
      <td>1.100000</td>
      <td>74.000000</td>
      <td>1.900000</td>
      <td>3.300000</td>
      <td>54.800000</td>
      <td>1.281000</td>
      <td>0.560000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>68.500000</td>
      <td>42.000000</td>
      <td>26.600000</td>
      <td>11.100000</td>
      <td>1.500000</td>
      <td>3.650000</td>
      <td>4.800000</td>
      <td>3.000000</td>
      <td>0.800000</td>
      <td>0.450000</td>
      <td>...</td>
      <td>3.350000</td>
      <td>37.900000</td>
      <td>1.400000</td>
      <td>1.800000</td>
      <td>81.250000</td>
      <td>3.100000</td>
      <td>5.250000</td>
      <td>58.500000</td>
      <td>1.364500</td>
      <td>0.585000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>76.000000</td>
      <td>70.000000</td>
      <td>32.600000</td>
      <td>118.000000</td>
      <td>12.300000</td>
      <td>34.500000</td>
      <td>46.800000</td>
      <td>29.200000</td>
      <td>6.900000</td>
      <td>4.300000</td>
      <td>...</td>
      <td>39.100000</td>
      <td>40.900000</td>
      <td>15.800000</td>
      <td>20.200000</td>
      <td>93.300000</td>
      <td>29.000000</td>
      <td>53.000000</td>
      <td>100.000000</td>
      <td>2.000000</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 27 columns</p>
</div>




```python
warTable.columns
```




    Index(['Name', 'GP', 'GS', 'MIN', 'PTS', 'OR', 'DR', 'REB', 'AST', 'STL',
           'BLK', 'TO', 'PF', 'AST/TO', 'FGM', 'FGA', 'FG%', '3PM', '3PA', '3P%',
           'FTM', 'FTA', 'FT%', '2PM', '2PA', '2P%', 'SC-EFF', 'SH-EFF'],
          dtype='object')




```python
warTable.shape
```




    (19, 28)




```python
warTable.dtypes
```




    Name       object
    GP          int64
    GS        float64
    MIN       float64
    PTS       float64
    OR        float64
    DR        float64
    REB       float64
    AST       float64
    STL       float64
    BLK       float64
    TO        float64
    PF        float64
    AST/TO    float64
    FGM       float64
    FGA       float64
    FG%       float64
    3PM       float64
    3PA       float64
    3P%       float64
    FTM       float64
    FTA       float64
    FT%       float64
    2PM       float64
    2PA       float64
    2P%       float64
    SC-EFF    float64
    SH-EFF    float64
    dtype: object



### Only ranking these teams based on the top 15 players since that is the size of the smallest team


```python
warTable = warTable.drop(warTable.index[16:])
```


```python
warTable.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Stephen Curry PG</td>
      <td>70</td>
      <td>70.0</td>
      <td>32.6</td>
      <td>26.4</td>
      <td>0.5</td>
      <td>3.9</td>
      <td>4.4</td>
      <td>5.0</td>
      <td>0.7</td>
      <td>...</td>
      <td>11.8</td>
      <td>40.4</td>
      <td>4.1</td>
      <td>4.4</td>
      <td>92.6</td>
      <td>4.0</td>
      <td>7.7</td>
      <td>51.8</td>
      <td>1.352</td>
      <td>0.57</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Klay Thompson SG</td>
      <td>72</td>
      <td>58.0</td>
      <td>29.6</td>
      <td>17.4</td>
      <td>0.4</td>
      <td>2.8</td>
      <td>3.3</td>
      <td>2.3</td>
      <td>0.6</td>
      <td>...</td>
      <td>8.9</td>
      <td>38.4</td>
      <td>1.6</td>
      <td>1.7</td>
      <td>91.9</td>
      <td>2.8</td>
      <td>5.6</td>
      <td>49.9</td>
      <td>1.202</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jonathan Kuminga PF</td>
      <td>70</td>
      <td>44.0</td>
      <td>26.3</td>
      <td>16.3</td>
      <td>1.3</td>
      <td>3.5</td>
      <td>4.8</td>
      <td>2.1</td>
      <td>0.7</td>
      <td>...</td>
      <td>2.3</td>
      <td>31.6</td>
      <td>3.1</td>
      <td>4.1</td>
      <td>74.0</td>
      <td>5.5</td>
      <td>9.6</td>
      <td>57.9</td>
      <td>1.377</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Andrew Wiggins SF</td>
      <td>67</td>
      <td>55.0</td>
      <td>27.0</td>
      <td>13.0</td>
      <td>1.6</td>
      <td>3.0</td>
      <td>4.5</td>
      <td>1.7</td>
      <td>0.6</td>
      <td>...</td>
      <td>3.5</td>
      <td>35.8</td>
      <td>1.9</td>
      <td>2.6</td>
      <td>74.3</td>
      <td>3.7</td>
      <td>7.4</td>
      <td>49.5</td>
      <td>1.190</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Chris Paul PG</td>
      <td>52</td>
      <td>15.0</td>
      <td>26.1</td>
      <td>9.2</td>
      <td>0.3</td>
      <td>3.5</td>
      <td>3.9</td>
      <td>6.8</td>
      <td>1.1</td>
      <td>...</td>
      <td>3.5</td>
      <td>38.6</td>
      <td>0.8</td>
      <td>1.0</td>
      <td>82.0</td>
      <td>2.2</td>
      <td>4.4</td>
      <td>49.1</td>
      <td>1.160</td>
      <td>0.53</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
warTable.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>Kevon Looney F</td>
      <td>69</td>
      <td>36.0</td>
      <td>16.3</td>
      <td>4.5</td>
      <td>2.0</td>
      <td>3.8</td>
      <td>5.7</td>
      <td>1.9</td>
      <td>0.4</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.8</td>
      <td>1.1</td>
      <td>68.8</td>
      <td>1.9</td>
      <td>3.1</td>
      <td>60.1</td>
      <td>1.444</td>
      <td>0.60</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Lester Quinones G</td>
      <td>34</td>
      <td>0.0</td>
      <td>11.0</td>
      <td>4.4</td>
      <td>0.6</td>
      <td>1.5</td>
      <td>2.1</td>
      <td>1.0</td>
      <td>0.2</td>
      <td>...</td>
      <td>2.4</td>
      <td>37.5</td>
      <td>0.5</td>
      <td>0.8</td>
      <td>66.7</td>
      <td>0.6</td>
      <td>1.4</td>
      <td>44.7</td>
      <td>1.181</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Gui Santos F</td>
      <td>20</td>
      <td>0.0</td>
      <td>7.9</td>
      <td>3.4</td>
      <td>0.8</td>
      <td>1.5</td>
      <td>2.2</td>
      <td>0.6</td>
      <td>0.2</td>
      <td>...</td>
      <td>1.1</td>
      <td>40.9</td>
      <td>0.7</td>
      <td>0.8</td>
      <td>93.3</td>
      <td>0.7</td>
      <td>1.1</td>
      <td>59.1</td>
      <td>1.523</td>
      <td>0.60</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Cory Joseph PG</td>
      <td>26</td>
      <td>0.0</td>
      <td>11.4</td>
      <td>2.4</td>
      <td>0.2</td>
      <td>0.9</td>
      <td>1.2</td>
      <td>1.6</td>
      <td>0.2</td>
      <td>...</td>
      <td>1.6</td>
      <td>31.0</td>
      <td>0.2</td>
      <td>0.3</td>
      <td>57.1</td>
      <td>0.4</td>
      <td>0.8</td>
      <td>45.5</td>
      <td>0.984</td>
      <td>0.46</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Jerome Robinson SG</td>
      <td>20</td>
      <td>0.0</td>
      <td>3.7</td>
      <td>1.3</td>
      <td>0.1</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.9</td>
      <td>11.8</td>
      <td>0.3</td>
      <td>0.5</td>
      <td>60.0</td>
      <td>0.4</td>
      <td>0.7</td>
      <td>50.0</td>
      <td>0.839</td>
      <td>0.32</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
warTable.sample()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8</th>
      <td>Dario Saric PF</td>
      <td>62</td>
      <td>9.0</td>
      <td>17.4</td>
      <td>8.1</td>
      <td>1.1</td>
      <td>3.3</td>
      <td>4.5</td>
      <td>2.3</td>
      <td>0.5</td>
      <td>...</td>
      <td>3.1</td>
      <td>37.6</td>
      <td>1.2</td>
      <td>1.4</td>
      <td>85.4</td>
      <td>1.7</td>
      <td>3.0</td>
      <td>55.6</td>
      <td>1.32</td>
      <td>0.56</td>
    </tr>
  </tbody>
</table>
<p>1 rows × 28 columns</p>
</div>




```python
warTable.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 16 entries, 0 to 15
    Data columns (total 28 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   Name    16 non-null     object 
     1   GP      16 non-null     int64  
     2   GS      16 non-null     float64
     3   MIN     16 non-null     float64
     4   PTS     16 non-null     float64
     5   OR      16 non-null     float64
     6   DR      16 non-null     float64
     7   REB     16 non-null     float64
     8   AST     16 non-null     float64
     9   STL     16 non-null     float64
     10  BLK     16 non-null     float64
     11  TO      16 non-null     float64
     12  PF      16 non-null     float64
     13  AST/TO  16 non-null     float64
     14  FGM     16 non-null     float64
     15  FGA     16 non-null     float64
     16  FG%     16 non-null     float64
     17  3PM     16 non-null     float64
     18  3PA     16 non-null     float64
     19  3P%     16 non-null     float64
     20  FTM     16 non-null     float64
     21  FTA     16 non-null     float64
     22  FT%     16 non-null     float64
     23  2PM     16 non-null     float64
     24  2PA     16 non-null     float64
     25  2P%     16 non-null     float64
     26  SC-EFF  16 non-null     float64
     27  SH-EFF  16 non-null     float64
    dtypes: float64(26), int64(1), object(1)
    memory usage: 3.6+ KB


### Additional Data Analysis

#### Total of average player PPG's for Brooklyn


```python
war_totAvgPts = warTable['PTS'].sum()
war_totAvgPts
```




    145.5



#### Players with most/least games played


```python
warGames = warTable['GP'].max()
print(warTable.loc[warTable['GP'] == warGames, 'Name'], warGames)
```

    1    Klay Thompson SG
    Name: Name, dtype: object 72



```python
warGames1 = warTable['GP'].min()
print(warTable.loc[warTable['GP'] == warGames1, 'Name'], warGames1)
```

    13          Gui Santos F
    15    Jerome Robinson SG
    Name: Name, dtype: object 20


#### Players with most/least fouls averaged per game


```python
warFouls = warTable['PF'].max()
print(warTable.loc[warTable['PF'] == warFouls, 'Name'], warFouls)
```

    6    Draymond Green PF
    Name: Name, dtype: object 3.0



```python
warFouls1 = warTable['PF'].min()
print(warTable.loc[warTable['PF'] == warFouls1, 'Name'], warFouls1)
```

    15    Jerome Robinson SG
    Name: Name, dtype: object 0.3



```python
warBar = plt.bar(warTable['Name'], warTable['PF'])
plt.title('Players/Their Avg Fouls/Game')
plt.xlabel('Players')
plt.ylabel('Avg Fouls/Game')
plt.xticks(rotation = 90)
warBar
```




    <BarContainer object of 16 artists>




    
![png](output_123_1.png)
    


#### Player averaging the most 3's


```python
warThrees = warTable['3PM'].max()
print(warTable.loc[warTable['3PM'] == warThrees, 'Name'], warThrees)
```

    0    Stephen Curry PG
    Name: Name, dtype: object 4.8


#### Player averaging the least 3's


```python
warThrees1 = warTable['3PM'].min()
print(warTable.loc[warTable['3PM'] == warThrees1, 'Name'], warThrees1)
```

    9     Trayce Jackson-Davis F
    11            Kevon Looney F
    Name: Name, dtype: object 0.0


#### Total Defensive Stats: Def Rebounds + Blocks + Steals


```python
DefReb4 = warTable['DR'].sum()
Blocks4 = warTable['BLK'].sum()
Steals4 = warTable['STL'].sum()
DefStats4 = (DefReb4 + Blocks4 + Steals4)
DefStats4
```




    59.0



## Memphis Grizzlies Data Scraping

### Initial Team Analysis


```python
url5 = 'https://www.espn.com/nba/team/stats/_/name/mem'
```


```python
table5 = pd.io.html.read_html(url5)
table5
```




    [                      Name
     0             Ja Morant PG
     1          Desmond Bane SG
     2     Jaren Jackson Jr. PF
     3          Marcus Smart PG
     4             GG Jackson F
     5        Brandon Clarke PF
     6       Lamar Stevens PF *
     7          Luke Kennard SG
     8          Santi Aldama PF
     9      Scotty Pippen Jr. G
     10    Vince Williams Jr. G
     11          Jake LaRavia F
     12         David Roddy F *
     13      Jordan Goodwin G *
     14       Ziaire Williams F
     15         Derrick Rose PG
     16        Trey Jemison C *
     17      Xavier Tillman F *
     18        Jaylen Nowell SG
     19     Bismack Biyombo C *
     20         DeJon Jarreau F
     21       Jacob Gilyard G *
     22         John Konchar SG
     23             Matt Hurt F
     24      Maozinha Pereira F
     25        Wenyen Gabriel F
     26      Yuta Watanabe SF *
     27  Kenneth Lofton Jr. F *
     28     Tosan Evbuomwan F *
     29    Shaquille Harrison G
     30        Zavier Simpson G
     31                   Total,
         GP    GS   MIN    PTS    OR    DR   REB   AST  STL  BLK    TO    PF  \
     0    9   9.0  35.3   25.1   0.7   4.9   5.6   8.1  0.8  0.6   3.0   2.1   
     1   42  42.0  34.4   23.7   0.9   3.5   4.4   5.5  1.0  0.5   2.7   2.9   
     2   66  66.0  32.2   22.5   1.3   4.2   5.5   2.3  1.2  1.6   2.4   3.6   
     3   20  20.0  30.3   14.5   0.3   2.4   2.7   4.3  2.1  0.3   3.1   2.7   
     4   42  12.0  24.5   13.3   1.0   3.0   4.0   1.1  0.5  0.5   1.3   1.3   
     5    4   0.0  21.0   12.0   2.5   3.3   5.8   1.8  0.8  1.3   0.3   1.5   
     6   17   1.0  21.9   11.1   1.3   3.5   4.8   0.9  0.8  0.8   0.8   1.6   
     7   39  22.0  25.6   11.0   0.3   2.6   2.9   3.5  0.5  0.1   1.4   1.0   
     8   61  35.0  26.5   10.7   1.2   4.6   5.8   2.3  0.7  0.9   1.1   1.5   
     9   15  10.0  23.0   10.4   0.7   2.1   2.9   4.1  1.3  0.5   2.3   2.5   
     10  52  33.0  27.6   10.0   1.1   4.4   5.6   3.4  0.9  0.7   1.8   2.6   
     11  31   2.0  20.9    9.0   1.5   2.0   3.5   1.5  0.8  0.3   1.0   2.0   
     12  48  13.0  23.2    8.4   1.1   3.1   4.2   1.6  0.5  0.2   1.1   1.4   
     13  12   7.0  27.3    8.3   2.3   4.6   6.8   4.7  1.3  0.8   1.8   1.8   
     14  51  15.0  20.4    8.2   0.7   2.8   3.5   1.5  0.7  0.2   1.3   1.7   
     15  24   7.0  16.6    8.0   0.3   1.6   1.9   3.3  0.3  0.1   1.3   0.9   
     16  17   8.0  21.6    7.0   2.4   2.3   4.6   0.9  0.4  1.1   1.2   2.8   
     17  34  13.0  20.6    6.0   1.6   3.0   4.6   1.7  1.2  1.0   0.9   1.8   
     18   9   1.0  17.3    5.7   0.3   1.2   1.6   1.8  0.3  0.0   0.6   1.4   
     19  30  27.0  23.9    5.2   1.9   4.5   6.4   1.7  0.3  1.1   1.3   2.7   
     20   9   0.0  16.7    4.8   0.9   4.0   4.9   2.9  0.7  0.2   1.0   1.6   
     21  37  14.0  17.7    4.7   0.2   0.9   1.2   3.5  0.7  0.1   0.8   0.9   
     22  55  23.0  21.3    4.3   1.3   3.4   4.7   2.0  0.9  0.9   0.8   1.4   
     23   8   0.0  14.1    4.0   1.1   0.9   2.0   0.5  0.4  0.4   0.3   1.0   
     24   5   0.0  11.0    3.6   1.6   1.8   3.4   0.2  0.8  0.6   0.4   1.2   
     25   5   0.0  16.2    3.4   1.4   3.6   5.0   0.6  0.4  0.4   1.6   2.0   
     26   5   0.0  16.4    2.6   0.0   1.8   1.8   1.0  0.6  0.0   0.6   1.0   
     27  15   0.0   6.6    2.6   0.1   0.9   1.0   0.9  0.2  0.2   0.4   1.0   
     28   4   0.0  18.5    2.5   2.0   1.5   3.5   1.5  0.0  0.3   0.3   1.3   
     29   3   0.0   2.0    0.7   0.0   0.7   0.7   0.0  0.0  0.3   0.0   0.0   
     30   1   0.0   9.0    0.0   1.0   0.0   1.0   4.0  1.0  0.0   1.0   1.0   
     31  76   NaN   NaN  106.0  10.6  31.8  42.4  25.0  8.0  6.2  14.2  19.1   
     
         AST/TO  
     0      2.7  
     1      2.1  
     2      1.0  
     3      1.4  
     4      0.9  
     5      7.0  
     6      1.1  
     7      2.5  
     8      2.0  
     9      1.8  
     10     1.9  
     11     1.5  
     12     1.4  
     13     2.7  
     14     1.1  
     15     2.5  
     16     0.8  
     17     2.0  
     18     3.2  
     19     1.3  
     20     2.9  
     21     4.5  
     22     2.4  
     23     2.0  
     24     0.5  
     25     0.4  
     26     1.7  
     27     2.3  
     28     6.0  
     29     0.0  
     30     4.0  
     31     1.8  ,
                           Name
     0             Ja Morant PG
     1          Desmond Bane SG
     2     Jaren Jackson Jr. PF
     3          Marcus Smart PG
     4             GG Jackson F
     5        Brandon Clarke PF
     6       Lamar Stevens PF *
     7          Luke Kennard SG
     8          Santi Aldama PF
     9      Scotty Pippen Jr. G
     10    Vince Williams Jr. G
     11          Jake LaRavia F
     12         David Roddy F *
     13      Jordan Goodwin G *
     14       Ziaire Williams F
     15         Derrick Rose PG
     16        Trey Jemison C *
     17      Xavier Tillman F *
     18        Jaylen Nowell SG
     19     Bismack Biyombo C *
     20         DeJon Jarreau F
     21       Jacob Gilyard G *
     22         John Konchar SG
     23             Matt Hurt F
     24      Maozinha Pereira F
     25        Wenyen Gabriel F
     26      Yuta Watanabe SF *
     27  Kenneth Lofton Jr. F *
     28     Tosan Evbuomwan F *
     29    Shaquille Harrison G
     30        Zavier Simpson G
     31                   Total,
          FGM   FGA   FG%   3PM   3PA   3P%   FTM   FTA    FT%   2PM   2PA   2P%  \
     0    8.9  18.9  47.1   1.6   5.7  27.5   5.8   7.1   81.3   7.3  13.2  55.5   
     1    8.6  18.5  46.4   3.3   8.6  38.1   3.3   3.8   87.0   5.3   9.9  53.6   
     2    7.8  17.6  44.4   1.8   5.5  32.0   5.1   6.3   80.8   6.0  12.0  50.2   
     3    5.1  11.9  43.0   2.1   6.7  31.3   2.2   2.8   76.8   3.0   5.2  58.3   
     4    4.5  10.4  43.2   2.0   5.5  36.2   2.3   3.1   76.0   2.5   5.0  50.7   
     5    5.8   9.5  60.5   0.3   1.0  25.0   0.3   1.3   20.0   5.5   8.5  64.7   
     6    4.5   9.8  45.8   0.5   1.8  30.0   1.6   2.1   77.1   3.9   8.0  49.3   
     7    3.6   8.1  44.8   2.7   6.1  45.0   1.0   1.2   88.9   0.9   2.0  44.2   
     8    4.0   9.3  43.5   1.7   5.0  34.9   0.9   1.4   62.1   2.3   4.3  53.4   
     9    3.6   7.6  47.4   1.4   3.0  46.7   1.8   2.6   69.2   2.2   4.6  47.8   
     10   3.3   7.3  44.6   1.5   4.0  37.8   2.0   2.5   80.0   1.7   3.3  52.9   
     11   2.8   7.6  36.3   1.2   3.9  30.8   2.2   2.8   80.2   1.6   3.8  41.9   
     12   3.2   8.0  40.2   1.0   3.3  30.1   1.0   1.4   68.7   2.3   4.8  47.0   
     13   3.4   9.7  35.3   1.0   3.5  28.6   0.5   1.2   42.9   2.4   6.2  39.2   
     14   2.9   7.4  39.7   1.1   3.7  30.7   1.2   1.5   82.7   1.8   3.7  48.7   
     15   3.2   6.9  46.1   0.6   1.7  36.6   1.0   1.1   88.9   2.5   5.2  49.2   
     16   3.1   5.3  57.8   0.0   0.0   0.0   0.9   1.1   78.9   3.1   5.3  57.8   
     17   2.6   6.3  40.8   0.4   1.6  22.6   0.5   1.3   41.9   2.2   4.7  46.9   
     18   2.4   6.1  40.0   0.4   2.6  17.4   0.3   0.3  100.0   2.0   3.6  56.3   
     19   2.2   4.0  56.3   0.0   0.0   0.0   0.7   1.5   47.8   2.2   4.0  56.3   
     20   1.9   5.6  34.0   0.4   1.4  30.8   0.6   1.2   45.5   1.4   4.1  35.1   
     21   1.6   3.9  41.7   1.4   3.2  42.5   0.1   0.1  100.0   0.2   0.6  37.5   
     22   1.6   3.8  42.3   0.7   2.2  31.7   0.4   0.5   84.0   0.9   1.6  56.8   
     23   1.5   4.3  35.3   0.6   2.5  25.0   0.4   0.4  100.0   0.9   1.8  50.0   
     24   1.4   3.2  43.8   0.2   1.0  20.0   0.6   1.0   60.0   1.2   2.2  54.5   
     25   1.6   4.4  36.4   0.2   1.2  16.7   0.0   1.0    0.0   1.4   3.2  43.8   
     26   1.2   3.8  31.6   0.2   2.0  10.0   0.0   0.4    0.0   1.0   1.8  55.6   
     27   0.9   2.5  37.8   0.2   0.7  30.0   0.5   1.0   53.3   0.7   1.8  40.7   
     28   1.0   3.8  26.7   0.5   2.0  25.0   0.0   0.0    0.0   0.5   1.8  28.6   
     29   0.3   0.7  50.0   0.0   0.0   0.0   0.0   0.0    0.0   0.3   0.7  50.0   
     30   0.0   1.0   0.0   0.0   0.0   0.0   0.0   0.0    0.0   0.0   1.0   0.0   
     31  38.3  87.8  43.6  13.3  38.2  34.7  16.2  21.3   76.1  25.0  49.5  50.6   
     
         SC-EFF  SH-EFF  
     0    1.329    0.51  
     1    1.285    0.55  
     2    1.280    0.49  
     3    1.219    0.52  
     4    1.276    0.53  
     5    1.263    0.62  
     6    1.133    0.48  
     7    1.362    0.62  
     8    1.151    0.53  
     9    1.368    0.57  
     10   1.375    0.55  
     11   1.173    0.44  
     12   1.044    0.46  
     13   0.862    0.41  
     14   1.111    0.47  
     15   1.158    0.51  
     16   1.322    0.58  
     17   0.958    0.44  
     18   0.927    0.44  
     19   1.311    0.56  
     20   0.860    0.38  
     21   1.201    0.59  
     22   1.130    0.51  
     23   0.941    0.43  
     24   1.125    0.47  
     25   0.773    0.39  
     26   0.684    0.34  
     27   1.054    0.42  
     28   0.667    0.33  
     29   1.000    0.50  
     30   0.000    0.00  
     31   1.208    0.51  ]




```python
grizstats = table5[0]
grizstats1 = table5[1]
grizstats2 = table5[3]
```


```python
griz = pd.merge(grizstats, grizstats1, right_index = True, left_index = True)
grizTable = pd.merge(griz, grizstats2, right_index = True, left_index = True)
grizTable
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ja Morant PG</td>
      <td>9</td>
      <td>9.0</td>
      <td>35.3</td>
      <td>25.1</td>
      <td>0.7</td>
      <td>4.9</td>
      <td>5.6</td>
      <td>8.1</td>
      <td>0.8</td>
      <td>...</td>
      <td>5.7</td>
      <td>27.5</td>
      <td>5.8</td>
      <td>7.1</td>
      <td>81.3</td>
      <td>7.3</td>
      <td>13.2</td>
      <td>55.5</td>
      <td>1.329</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Desmond Bane SG</td>
      <td>42</td>
      <td>42.0</td>
      <td>34.4</td>
      <td>23.7</td>
      <td>0.9</td>
      <td>3.5</td>
      <td>4.4</td>
      <td>5.5</td>
      <td>1.0</td>
      <td>...</td>
      <td>8.6</td>
      <td>38.1</td>
      <td>3.3</td>
      <td>3.8</td>
      <td>87.0</td>
      <td>5.3</td>
      <td>9.9</td>
      <td>53.6</td>
      <td>1.285</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jaren Jackson Jr. PF</td>
      <td>66</td>
      <td>66.0</td>
      <td>32.2</td>
      <td>22.5</td>
      <td>1.3</td>
      <td>4.2</td>
      <td>5.5</td>
      <td>2.3</td>
      <td>1.2</td>
      <td>...</td>
      <td>5.5</td>
      <td>32.0</td>
      <td>5.1</td>
      <td>6.3</td>
      <td>80.8</td>
      <td>6.0</td>
      <td>12.0</td>
      <td>50.2</td>
      <td>1.280</td>
      <td>0.49</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Marcus Smart PG</td>
      <td>20</td>
      <td>20.0</td>
      <td>30.3</td>
      <td>14.5</td>
      <td>0.3</td>
      <td>2.4</td>
      <td>2.7</td>
      <td>4.3</td>
      <td>2.1</td>
      <td>...</td>
      <td>6.7</td>
      <td>31.3</td>
      <td>2.2</td>
      <td>2.8</td>
      <td>76.8</td>
      <td>3.0</td>
      <td>5.2</td>
      <td>58.3</td>
      <td>1.219</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>4</th>
      <td>GG Jackson F</td>
      <td>42</td>
      <td>12.0</td>
      <td>24.5</td>
      <td>13.3</td>
      <td>1.0</td>
      <td>3.0</td>
      <td>4.0</td>
      <td>1.1</td>
      <td>0.5</td>
      <td>...</td>
      <td>5.5</td>
      <td>36.2</td>
      <td>2.3</td>
      <td>3.1</td>
      <td>76.0</td>
      <td>2.5</td>
      <td>5.0</td>
      <td>50.7</td>
      <td>1.276</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Brandon Clarke PF</td>
      <td>4</td>
      <td>0.0</td>
      <td>21.0</td>
      <td>12.0</td>
      <td>2.5</td>
      <td>3.3</td>
      <td>5.8</td>
      <td>1.8</td>
      <td>0.8</td>
      <td>...</td>
      <td>1.0</td>
      <td>25.0</td>
      <td>0.3</td>
      <td>1.3</td>
      <td>20.0</td>
      <td>5.5</td>
      <td>8.5</td>
      <td>64.7</td>
      <td>1.263</td>
      <td>0.62</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Lamar Stevens PF *</td>
      <td>17</td>
      <td>1.0</td>
      <td>21.9</td>
      <td>11.1</td>
      <td>1.3</td>
      <td>3.5</td>
      <td>4.8</td>
      <td>0.9</td>
      <td>0.8</td>
      <td>...</td>
      <td>1.8</td>
      <td>30.0</td>
      <td>1.6</td>
      <td>2.1</td>
      <td>77.1</td>
      <td>3.9</td>
      <td>8.0</td>
      <td>49.3</td>
      <td>1.133</td>
      <td>0.48</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Luke Kennard SG</td>
      <td>39</td>
      <td>22.0</td>
      <td>25.6</td>
      <td>11.0</td>
      <td>0.3</td>
      <td>2.6</td>
      <td>2.9</td>
      <td>3.5</td>
      <td>0.5</td>
      <td>...</td>
      <td>6.1</td>
      <td>45.0</td>
      <td>1.0</td>
      <td>1.2</td>
      <td>88.9</td>
      <td>0.9</td>
      <td>2.0</td>
      <td>44.2</td>
      <td>1.362</td>
      <td>0.62</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Santi Aldama PF</td>
      <td>61</td>
      <td>35.0</td>
      <td>26.5</td>
      <td>10.7</td>
      <td>1.2</td>
      <td>4.6</td>
      <td>5.8</td>
      <td>2.3</td>
      <td>0.7</td>
      <td>...</td>
      <td>5.0</td>
      <td>34.9</td>
      <td>0.9</td>
      <td>1.4</td>
      <td>62.1</td>
      <td>2.3</td>
      <td>4.3</td>
      <td>53.4</td>
      <td>1.151</td>
      <td>0.53</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Scotty Pippen Jr. G</td>
      <td>15</td>
      <td>10.0</td>
      <td>23.0</td>
      <td>10.4</td>
      <td>0.7</td>
      <td>2.1</td>
      <td>2.9</td>
      <td>4.1</td>
      <td>1.3</td>
      <td>...</td>
      <td>3.0</td>
      <td>46.7</td>
      <td>1.8</td>
      <td>2.6</td>
      <td>69.2</td>
      <td>2.2</td>
      <td>4.6</td>
      <td>47.8</td>
      <td>1.368</td>
      <td>0.57</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Vince Williams Jr. G</td>
      <td>52</td>
      <td>33.0</td>
      <td>27.6</td>
      <td>10.0</td>
      <td>1.1</td>
      <td>4.4</td>
      <td>5.6</td>
      <td>3.4</td>
      <td>0.9</td>
      <td>...</td>
      <td>4.0</td>
      <td>37.8</td>
      <td>2.0</td>
      <td>2.5</td>
      <td>80.0</td>
      <td>1.7</td>
      <td>3.3</td>
      <td>52.9</td>
      <td>1.375</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Jake LaRavia F</td>
      <td>31</td>
      <td>2.0</td>
      <td>20.9</td>
      <td>9.0</td>
      <td>1.5</td>
      <td>2.0</td>
      <td>3.5</td>
      <td>1.5</td>
      <td>0.8</td>
      <td>...</td>
      <td>3.9</td>
      <td>30.8</td>
      <td>2.2</td>
      <td>2.8</td>
      <td>80.2</td>
      <td>1.6</td>
      <td>3.8</td>
      <td>41.9</td>
      <td>1.173</td>
      <td>0.44</td>
    </tr>
    <tr>
      <th>12</th>
      <td>David Roddy F *</td>
      <td>48</td>
      <td>13.0</td>
      <td>23.2</td>
      <td>8.4</td>
      <td>1.1</td>
      <td>3.1</td>
      <td>4.2</td>
      <td>1.6</td>
      <td>0.5</td>
      <td>...</td>
      <td>3.3</td>
      <td>30.1</td>
      <td>1.0</td>
      <td>1.4</td>
      <td>68.7</td>
      <td>2.3</td>
      <td>4.8</td>
      <td>47.0</td>
      <td>1.044</td>
      <td>0.46</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Jordan Goodwin G *</td>
      <td>12</td>
      <td>7.0</td>
      <td>27.3</td>
      <td>8.3</td>
      <td>2.3</td>
      <td>4.6</td>
      <td>6.8</td>
      <td>4.7</td>
      <td>1.3</td>
      <td>...</td>
      <td>3.5</td>
      <td>28.6</td>
      <td>0.5</td>
      <td>1.2</td>
      <td>42.9</td>
      <td>2.4</td>
      <td>6.2</td>
      <td>39.2</td>
      <td>0.862</td>
      <td>0.41</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Ziaire Williams F</td>
      <td>51</td>
      <td>15.0</td>
      <td>20.4</td>
      <td>8.2</td>
      <td>0.7</td>
      <td>2.8</td>
      <td>3.5</td>
      <td>1.5</td>
      <td>0.7</td>
      <td>...</td>
      <td>3.7</td>
      <td>30.7</td>
      <td>1.2</td>
      <td>1.5</td>
      <td>82.7</td>
      <td>1.8</td>
      <td>3.7</td>
      <td>48.7</td>
      <td>1.111</td>
      <td>0.47</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Derrick Rose PG</td>
      <td>24</td>
      <td>7.0</td>
      <td>16.6</td>
      <td>8.0</td>
      <td>0.3</td>
      <td>1.6</td>
      <td>1.9</td>
      <td>3.3</td>
      <td>0.3</td>
      <td>...</td>
      <td>1.7</td>
      <td>36.6</td>
      <td>1.0</td>
      <td>1.1</td>
      <td>88.9</td>
      <td>2.5</td>
      <td>5.2</td>
      <td>49.2</td>
      <td>1.158</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Trey Jemison C *</td>
      <td>17</td>
      <td>8.0</td>
      <td>21.6</td>
      <td>7.0</td>
      <td>2.4</td>
      <td>2.3</td>
      <td>4.6</td>
      <td>0.9</td>
      <td>0.4</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.9</td>
      <td>1.1</td>
      <td>78.9</td>
      <td>3.1</td>
      <td>5.3</td>
      <td>57.8</td>
      <td>1.322</td>
      <td>0.58</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Xavier Tillman F *</td>
      <td>34</td>
      <td>13.0</td>
      <td>20.6</td>
      <td>6.0</td>
      <td>1.6</td>
      <td>3.0</td>
      <td>4.6</td>
      <td>1.7</td>
      <td>1.2</td>
      <td>...</td>
      <td>1.6</td>
      <td>22.6</td>
      <td>0.5</td>
      <td>1.3</td>
      <td>41.9</td>
      <td>2.2</td>
      <td>4.7</td>
      <td>46.9</td>
      <td>0.958</td>
      <td>0.44</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Jaylen Nowell SG</td>
      <td>9</td>
      <td>1.0</td>
      <td>17.3</td>
      <td>5.7</td>
      <td>0.3</td>
      <td>1.2</td>
      <td>1.6</td>
      <td>1.8</td>
      <td>0.3</td>
      <td>...</td>
      <td>2.6</td>
      <td>17.4</td>
      <td>0.3</td>
      <td>0.3</td>
      <td>100.0</td>
      <td>2.0</td>
      <td>3.6</td>
      <td>56.3</td>
      <td>0.927</td>
      <td>0.44</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Bismack Biyombo C *</td>
      <td>30</td>
      <td>27.0</td>
      <td>23.9</td>
      <td>5.2</td>
      <td>1.9</td>
      <td>4.5</td>
      <td>6.4</td>
      <td>1.7</td>
      <td>0.3</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.7</td>
      <td>1.5</td>
      <td>47.8</td>
      <td>2.2</td>
      <td>4.0</td>
      <td>56.3</td>
      <td>1.311</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>20</th>
      <td>DeJon Jarreau F</td>
      <td>9</td>
      <td>0.0</td>
      <td>16.7</td>
      <td>4.8</td>
      <td>0.9</td>
      <td>4.0</td>
      <td>4.9</td>
      <td>2.9</td>
      <td>0.7</td>
      <td>...</td>
      <td>1.4</td>
      <td>30.8</td>
      <td>0.6</td>
      <td>1.2</td>
      <td>45.5</td>
      <td>1.4</td>
      <td>4.1</td>
      <td>35.1</td>
      <td>0.860</td>
      <td>0.38</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Jacob Gilyard G *</td>
      <td>37</td>
      <td>14.0</td>
      <td>17.7</td>
      <td>4.7</td>
      <td>0.2</td>
      <td>0.9</td>
      <td>1.2</td>
      <td>3.5</td>
      <td>0.7</td>
      <td>...</td>
      <td>3.2</td>
      <td>42.5</td>
      <td>0.1</td>
      <td>0.1</td>
      <td>100.0</td>
      <td>0.2</td>
      <td>0.6</td>
      <td>37.5</td>
      <td>1.201</td>
      <td>0.59</td>
    </tr>
    <tr>
      <th>22</th>
      <td>John Konchar SG</td>
      <td>55</td>
      <td>23.0</td>
      <td>21.3</td>
      <td>4.3</td>
      <td>1.3</td>
      <td>3.4</td>
      <td>4.7</td>
      <td>2.0</td>
      <td>0.9</td>
      <td>...</td>
      <td>2.2</td>
      <td>31.7</td>
      <td>0.4</td>
      <td>0.5</td>
      <td>84.0</td>
      <td>0.9</td>
      <td>1.6</td>
      <td>56.8</td>
      <td>1.130</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Matt Hurt F</td>
      <td>8</td>
      <td>0.0</td>
      <td>14.1</td>
      <td>4.0</td>
      <td>1.1</td>
      <td>0.9</td>
      <td>2.0</td>
      <td>0.5</td>
      <td>0.4</td>
      <td>...</td>
      <td>2.5</td>
      <td>25.0</td>
      <td>0.4</td>
      <td>0.4</td>
      <td>100.0</td>
      <td>0.9</td>
      <td>1.8</td>
      <td>50.0</td>
      <td>0.941</td>
      <td>0.43</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Maozinha Pereira F</td>
      <td>5</td>
      <td>0.0</td>
      <td>11.0</td>
      <td>3.6</td>
      <td>1.6</td>
      <td>1.8</td>
      <td>3.4</td>
      <td>0.2</td>
      <td>0.8</td>
      <td>...</td>
      <td>1.0</td>
      <td>20.0</td>
      <td>0.6</td>
      <td>1.0</td>
      <td>60.0</td>
      <td>1.2</td>
      <td>2.2</td>
      <td>54.5</td>
      <td>1.125</td>
      <td>0.47</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Wenyen Gabriel F</td>
      <td>5</td>
      <td>0.0</td>
      <td>16.2</td>
      <td>3.4</td>
      <td>1.4</td>
      <td>3.6</td>
      <td>5.0</td>
      <td>0.6</td>
      <td>0.4</td>
      <td>...</td>
      <td>1.2</td>
      <td>16.7</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>1.4</td>
      <td>3.2</td>
      <td>43.8</td>
      <td>0.773</td>
      <td>0.39</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Yuta Watanabe SF *</td>
      <td>5</td>
      <td>0.0</td>
      <td>16.4</td>
      <td>2.6</td>
      <td>0.0</td>
      <td>1.8</td>
      <td>1.8</td>
      <td>1.0</td>
      <td>0.6</td>
      <td>...</td>
      <td>2.0</td>
      <td>10.0</td>
      <td>0.0</td>
      <td>0.4</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.8</td>
      <td>55.6</td>
      <td>0.684</td>
      <td>0.34</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Kenneth Lofton Jr. F *</td>
      <td>15</td>
      <td>0.0</td>
      <td>6.6</td>
      <td>2.6</td>
      <td>0.1</td>
      <td>0.9</td>
      <td>1.0</td>
      <td>0.9</td>
      <td>0.2</td>
      <td>...</td>
      <td>0.7</td>
      <td>30.0</td>
      <td>0.5</td>
      <td>1.0</td>
      <td>53.3</td>
      <td>0.7</td>
      <td>1.8</td>
      <td>40.7</td>
      <td>1.054</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Tosan Evbuomwan F *</td>
      <td>4</td>
      <td>0.0</td>
      <td>18.5</td>
      <td>2.5</td>
      <td>2.0</td>
      <td>1.5</td>
      <td>3.5</td>
      <td>1.5</td>
      <td>0.0</td>
      <td>...</td>
      <td>2.0</td>
      <td>25.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.5</td>
      <td>1.8</td>
      <td>28.6</td>
      <td>0.667</td>
      <td>0.33</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Shaquille Harrison G</td>
      <td>3</td>
      <td>0.0</td>
      <td>2.0</td>
      <td>0.7</td>
      <td>0.0</td>
      <td>0.7</td>
      <td>0.7</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.3</td>
      <td>0.7</td>
      <td>50.0</td>
      <td>1.000</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Zavier Simpson G</td>
      <td>1</td>
      <td>0.0</td>
      <td>9.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>4.0</td>
      <td>1.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.000</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Total</td>
      <td>76</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>106.0</td>
      <td>10.6</td>
      <td>31.8</td>
      <td>42.4</td>
      <td>25.0</td>
      <td>8.0</td>
      <td>...</td>
      <td>38.2</td>
      <td>34.7</td>
      <td>16.2</td>
      <td>21.3</td>
      <td>76.1</td>
      <td>25.0</td>
      <td>49.5</td>
      <td>50.6</td>
      <td>1.208</td>
      <td>0.51</td>
    </tr>
  </tbody>
</table>
<p>32 rows × 28 columns</p>
</div>




```python
grizTable.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>BLK</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>32.000000</td>
      <td>31.000000</td>
      <td>31.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>...</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
      <td>32.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>26.437500</td>
      <td>12.258065</td>
      <td>20.761290</td>
      <td>11.540625</td>
      <td>1.362500</td>
      <td>3.590625</td>
      <td>4.959375</td>
      <td>3.065625</td>
      <td>0.940625</td>
      <td>0.693750</td>
      <td>...</td>
      <td>3.987500</td>
      <td>26.490625</td>
      <td>1.668750</td>
      <td>2.290625</td>
      <td>60.940625</td>
      <td>2.943750</td>
      <td>5.856250</td>
      <td>47.721875</td>
      <td>1.079687</td>
      <td>0.473437</td>
    </tr>
    <tr>
      <th>std</th>
      <td>21.348019</td>
      <td>15.459555</td>
      <td>7.600468</td>
      <td>18.307955</td>
      <td>1.821334</td>
      <td>5.314275</td>
      <td>7.042216</td>
      <td>4.363752</td>
      <td>1.356433</td>
      <td>1.084179</td>
      <td>...</td>
      <td>6.604483</td>
      <td>12.832126</td>
      <td>2.990138</td>
      <td>3.832153</td>
      <td>32.225304</td>
      <td>4.380524</td>
      <td>8.532516</td>
      <td>11.534457</td>
      <td>0.278574</td>
      <td>0.113865</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.700000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.600000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>8.750000</td>
      <td>0.000000</td>
      <td>16.650000</td>
      <td>4.225000</td>
      <td>0.600000</td>
      <td>1.750000</td>
      <td>2.525000</td>
      <td>1.075000</td>
      <td>0.400000</td>
      <td>0.200000</td>
      <td>...</td>
      <td>1.350000</td>
      <td>21.950000</td>
      <td>0.375000</td>
      <td>0.875000</td>
      <td>44.850000</td>
      <td>0.975000</td>
      <td>1.950000</td>
      <td>44.100000</td>
      <td>0.953750</td>
      <td>0.437500</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>18.500000</td>
      <td>8.000000</td>
      <td>21.000000</td>
      <td>8.100000</td>
      <td>1.100000</td>
      <td>2.900000</td>
      <td>4.100000</td>
      <td>1.800000</td>
      <td>0.700000</td>
      <td>0.450000</td>
      <td>...</td>
      <td>2.550000</td>
      <td>30.050000</td>
      <td>0.800000</td>
      <td>1.250000</td>
      <td>76.050000</td>
      <td>2.100000</td>
      <td>4.050000</td>
      <td>50.000000</td>
      <td>1.142000</td>
      <td>0.495000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>42.000000</td>
      <td>17.500000</td>
      <td>25.050000</td>
      <td>11.025000</td>
      <td>1.525000</td>
      <td>3.700000</td>
      <td>5.125000</td>
      <td>3.500000</td>
      <td>0.925000</td>
      <td>0.825000</td>
      <td>...</td>
      <td>4.250000</td>
      <td>34.750000</td>
      <td>1.850000</td>
      <td>2.525000</td>
      <td>81.650000</td>
      <td>2.625000</td>
      <td>5.225000</td>
      <td>54.750000</td>
      <td>1.277000</td>
      <td>0.535000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>76.000000</td>
      <td>66.000000</td>
      <td>35.300000</td>
      <td>106.000000</td>
      <td>10.600000</td>
      <td>31.800000</td>
      <td>42.400000</td>
      <td>25.000000</td>
      <td>8.000000</td>
      <td>6.200000</td>
      <td>...</td>
      <td>38.200000</td>
      <td>46.700000</td>
      <td>16.200000</td>
      <td>21.300000</td>
      <td>100.000000</td>
      <td>25.000000</td>
      <td>49.500000</td>
      <td>64.700000</td>
      <td>1.375000</td>
      <td>0.620000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 27 columns</p>
</div>




```python
grizTable.columns
```




    Index(['Name', 'GP', 'GS', 'MIN', 'PTS', 'OR', 'DR', 'REB', 'AST', 'STL',
           'BLK', 'TO', 'PF', 'AST/TO', 'FGM', 'FGA', 'FG%', '3PM', '3PA', '3P%',
           'FTM', 'FTA', 'FT%', '2PM', '2PA', '2P%', 'SC-EFF', 'SH-EFF'],
          dtype='object')




```python
grizTable.shape
```




    (32, 28)




```python
grizTable.dtypes
```




    Name       object
    GP          int64
    GS        float64
    MIN       float64
    PTS       float64
    OR        float64
    DR        float64
    REB       float64
    AST       float64
    STL       float64
    BLK       float64
    TO        float64
    PF        float64
    AST/TO    float64
    FGM       float64
    FGA       float64
    FG%       float64
    3PM       float64
    3PA       float64
    3P%       float64
    FTM       float64
    FTA       float64
    FT%       float64
    2PM       float64
    2PA       float64
    2P%       float64
    SC-EFF    float64
    SH-EFF    float64
    dtype: object



### Only ranking these teams based on the top 15 players since that is the size of the smallest team


```python
grizTable = grizTable.drop(grizTable.index[16:])
```


```python
grizTable.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ja Morant PG</td>
      <td>9</td>
      <td>9.0</td>
      <td>35.3</td>
      <td>25.1</td>
      <td>0.7</td>
      <td>4.9</td>
      <td>5.6</td>
      <td>8.1</td>
      <td>0.8</td>
      <td>...</td>
      <td>5.7</td>
      <td>27.5</td>
      <td>5.8</td>
      <td>7.1</td>
      <td>81.3</td>
      <td>7.3</td>
      <td>13.2</td>
      <td>55.5</td>
      <td>1.329</td>
      <td>0.51</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Desmond Bane SG</td>
      <td>42</td>
      <td>42.0</td>
      <td>34.4</td>
      <td>23.7</td>
      <td>0.9</td>
      <td>3.5</td>
      <td>4.4</td>
      <td>5.5</td>
      <td>1.0</td>
      <td>...</td>
      <td>8.6</td>
      <td>38.1</td>
      <td>3.3</td>
      <td>3.8</td>
      <td>87.0</td>
      <td>5.3</td>
      <td>9.9</td>
      <td>53.6</td>
      <td>1.285</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jaren Jackson Jr. PF</td>
      <td>66</td>
      <td>66.0</td>
      <td>32.2</td>
      <td>22.5</td>
      <td>1.3</td>
      <td>4.2</td>
      <td>5.5</td>
      <td>2.3</td>
      <td>1.2</td>
      <td>...</td>
      <td>5.5</td>
      <td>32.0</td>
      <td>5.1</td>
      <td>6.3</td>
      <td>80.8</td>
      <td>6.0</td>
      <td>12.0</td>
      <td>50.2</td>
      <td>1.280</td>
      <td>0.49</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Marcus Smart PG</td>
      <td>20</td>
      <td>20.0</td>
      <td>30.3</td>
      <td>14.5</td>
      <td>0.3</td>
      <td>2.4</td>
      <td>2.7</td>
      <td>4.3</td>
      <td>2.1</td>
      <td>...</td>
      <td>6.7</td>
      <td>31.3</td>
      <td>2.2</td>
      <td>2.8</td>
      <td>76.8</td>
      <td>3.0</td>
      <td>5.2</td>
      <td>58.3</td>
      <td>1.219</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>4</th>
      <td>GG Jackson F</td>
      <td>42</td>
      <td>12.0</td>
      <td>24.5</td>
      <td>13.3</td>
      <td>1.0</td>
      <td>3.0</td>
      <td>4.0</td>
      <td>1.1</td>
      <td>0.5</td>
      <td>...</td>
      <td>5.5</td>
      <td>36.2</td>
      <td>2.3</td>
      <td>3.1</td>
      <td>76.0</td>
      <td>2.5</td>
      <td>5.0</td>
      <td>50.7</td>
      <td>1.276</td>
      <td>0.53</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
grizTable.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>Jake LaRavia F</td>
      <td>31</td>
      <td>2.0</td>
      <td>20.9</td>
      <td>9.0</td>
      <td>1.5</td>
      <td>2.0</td>
      <td>3.5</td>
      <td>1.5</td>
      <td>0.8</td>
      <td>...</td>
      <td>3.9</td>
      <td>30.8</td>
      <td>2.2</td>
      <td>2.8</td>
      <td>80.2</td>
      <td>1.6</td>
      <td>3.8</td>
      <td>41.9</td>
      <td>1.173</td>
      <td>0.44</td>
    </tr>
    <tr>
      <th>12</th>
      <td>David Roddy F *</td>
      <td>48</td>
      <td>13.0</td>
      <td>23.2</td>
      <td>8.4</td>
      <td>1.1</td>
      <td>3.1</td>
      <td>4.2</td>
      <td>1.6</td>
      <td>0.5</td>
      <td>...</td>
      <td>3.3</td>
      <td>30.1</td>
      <td>1.0</td>
      <td>1.4</td>
      <td>68.7</td>
      <td>2.3</td>
      <td>4.8</td>
      <td>47.0</td>
      <td>1.044</td>
      <td>0.46</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Jordan Goodwin G *</td>
      <td>12</td>
      <td>7.0</td>
      <td>27.3</td>
      <td>8.3</td>
      <td>2.3</td>
      <td>4.6</td>
      <td>6.8</td>
      <td>4.7</td>
      <td>1.3</td>
      <td>...</td>
      <td>3.5</td>
      <td>28.6</td>
      <td>0.5</td>
      <td>1.2</td>
      <td>42.9</td>
      <td>2.4</td>
      <td>6.2</td>
      <td>39.2</td>
      <td>0.862</td>
      <td>0.41</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Ziaire Williams F</td>
      <td>51</td>
      <td>15.0</td>
      <td>20.4</td>
      <td>8.2</td>
      <td>0.7</td>
      <td>2.8</td>
      <td>3.5</td>
      <td>1.5</td>
      <td>0.7</td>
      <td>...</td>
      <td>3.7</td>
      <td>30.7</td>
      <td>1.2</td>
      <td>1.5</td>
      <td>82.7</td>
      <td>1.8</td>
      <td>3.7</td>
      <td>48.7</td>
      <td>1.111</td>
      <td>0.47</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Derrick Rose PG</td>
      <td>24</td>
      <td>7.0</td>
      <td>16.6</td>
      <td>8.0</td>
      <td>0.3</td>
      <td>1.6</td>
      <td>1.9</td>
      <td>3.3</td>
      <td>0.3</td>
      <td>...</td>
      <td>1.7</td>
      <td>36.6</td>
      <td>1.0</td>
      <td>1.1</td>
      <td>88.9</td>
      <td>2.5</td>
      <td>5.2</td>
      <td>49.2</td>
      <td>1.158</td>
      <td>0.51</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
grizTable.sample()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>GP</th>
      <th>GS</th>
      <th>MIN</th>
      <th>PTS</th>
      <th>OR</th>
      <th>DR</th>
      <th>REB</th>
      <th>AST</th>
      <th>STL</th>
      <th>...</th>
      <th>3PA</th>
      <th>3P%</th>
      <th>FTM</th>
      <th>FTA</th>
      <th>FT%</th>
      <th>2PM</th>
      <th>2PA</th>
      <th>2P%</th>
      <th>SC-EFF</th>
      <th>SH-EFF</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8</th>
      <td>Santi Aldama PF</td>
      <td>61</td>
      <td>35.0</td>
      <td>26.5</td>
      <td>10.7</td>
      <td>1.2</td>
      <td>4.6</td>
      <td>5.8</td>
      <td>2.3</td>
      <td>0.7</td>
      <td>...</td>
      <td>5.0</td>
      <td>34.9</td>
      <td>0.9</td>
      <td>1.4</td>
      <td>62.1</td>
      <td>2.3</td>
      <td>4.3</td>
      <td>53.4</td>
      <td>1.151</td>
      <td>0.53</td>
    </tr>
  </tbody>
</table>
<p>1 rows × 28 columns</p>
</div>




```python
grizTable.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 16 entries, 0 to 15
    Data columns (total 28 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   Name    16 non-null     object 
     1   GP      16 non-null     int64  
     2   GS      16 non-null     float64
     3   MIN     16 non-null     float64
     4   PTS     16 non-null     float64
     5   OR      16 non-null     float64
     6   DR      16 non-null     float64
     7   REB     16 non-null     float64
     8   AST     16 non-null     float64
     9   STL     16 non-null     float64
     10  BLK     16 non-null     float64
     11  TO      16 non-null     float64
     12  PF      16 non-null     float64
     13  AST/TO  16 non-null     float64
     14  FGM     16 non-null     float64
     15  FGA     16 non-null     float64
     16  FG%     16 non-null     float64
     17  3PM     16 non-null     float64
     18  3PA     16 non-null     float64
     19  3P%     16 non-null     float64
     20  FTM     16 non-null     float64
     21  FTA     16 non-null     float64
     22  FT%     16 non-null     float64
     23  2PM     16 non-null     float64
     24  2PA     16 non-null     float64
     25  2P%     16 non-null     float64
     26  SC-EFF  16 non-null     float64
     27  SH-EFF  16 non-null     float64
    dtypes: float64(26), int64(1), object(1)
    memory usage: 3.6+ KB


### Additional Data Analysis

#### Total of average player PPG's for Memphis


```python
griz_totAvgPts = grizTable['PTS'].sum()
griz_totAvgPts
```




    206.2



#### Players with most/least games played


```python
grizGames = grizTable['GP'].max()
print(grizTable.loc[grizTable['GP'] == grizGames, 'Name'], grizGames)
```

    2    Jaren Jackson Jr. PF
    Name: Name, dtype: object 66



```python
grizGames1 = grizTable['GP'].min()
print(grizTable.loc[grizTable['GP'] == grizGames1, 'Name'], grizGames1)
```

    5    Brandon Clarke PF
    Name: Name, dtype: object 4


#### Players with most/least fouls averaged per game


```python
grizFouls = grizTable['PF'].max()
print(grizTable.loc[grizTable['PF'] == grizFouls, 'Name'], grizFouls)
```

    2    Jaren Jackson Jr. PF
    Name: Name, dtype: object 3.6



```python
grizFouls1 = grizTable['PF'].min()
print(grizTable.loc[grizTable['PF'] == grizFouls1, 'Name'], grizFouls1)
```

    15    Derrick Rose PG
    Name: Name, dtype: object 0.9



```python
grizBar = plt.bar(grizTable['Name'], grizTable['PF'])
plt.title('Players/Their Avg Fouls/Game')
plt.xlabel('Players')
plt.ylabel('Avg Fouls/Game')
plt.xticks(rotation = 90)
grizBar
```




    <BarContainer object of 16 artists>




    
![png](output_155_1.png)
    


#### Player averaging the most 3's


```python
grizThrees = grizTable['3PM'].max()
print(grizTable.loc[grizTable['3PM'] == grizThrees, 'Name'], grizThrees)
```

    1    Desmond Bane SG
    Name: Name, dtype: object 3.3


#### Player averaging the least 3's


```python
grizThrees1 = grizTable['3PM'].min()
print(grizTable.loc[grizTable['3PM'] == grizThrees1, 'Name'], grizThrees1)
```

    5    Brandon Clarke PF
    Name: Name, dtype: object 0.3


#### Total Defensive Stats: Def Rebounds + Blocks + Steals


```python
DefReb5 = grizTable['DR'].sum()
Blocks5 = grizTable['BLK'].sum()
Steals5 = grizTable['STL'].sum()
DefStats5 = (DefReb5 + Blocks5 + Steals5)
DefStats5
```




    76.2



## Analysis Questions

### Q1: How do the selected teams rank based on average points per game?
####   Denver - 135.399
####   Golden State - 145.5
####   Boston - 152.399
####   Brooklyn - 162.399
####   Memphis - 206.2

### Q2: Of the top 16 players on each team, who played the most/least games this season?
####   Brooklyn: Mikal Bridges(77) - Keon Johnson(4)
####   Denver: Reggie Jackson/Christian Braun(76) - Hunter Tyson(14)
####   Boston: Payton Pritchard(76) - Drew Peterson(1)
####   Golden State: Klay Thompson(72) - Jerome Robinson/Gui Santos(20)
####   Memphis: Jaren Jackson(66) - Brandon Clarke(4)

### Q3: Which players from each team average the most/least average fouls/game?
####   Brooklyn: Nic Claxton(2.5) - Armoni Brooks(0.3)
####   Denver: Nikola Jokic(2.4) - Jalen Pickett/Jay Huff(0.5)
####   Boston: Kristaps Porzingis(2.8) - Svi Myhailiuk(0.4)
####   Golden State: Draymond Green(3.0) - Jerome Robinson(0.3)
####   Memphis: Jaren Jackson Jr(3.6) - Derrick Rose(0.9)

### Q4: Which players from each team are the best/worst at shooting three's/game?
####   Brooklyn: Mikal Bridges(2.7) - Nic Claxton/Ben Simmons(0)
####   Denver: Michael Porter Jr(2.8) - Deandre Jordan(0)
####   Boston: Jayson Tatum(3.1) - Luke Kornet/Neemias Queta(0)
####   Golden State: Steph Curry(4.8) - Tracey Jackson-Davis/Kevin Looney(0)
####   Memphis: Desmond Bane(3.3) - Brandon Clarke(0.3)

### Q5: Considering the Defensive Stats (DR/BLK/STL), which team has the best defense?
####  Brooklyn: 65.7
####  Denver: 65.7
####  Boston: 55.0
####  Golden State: 59.0
####  Memphis: 76.2
