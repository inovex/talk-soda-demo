# soda-demo
- Project contains Soda Demo Codes in a Jupyter notebook which focuses mainly on functionalities of Soda Scans using the Soda Core Python library
- Soda Core is here connected with Soda Cloud and considers as data source PostgreSQL

## Project Setup


### Setup data source
- In this demo we are considering PostgreSQL as data source

- Setup PostgreSQL with docker locally with
    ```
    sudo docker run --name postgresql1 -e POSTGRES_PASSWORD=test -v ${HOME}/postgres-data/:/var/lib/postgresql/data -p 5432:5432 -d postgres:15.2
    ```

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
- Open and run the notebook file `setup_notebook.ipynb`
- Open the notebook file `soda_demo_notebook.pynb`
 

### Setup Soda Cloud Account with API keys
- Navigate to https://cloud.soda.io/signup and create a new Soda account (free 45-day trial)
- Log in into your account and navigate to **your avatar** > **Profile** then access the **API keys** tab
- Click the plus icon to generate new API keys
- Save the API key values locally
- Replace the values for `api_key_id` and `api_key_secret` in the `configuration.yml` with the generated values (Do not push the changes in the `configuration.yml` into repository)