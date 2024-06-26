---
title: COMP_SCI 396
separator: <!--s-->
verticalSeparator: <!--v-->
theme: serif
revealOptions:
  transition: 'none'
---

<div class = "header-slide">

# Introduction to the Data Science Pipeline
## L.03 Exploratory Data Analysis

</div>

<!--s-->

## Announcements

- **H.01** is due 04.04.2024 at 11:59 PM.

- **P.01** is due on 04.09.2024 at 11:59 PM. 

<!--s-->

## Exploratory Data Analysis (EDA) | Introduction

**Exploratory Data Analysis** (EDA) is an approach to analyzing data sets to summarize their main characteristics, often with visual methods.

This should be done every single time you are exposed to a new dataset. **ALWAYS** look at the data.

EDA will help you to identify early issues or patterns in the data, and will guide you in the next steps of your analysis. It is an absolutely **critical**, but often overlooked step.

<!--s-->

## Exploratory Data Analysis (EDA) | Methodology

We can break down EDA into two main categories:

- **Descriptive EDA**: Summarizing the main characteristics of the data.
- **Graphical EDA**: Visualizing the data to understand its structure and patterns.

<!--s-->

<div class="header-slide"> 

# Descriptive EDA

</div>

<!--s-->

## Descriptive EDA | Examples

- **Central tendency**
    - Mean, Median, Mode
- **Spread**
    - Range, Variance, interquartile range (IQR)
- **Skewness**
    - A measure of the asymmetry of the distribution
- **Kurtosis**
    - A measure of the "tailedness" of the distribution

<!--s-->

## Central Tendency

- **Mean**: The average of the data. 

    - $ \bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i $

    - <span class="code-span">np.mean(data)</span>

- **Median**: The middle value of the data, when sorted.

    - <span class="code-span">np.median(data)</span>

- **Mode**: The most frequent value in the data.

    ```python
    from scipy.stats import mode
    data = np.random.normal(0, 1, 1000)
    mode(data)
    ```

<!--s-->

## Spread

- **Range**: The difference between the maximum and minimum values in the data.
    
    - <span class="code-span">np.max(data) - np.min(data)</span>

- **Variance**: The average of the squared differences from the mean.

    - $ \frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^2 $

    - <span class="code-span">np.var(data)</span>

- **Standard Deviation**: The square root of the variance.

    - $ \sqrt{\frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^2} $
    - <span class="code-span">np.std(data)</span>

- **Interquartile Range (IQR)**: The difference between the 75th and 25th percentiles.
    - <span class="code-span">np.percentile(data, 75) - np.percentile(data, 25)</span>

<!--s-->

## Skewness

A measure of the lack of "symmetry" in the data.

**Positive skew (> 0)**: the right tail is longer; the mass of the distribution is concentrated on the left of the figure.

**Negative skew (< 0)**: the left tail is longer; the mass of the distribution is concentrated on the right of the figure.

```python
import numpy as np
from scipy.stats import skew

data = np.random.normal(0, 1, 1000)
print(skew(data))
```

<!--s-->

## Skewness | Plot

<iframe width = "80%" height = "80%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/skewness.html" title="scatter_plot"></iframe>

<!--s-->

## Kurtosis

A measure of the "tailedness" of the distribution.

- **Leptokurtic (> 3)**: the tails are fatter than the normal distribution.

- **Mesokurtic (3)**: the tails are the same as the normal distribution.

- **Platykurtic (< 3)**: the tails are thinner than the normal distribution.

```python
import numpy as np
from scipy.stats import kurtosis

data = np.random.normal(0, 1, 1000)
print(kurtosis(data))
```



<!--s-->

## Kurtosis | Plot

<iframe width = "80%" height = "80%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/kurtosis.html" title="scatter_plot" padding=2em;></iframe>

<!--s-->

<div class="header-slide">

# Graphical EDA 

</div>

<!--s-->

