```python
import pandas as pd
import matplotlib.pyplot as plt
```


```python
df = pd.read_csv("ROLLING_STONE_TOP_500_ALBUMS.csv")
```


```python
df_artist = pd.DataFrame(df.groupby(['Position','Artist']).mean())
Top_5 = df_artist.head(5)
```


```python
Top_5
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
      <th></th>
      <th>Year</th>
    </tr>
    <tr>
      <th>Position</th>
      <th>Artist</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <th>Marvin Gaye</th>
      <td>1971</td>
    </tr>
    <tr>
      <th>2</th>
      <th>The Beach Boys</th>
      <td>1966</td>
    </tr>
    <tr>
      <th>3</th>
      <th>Joni Mitchell</th>
      <td>1971</td>
    </tr>
    <tr>
      <th>4</th>
      <th>Stevie Wonder</th>
      <td>1976</td>
    </tr>
    <tr>
      <th>5</th>
      <th>The Beatles</th>
      <td>1969</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.hist(Top_5, bins=10)
plt.show()
```




    
![png](Portfolio_data_visualization_files/Portfolio_data_visualization_4_0.png)
    




```python

```
