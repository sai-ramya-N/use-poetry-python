# Poetry Python Workflow

## How to use python with poetry and virtual environment

### Steps

1. Create a Project

    ```pwsh
    mkdir use-poetry-python
    ```

1. Navigate to the created directory and open it in editor

    ```pwsh
    cd .\use-poetry-python\
    ```

1. Initialize Git Repository

    ```pwsh
    git init
    ```

1. Create Virtual Environment

    ```pwsh
    python -m venv .venv
    ```

1. Initialize Poetry and generate `pyproject.toml`

    ```pwsh
    poetry init
    ```

1. Activate Virtual Environment

    ```pwsh
    .\.venv\Scripts\Activate.ps1

    # To Deactivate (after completing all the steps)
    deactivate
    ```

1. Install Poetry using pip inside activated virtual environment

    ```pwsh
    pip install poetry
    ```

    **NOTE**: this step is a temporary workaround for a unknown bug

1. Select a Interpreter (in the bottom left corner in VScode or else use the below command for auto detection) to use python venv version if not chosen automatically

    ```json
    "python.defaultInterpreterPath": ".venv\\Scripts\\python.exe",
    ```

    **NOTE**: this should be added as default user settings in VSCode (`Ctrl + ,`)

1. Create `.gitignore` file and add `.venv` folder to it

1. Install Dependencies

    ```pwsh
    # normal dependecies
    poetry add <package_name>

    # developer dependencies
    poetry add -D <package_name>
    ```

1. Export the dependencies to `requirements.txt` for use for others

    ```pwsh
    poetry export -f requirements.txt --output requirements.txt
    ```

### Usage in other computers

1. Create a Virtual Environment to safely install python packages.

    ```pwsh
    python -m venv .venv
    ```

1. Install the packages when `requirements.txt` is present

    ```pwsh
    pip install -r requirements.txt
    ```

    - Also freeze the installed packages using freeze (not recommended when using poetry)

        ```pwsh
        pip freeze > requirements.txt
        ```

    - Always note down what packages are being installed when not using poetry or pipenv

