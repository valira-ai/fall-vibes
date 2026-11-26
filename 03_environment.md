# 03 · Create the environment

The agent sets up the environment, proves it works, and writes the commands into CLAUDE.md for next time.

```text
Set up a local development environment for this project.

- Create a virtual environment in .venv with the system Python 3 and install requirements.txt into it. Don't install anything globally.
- Check that it works without starting the server: import streamlit and pandas, and run the app once headlessly with streamlit.testing.v1.AppTest. Run that check from a temporary script outside the repo, not as a new file in the repo. Report any exceptions or warnings.
- Tell me the installed versions of Python, streamlit, and pandas.
- Add a short "Commands" section to CLAUDE.md: how to create the env, how to run the app, and that you should always use .venv instead of the system Python. Also note that you shouldn't start the app server unless I ask.
```

Using `uv` or conda? Replace the first bullet with "Create the environment with `uv venv` and `uv pip install -r requirements.txt`" or "Create a conda env named `gdp` from requirements.txt".
