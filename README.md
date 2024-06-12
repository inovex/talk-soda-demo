# soda-demo
- Project contains Soda Demo Codes in a Jupyter notebook which focuses mainly on functionalities of Soda Scans using the Soda Core Python library
- Soda Core is here connected with Soda Cloud and considers as data source PostgreSQL

## Project Setup

### Download demo data
- Demo data used in this project is the "Bus Breakdown and Deplays" data from NYC Open Data downloaded from: https://github.com/sodadata/tutorial-demo-project/tree/main/data/ny_bus_breakdown (description of the data: https://data.cityofnewyork.us/Transportation/Bus-Breakdown-and-Delays/ez4e-fazm/about_data)

### Setup data source
- In this demo we are considering PostgreSQL as data source
- Setup PostgreSQL with docker locally with
    ```
    sudo docker run --name postgresql1 -e POSTGRES_PASSWORD=test -v ${HOME}/postgres-data/:/var/lib/postgresql/data -p 5432:5432 -d postgres:15.2
    ```

### Import downloaded data into datasource
- Import the downloaded "bus_breakdown_and_delays.csv" file into a PostgreSQL database (import `incident_number` column as `varchar`)
    - database: `demo`
    - user: `postgres`
    - schema: `public`
    - table name: `bus_breakdown_and_delays`
- Tools like pgAdmin, dbeaver can be used to import the data

### Setup Python virtual environment and install Jupyter
- Requirements: Python 3.8 or greater; Pip 21.0 or greater
- Create a Python virtual environment
    ```
    virtualenv path/to/venv/soda_env
    ```
- Activate the virtual environment
    ```
    source path/to/venv/soda_env/bin/activate
    ```
- Install Jupyter
    ```
    pip install jupyter
    ```
- Start jupyter notebook in the project directory
    ```
    jupyter notebook
    ```
- Open the notebook file `soda_demo_notebook.pynb`

### Setup Soda Cloud Account with API keys
- Navigate to https://cloud.soda.io/signup and create a new Soda account (free 45-day trial)
- Log in into your account and navigate to **your avatar** > **Profile** then access the **API keys** tab
- Click the plus icon to generate new API keys
- Save the API key values locally
- Replace the values for `api_key_id` and `api_key_secret` in the `configuration.yml` with the generated values (Do not push the changes in the `configuration.yml` into repository)