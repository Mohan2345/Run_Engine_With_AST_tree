# Application-1 :  Run_Engine_With_AST_tree

### The given file is in ZIP Format so first extract the files after that apply following procedure...


### Installation

I have tried my best to make it platform agnostic, and packaged everything into a
Docker Container. You can also execute the below seperately for running them on
your machine without Docker.

- Frontend
  ```bash
  cd frontend/
  npm install
  ```
- Backend
  If `poetry` isn't previously installed, install it first.
  ```bash
  python3 -m venv $VENV_PATH
  $VENV_PATH/bin/pip install -U pip setuptools
  $VENV_PATH/bin/pip install poetry
  ```
  
  Then continue to create a venv, and install dependencies

  ```bash
  cd backend/
  poetry install
  ```

- Database
  After a `poetry install`, execute the following to setup raw data in your
  postgres instance. Make sure to populate the connection creds in the `.env`.

  ```bash
  docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres
  ```

### How to run

Expecting that above installation process, suceeded.

- Frontend
  ```bash
  npm run dev
  ```
- Backend
  ```bash
  poetry run python main.py --dev
  ```
- Database
  ```bash
  docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres
  ```


