# Using the Pre-Commit Framework

To use the **pre-commit** framework, follow these steps:

### 1. Install Pre-Commit
Install the `pre-commit` package via pip:
```bash
pip install pre-commit
```

### 2. Create the YAML Configuration File
Create a .pre-commit-config.yaml file in the root of your repository. In this file, reference the hooks by name. You can find available hooks in the pre-commit repository.

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

### 3. Install the Hooks

Run the following command to set up the hooks:
```bash
pre-commit install
```

### 4. Done!

You can run the following line to execute the scripts or work as normal.
```bash
pre-commit run --all-files
```
