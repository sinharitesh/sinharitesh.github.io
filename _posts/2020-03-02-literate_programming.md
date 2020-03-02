# Literate Programming
> A concept introduced by Donald Knuth some 35 years ago!


## Background

The programming is done in a way that logic is explained in natural language, which enables generation of comilable source code. This was first envisioned by Donald Knuth.

According to Knuth, literate programming provides higher-quality programs, since it forces programmers to explicitly state the thoughts behind the program, making poorly thought-out design decisions more obvious. 

## Literate programming is different than document generation

As per wikipedia

Implementing literate programming consists of two steps:

Weaving: Generating a comprehensive document about the program and its maintenance.

Tangling: Generating machine executable code

Weaving and tangling are done on the same source so that they are consistent with each other.

## Order of human logic, not that of the compiler

Juputer Noteboos and R markdown are listed as the tools for Literate Programming, but as per the above definition, in true sense, they probably are not. `Tangling` is not achieved by these tools.

Write about nbdev

### Explain what nbdev does, some of the things it does , show an example of development of libraries.

Let us develop something here. I have a dataset and I need to have a generic function which can draw some chart.

```python
#export
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

```python
#export
def get_dataframe():
    """
    gets a dataframe with 
    """
    import pandas as pd
    import numpy as np
    dates = pd.date_range('20130101', periods=6)
    df = pd.DataFrame(np.random.randn(6, 4), index = dates, columns=list('ABCD'))
    return df
```

```python
df_test = get_dataframe()
```

```python
df_test.head()
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2013-01-01</th>
      <td>-0.539227</td>
      <td>-2.203705</td>
      <td>-3.167999</td>
      <td>0.275525</td>
    </tr>
    <tr>
      <th>2013-01-02</th>
      <td>1.258536</td>
      <td>-0.257426</td>
      <td>-0.086583</td>
      <td>-1.758281</td>
    </tr>
    <tr>
      <th>2013-01-03</th>
      <td>-1.766715</td>
      <td>0.668160</td>
      <td>2.514621</td>
      <td>-0.456803</td>
    </tr>
    <tr>
      <th>2013-01-04</th>
      <td>-1.057043</td>
      <td>-0.157582</td>
      <td>1.425256</td>
      <td>1.210564</td>
    </tr>
    <tr>
      <th>2013-01-05</th>
      <td>-1.009482</td>
      <td>-0.514296</td>
      <td>0.670356</td>
      <td>-0.303426</td>
    </tr>
  </tbody>
</table>
</div>



```python
#export
def draw_chart(df):
    """
    plotting a simple chart here. 
    """
    
    plt.plot(df.index, df['A'], linewidth = 2.0)
    plt.show()
```

```python
draw_chart(df_test)
```


![png](/images/literate_programming_files/output_15_0.png)


```python
from nbdev.showdoc import *
show_doc(draw_chart)
```


<h4 id="draw_chart" class="doc_header"><code>draw_chart</code><a href="__main__.py#L2" class="source_link" style="float:right">[source]</a></h4>

> <code>draw_chart</code>(**`df`**)

plotting a simple chart here. 

