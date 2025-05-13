# Interactive Correlation Analysis Demo

## Understanding Correlation

**Figure:** Example scatterplot where points roughly cluster around a line. The Pearson correlation coefficient *r* quantifies the strength and direction of this linear relationship between two variables. A single value of *r* (between –1 and +1) summarizes how tightly the data follow a straight line. Values near +1 indicate a strong positive linear association (both variables increase together); values near –1 indicate a strong negative linear association (one variable decreases as the other increases). An *r* of 0 implies no linear correlation. In practice, use Pearson correlation when both variables are quantitative (continuous) and roughly linearly related.

## When to Use Pearson Correlation

* Both variables should be **numeric (quantitative)**, not categorical.
* The relationship between variables should be **approximately linear** (Pearson’s *r* measures linear trends).
* **Outliers** should be minimal, as extreme values can distort the correlation.
* For inference, assume the data are roughly normally distributed (so that the *p*-value is reliable).

## Interpreting Pearson’s *r* and *p*-value

* *r* ranges from **–1 to +1**. An *r* of ±1 means a perfect linear relationship; an *r* near 0 means little or no linear association.
* The **sign** of *r* indicates direction: positive *r* (as X increases, Y increases) or negative *r* (as X increases, Y decreases).
* **Strength:** As a rough guide, |*r*| > 0.5 is often considered strong, 0.3–0.5 moderate, and <0.3 weak.
* The *p*-value (from testing the null hypothesis of no correlation) tells us whether the observed *r* is statistically significant. A small *p* (e.g. < 0.05) suggests the correlation is unlikely to have arisen by chance.
* **Note:** Correlation does *not* imply causation – even a high *r* does not prove that one variable causes the other to change.

## Code Example: Interactive Correlation Plot

Below we use the classic Iris dataset (flower sepal/petal measurements) to demonstrate an interactive scatterplot with Pearson correlation. For example, Seaborn’s **tips** dataset (restaurant bills and tips) is often used for similar demos. We use `ipywidgets` to create dropdown menus for selecting any two numeric columns, and `scipy.stats.pearsonr` to compute *r* and its *p*-value. Changing the dropdowns will update the plot and correlation output immediately.

```python
# Load libraries and data
import pandas as pd
import matplotlib.pyplot as plt
from scipy.stats import pearsonr
import ipywidgets as widgets
from sklearn.datasets import load_iris

# Load the Iris dataset into a pandas DataFrame
iris = load_iris()
feature_names = [name.replace(" (cm)","").replace(" ","_") for name in iris.feature_names]
df = pd.DataFrame(iris.data, columns=feature_names)
```

This dataset contains numeric measurements like sepal length/width and petal length/width. We extract the numeric columns for the dropdown options:

```python
# Identify numeric columns
numeric_cols = df.select_dtypes(include='number').columns.tolist()
numeric_cols
```

Next, create two dropdown widgets for the user to select the X and Y variables, and define a function that draws the scatterplot and prints the Pearson correlation whenever the selection changes:

```python
# Create dropdown menus for selecting variables
dropdown_x = widgets.Dropdown(options=numeric_cols, value=numeric_cols[0], description='X:')
dropdown_y = widgets.Dropdown(options=numeric_cols, value=numeric_cols[1], description='Y:')

def update_plot(x, y):
    """
    Plot X vs Y as a scatterplot and display Pearson correlation and p-value.
    This function is called automatically when dropdown values change.
    """
    plt.figure(figsize=(6,4))
    plt.scatter(df[x], df[y], color='blue')
    plt.xlabel(x.replace("_"," ").title())
    plt.ylabel(y.replace("_"," ").title())
    plt.title(f"{x.replace('_',' ').title()} vs {y.replace('_',' ').title()}")
    plt.grid(True)
    plt.show()
    
    # Calculate Pearson r and p-value
    r, p = pearsonr(df[x], df[y])
    print(f"Pearson correlation r = {r:.2f}, p-value = {p:.4f}")

# Link the update function to the dropdowns using interactive_output
out = widgets.interactive_output(update_plot, {'x': dropdown_x, 'y': dropdown_y})

# Display the widgets and output vertically
widgets.VBox([widgets.HBox([dropdown_x, dropdown_y]), out])
```

Running the above cells in Jupyter (Notebook or Lab) will display two dropdowns labeled **X** and **Y**, along with an output area. Selecting different variables from the menus will **automatically** update the scatterplot and correlation results. This interactive setup helps students explore and visualize correlations in real time.

*Make sure `ipywidgets` is installed and enabled in your Jupyter environment. In older notebooks you may need `%matplotlib inline` and to enable the widgets extension.*

**Sources:** Authoritative definitions and explanations of Pearson’s *r*; details on dataset contents; and `ipywidgets` usage in Jupyter.

