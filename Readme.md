# Dashboard for python Project

### Tools and Software
- Streamlit, flast, React,  - web framework
- Pandas - a data analysis Library
- Altair - a data visualization library
- Plotly Express - a terse and high-level API for creating figures
- HTML CSS Javascript Typescript - Web Development

## Development start
- Installation Tools Softw Library
- Configuration
- Load Data
- Preprea Data
- select plot graph  chart
- Build & Test
- Deploy

## How do it?

```bash
## bash ##

mkdir dash-app-project
cd dash-app-project

python -m venv venv
source venv/bin/activate

(venv) $ python -m pip install dash==2.8.1 pandas==1.5.3

```

## Defination dashboard project 

```python
-- app.py
import pandas as pd
from dash import Dash, dcc, html

data = (
    pd.read_csv("durian.csv")
)

app = Dash(__name__)

```

## Laytout DashBoard for Durian

```python

# ...

app.layout = html.Div(
    children=[
        html.H1(children="Durian Analytics"),
        html.P(
            children=(
                "Analyze the behavior of Druian prices and the number"
                " of Druian sold in the TH between 2015 and 2025"
            ),
        ),
        dcc.Graph(
            figure={
                "data": [
                    {
                        "x": data["Date"],
                        "y": data["AveragePrice"],
                        "type": "lines",
                    },
                ],
                "layout": {"title": "Average Price of Druian"},
            },
        ),
        dcc.Graph(
            figure={
                "data": [
                    {
                        "x": data["Date"],
                        "y": data["Total Volume"],
                        "type": "lines",
                    },
                ],
                "layout": {"title": "Druian Sold"},
            },
        ),
    ]
)


```

## Set HTML file

HTML

```html

<div>
  <h1>Durian Thainland Analytics</h1>
  <p>
    Analyze the behavior of Durian prices and the number
    of Durian sold in the TH between 2015 and 2025
  </p>
  <!-- Rest of the app -->
</div>

```

## Run on Server

Python 
```python
-- app.py
if __name__ == "__main__":
    app.run_server(debug=True)

```


## Set CSS 

CSS
```python
html.H1(
    children="Durian Analytics",
    style={"fontSize": "48px", "color": "red"},
),
```

```css
.header-title {
  font-size: 48px;
  color: red;
}
```

## Source data


| Year  | Jan | Mar  | Apr | May  |  Jun | July  |  Aug | Sep  | Oct  |  Nov | Dec  |
|---|---|---|---|---|
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |


