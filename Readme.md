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
    .query("type == 'conventional' and region == 'Albany'")
    .assign(Date=lambda data: pd.to_datetime(data["Date"], format="%Y-%m-%d"))
    .sort_values(by="Date")
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

## Source dta

|Year|Jan|Feb|Mar|Apr|May|Jun|Junly|Aug|Sep|Oct|Nov|Dec|
2563,125.00, 138.64, 115.92, 92.52, 97.63, 90.95, 100.30, 100.00, 120.98,0,0,0
2564,158.00, 165.18, 130.09, 117.95, 140.98, 99.10, 72.10, 78.20,0,0,0,0
2565,0, 196.67, 130.76, 78.29, 77.28, 94.86,118.48, 0,0,0,0,0
2566,0, 114.68, 77.35, 111.55, 92.01, 104.90, 103.06, 101.59, 101.07,0,0,0,