## Graphical EDA | Data Types

There are three primary types of data -- nominal, ordinal, and numerical.

| Data Type | Definition | Example |
| --- | --- | --- |
| Nominal | Categorical data without an inherent order | <span class="code-span">["red", "green", "orange"]</span> |
| Ordinal | Categorical data with an inherent order | <span class="code-span">["small", "medium", "large"]</span> <p><span class="code-span">["1", "2", "3"]</span> |
| Numerical | Continuous or discrete numerical data | <span class="code-span">[3.1, 2.1, 2.4]</span> |

<!--s-->

## Graphical EDA | Choosing a Visualization

The type of visualization you choose will depend on:

- **Data type**: nominal, ordinal, numerical.
- **Dimensionality**: 1D, 2D, 3D+.
- **Story**: The story you want to tell with the data.

Whatever type of plot you choose, make sure your visualization is information dense **and** easy to interpret. It should always be clear what the plot is trying to convey.

<!--s-->

## Graphical EDA | Common Visualization Types

<div class = "col-wrapper">
<div class="c1" style = "width: 50%">

### 1D Data
- Bar chart
- Pie chart
- Histogram
- Boxplot
- Violin plot
- Line plot

### 2D Data
- Scatter plot
- Heatmap
- Bubble plot
- Line plot
- Boxplot
- Violin plot

</div>
<div class="c2 col-centered" style = "width: 50%;">

### 3D+ Data

- 3D scatter plot
- Bubble plot
- Color scatter plot
- Scatter plot matrix

</div>
</div>

<!--s-->

## A Note on Tools

Matplotlib and Plotly are the most popular libraries for data visualization in Python.

| Library | Pros | Cons |
| --- | --- | --- |
| Matplotlib | Excellent for static publication-quality plots, very fast render, old and well supported. | Steeper learning curve, many ways to do the same thing, no interactivity, OOTB color schemes. |
| Plotly | Excellent for interactive plots, easy to use, easy tooling for animations, built-in support for dashboarding and publishing online. | Not as good for static plots, less fine-grained control, high density renders can be non-trivial. |

<!--s-->

## 1D Data | Histograms

When you have numerical data, histograms are a great way to visualize the distribution of the data. If there is a clear distribution, it's often useful to fit a probability density function (PDF).

<div class = "col-wrapper">
<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python
import numpy as np
from plotly import express as px

data = np.random.normal(0, 1, 100)
fig = px.histogram(data, nbins = 50)
fig.show()
```

</div>
<div class="c2 col-centered" style = "width: 60%; padding: 0; margin: 0;">

<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/histogram.html" title="scatter_plot" padding=2em;></iframe>

</div>
</div>

<!--s-->


## 1D Data | Boxplots

Boxplots are a great way to visualize the distribution of the data, and to identify outliers.

<div class = "col-wrapper">
<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python
import numpy as np
from plotly import express as px

data = np.random.normal(0, 1, 100)
fig = px.box(data)
fig.show()
```

</div>
<div class="c2 col-centered" style = "width: 60%; padding: 0; margin: 0;">
<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/boxplot.html" title="scatter_plot" padding=2em;></iframe>
</div>
</div>

<!--s-->

## 1D Data | Violin Plots

Violin plots are similar to box plots, but they also show the probability density of the data at different values.

<div class = "col-wrapper">

<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python

import numpy as np
from plotly import express as px

data = np.random.normal(0, 1, 100)
fig = px.violin(data)
fig.show()
```

</div>
<div class="c2 col-centered" style = "width: 60%; padding: 0; margin: 0;">
<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/violin.html" title="scatter_plot" padding=2em;></iframe>
</div>
</div>

<!--s-->

## 1D Data | Bar Charts

Bar charts are a great way to visualize the distribution of **categorical** data.

<div class = "col-wrapper">
<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python

import numpy as np
from plotly import express as px

data = np.random.choice(["A", "B", "C"], 1000)
fig = px.histogram(data)
fig.show()
```

