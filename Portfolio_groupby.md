### Import Pandas


```python
import pandas as pd
```

### Read in Data


```python
df = pd.read_csv("ROLLING_STONE_TOP_500_ALBUMS.csv")
```

### Print df


```python
df.head()
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
      <th>Position</th>
      <th>Artist</th>
      <th>Album Name</th>
      <th>Label</th>
      <th>Year</th>
      <th>Critic</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Marvin Gaye</td>
      <td>'What's Going On'</td>
      <td>Tamla/Motown</td>
      <td>1971</td>
      <td>At the end of the final song on What’s Going O...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>The Beach Boys</td>
      <td>'Pet Sounds'</td>
      <td>Capitol</td>
      <td>1966</td>
      <td>The album’s centerpiece is “God Only Knows,” a...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Joni Mitchell</td>
      <td>'Blue'</td>
      <td>Reprise</td>
      <td>1971</td>
      <td>Mitchell continued to release excellent record...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Stevie Wonder</td>
      <td>'Songs in the Key of Life'</td>
      <td>Tamla/Motown</td>
      <td>1976</td>
      <td>The album’s mastery of many styles remains ast...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>The Beatles</td>
      <td>'Abbey Road'</td>
      <td>Apple</td>
      <td>1969</td>
      <td>There was no thematic link, other than the Bea...</td>
    </tr>
  </tbody>
</table>
</div>



### Groupby Position and Artist


```python
df_artist = pd.DataFrame(df.groupby(['Position','Artist']).mean())
```

### Print Artists of Top 5 Albums


```python
df_artist.head()
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

```
