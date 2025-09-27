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

## Installation 

```python
-- app.py
import pandas as pd
from dash import Dash, dcc, html

data = (
    pd.read_csv("avocado.csv")
    .query("type == 'conventional' and region == 'Albany'")
    .assign(Date=lambda data: pd.to_datetime(data["Date"], format="%Y-%m-%d"))
    .sort_values(by="Date")
)

app = Dash(__name__)

```
