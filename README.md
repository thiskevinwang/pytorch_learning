# Setup

```sh
python3 -m venv .venv
source .venv/bin/activate
which python
deactivate

python3 -m pip install --upgrade pip
python3 -m pip --version
```

Pre requirements.txt:

```sh
python3 -m pip install torch pandas matplotlib scikit-learn numpy ipykernel
python3 -m pip freeze > requirements.txt
```

Post requirements.txt:

```sh
python3 -m pip install -r requirements.txt
```

### Using VSCode Jupyter Notebooks w/ local

https://code.visualstudio.com/docs/datascience/jupyter-notebooks

- Cmd+Shift+P; "Python: Select Interpreter", and choose the one like `./.venv/bin/python`,

## Misc

Generating `nyc_taxi.csv` from https://sql.clickhouse.com/:

```sql
SELECT
toStartOfDay(pickup_datetime) t,
count(*) c
 FROM nyc_taxi.trips
WHERE
    t >= '2009-01-01 00:00:00'::DateTime AND
    t <= '2021-07-31 00:00:00'::DateTime
 GROUP BY t
```