</div>
<div class="c2 col-centered" style = "width: 60%; padding: 0; margin: 0;">
<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/bar.html" title="scatter_plot" padding=2em;></iframe>
</div>
</div>

<!--s-->

## 1D Data | Pie Charts

Pie charts are another way to visualize the distribution of categorical data.

<div class = "col-wrapper">
<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python

import numpy as np
from plotly import express as px

data = np.random.choice(["A", "B", "C"], 100)
fig = px.pie(data)
fig.show()
```

</div>
<div class="c2 col-centered" style = "width: 60%; padding: 0; margin: 0;">
<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/pie.html" title="scatter_plot"  padding=2em;></iframe>
</div>
</div>

<!--s-->

## 2D Data | Scatter Plots

Scatter plots can help visualize the relationship between two numerical variables.

<div class = "col-wrapper">
<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python
import numpy as np
from plotly import express as px

x = np.random.normal(0, 1, 100)
y = np.random.normal(0, 1, 100)
fig = px.scatter(x = x, y = y)
fig.show()
```

</div>
<div class="c2 col-centered" style = "width: 60%; padding: 0; margin: 0;">
<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/scatter.html" title="scatter_plot"  padding=2em;></iframe>
</div>
</div>

<!--s-->

## 2D Data | Heatmaps (2D Histogram)

Heatmaps help to visualize the density of data in 2D.

<div class = "col-wrapper">
<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python
import numpy as np
from plotly import express as px

x = np.random.normal(0, 1, 100)
y = np.random.normal(0, 1, 100)
fig = px.density_heatmap(x = x, y = y)
fig.show()
```

</div>
<div class="c2" style = "width: 60%">
<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/heatmap.html" title="scatter_plot"  padding=2em;></iframe>
</div>
</div>

<!--s-->

## 3D+ Data | Bubble Plots

Bubble plots are a great way to visualize the relationship between three numerical variables and a categorical variable.


<div class = "col-wrapper">
<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python
import numpy as np
from plotly import express as px

x = np.random.normal(0, 1, 100)
y = np.random.normal(0, 1, 100)
z = np.random.normal(0, 1, 100)
c = np.random.choice(["A", "B", "C"], 100)
fig = px.scatter(x = x, y = y, size = z, color = c)
fig.show()
```

</div>
<div class="c2" style = "width: 60%">
<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/bubble_plot.html" title="scatter_plot" padding=2em;></iframe>
</div>
</div>

<!--s-->

## 3D+ Data | Scatter Plots

Instead of using the size of the markers (as in the bubble plot), you can use another axis to represent a third numerical variable. And, you still have the option to color by a categorical variable.

<div class = "col-wrapper">
<div class="c1 col-centered" style = "width: 40%; padding: 0; margin: 0;">

```python
import numpy as np
from plotly import express as px

x = np.random.normal(0, 1, 100)
y = np.random.normal(0, 1, 100)
z = np.random.normal(0, 1, 100)
c = np.random.choice(["A", "B", "C"], 100)

fig = px.scatter_3d(x = x, y = y, z = z, color = c)
fig.show()
```

</div>
<div class="c2" style = "width: 50%">
<iframe width = "100%" height = "100%" src="https://storage.googleapis.com/cs326-bucket/lecture_3_plots/scatter_3d.html" title="scatter_plot" padding=2em;></iframe>
</div>
</div>

<!--s-->

## TLDR;

- **Descriptive EDA**: Summarizing the main characteristics of the data.
- **Graphical EDA**: Visualizing the data to understand its structure and patterns.

<!--s-->

## Wrapping Up

- Thank you for attending this pre-recorded lecture! You will see some of these concepts in H.02, so make sure to review this material before starting the homework.

- A reminder that Chongyang has graciously agreed to be in G15 during our normal class time on Thursday. Please feel free to stop by if you have any questions.

<!--s-->