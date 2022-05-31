# st.write

Write arguments to the app.

This is the Swiss Army knife of Streamlit commands: it does different things depending on what you throw at it. Unlike other Streamlit commands, write() has some unique properties:
1. You can pass in multiple arguments, all of which will be written.
2. Its behavior depends on the input types as follows.

`st.write` supports a wide range of data types: text strings, emojis, numerical values, DataFrames and chart figures (matplotlib, altair, bokeh, plotly)

To use the st.write command, you can provide one or more arguments as the input argument.

By default HTML tags will be treated as pure text as the **`unsafe_allow_html`** option defaults to False. You can set this to `True` if you want HTML tags to be recognized.

## Demo app

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io/dataprofessor/streamlit-write/)

## Code
Here's how to use `st.write`:
```python
import streamlit as st

# 1. Display text
st.write('Hello world')

# 2. Display a title and some text to the app:
st.write('''
# This is the document title
This is some _markdown_.
''')

# 3. Display the dataframe
import pandas as pd
df = pd.DataFrame({'col1': [1,2,3], 'col2': [4,5,6]})
st.write(df) 

# 4. Display the string 'x' and then the value of x
x = 10
st.write('x', x)

# 5. Display Matplotlib chart
import matplotlib.pyplot as plt
import numpy as np

y = np.random.normal(0, 1, size=1000)
fig, ax = plt.subplots()
ax.hist(y, bins=20)

st.write(fig)
```
