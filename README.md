# Setting Up Manual Git Hooks for LLM Fine-tuning

This tutorial does not focus on implementing LLM finetuning. For that tutorial, refer [here](https://github.com/dlops-io/llm-finetuning/).

[Pre-commit hooks](https://git-scm.com/book/ms/v2/Customizing-Git-Git-Hooks#_client_side_hooks) are programs that automatically run when the user commits, but before the commit is registered on the index. It is used to inspect the code to check for syntax, run tests or any other function.

This tutorial builds client-side hooks using the t**pre-commit** framework to run locally during the pre-commit phase.

To set it up, follow these steps:

### Step 1: Install Pre-Commit
Install the `pre-commit` package via pip:

```bash
pip install pre-commit
```
### Step 2: Create the YAML Configuration File

Create a `.pre-commit-config.yaml` file in the root of your repository. In this file, reference the hooks by name. You can find available hooks in the [pre-commit repository](https://github.com/pre-commit/pre-commit-hooks/tree/main/pre_commit_hooks).

Example configuration:
```bash
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v5.0.0  # Specify the version of the repo
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
  - repo: https://github.com/psf/black
    rev: 24.10.0
    hooks:
      - id: black
        args: ["--line-length", "120"]  # Customize line length for Black (default is 88)
```
Save this file as `.pre-commit-config.yaml`.

### Step 3: Install the Hooks

Run the following command to set up the hooks:
```bash
pre-commit install
```

### Step 4: Done!

You can run the following line to execute the scripts or work as normal.
```bash
pre-commit run --all-files
```
