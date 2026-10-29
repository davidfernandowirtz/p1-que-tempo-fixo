# Project description
In this project we are downloading meteo data and clean it with pandas library, analyzing temperatures or precipitations and saving data in PostgreSQL
Meteo data of A Coruna

# Data Source and Usage Conditions
- Source: Meteosat API
- URL : https://github.com/bigdatawirtz/datasets/raw/refs/heads/main/datasets/meteo_alvedro_2021_2025.csv
- License: Free use

# Run Project

## Step 1: Clone the Repository

```bash
git clone [url]
cd [folder]
```
Step 2: Install Python
```bash
uv python install 3.12
```
Step 3: Create and activate the virtual environment
```bash
uv venv --python 3.12 .venv
source .venv/bin/activate
```
Step 4: Install dependencies
```bash
uv pip install -r requirements.txt
```
Step 5: Copy .env.example to .env file
```bash
cp .env.example .env
```
Step 6: Start docker
```bash
docker compose up
```

# Cleaning decision

- Missing values -> Interpolate with neightbours
- Invalid values ->  
    - Temperature and Presion nulls
        - We are gonna to interpolate the nulls values with next values to it.
    - Prec nulls
        - Its better to not invent prec data, so we have to stay the null values as it is.

## How I Realized There Were Errors in the Data
 At first, I read the CSV file and figured out the main ones (delimiter, decimals...), and then what really helped me spot the other errors was creating a chart of the different columns