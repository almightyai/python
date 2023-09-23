---
layout: default
title: Virtual Environments venv and virtualenv
parent: Quick Setup Python Environment and Tools
grand_parent: Python Foundations
nav_order: 2
---
# "Virtual Environments: venv and virtualenv"

## Introduction

In the world of programming, developers often work on multiple projects simultaneously. Each project can have its own set of dependencies, libraries, and versions of Python. Managing these different environments can be a real challenge. This is where virtual environments come in handy.

## What is a Virtual Environment?

A virtual environment is an isolated working copy of Python and its associated libraries. It allows developers to create an environment with its own set of packages, independent of the globally installed packages.

Virtual environments help prevent conflicts between different projects that may rely on different versions of the same library. They ensure that each project runs with a consistent and reproducible set of dependencies.

In Python, there are two commonly used tools for creating virtual environments: `venv` and `virtualenv`.

## venv

`venv` is a built-in module in Python 3. It provides a lightweight and straightforward way to create and manage virtual environments.

To create a virtual environment using `venv`, open your terminal and navigate to the project directory. Then, run the following command:

```
python3 -m venv myenv
```

This command creates a new virtual environment named `myenv` in the current directory. The `-m` flag tells Python to run `venv` as a module.

To activate the virtual environment, use the appropriate command for your operating system:

- On macOS and Linux:
  ```
  source myenv/bin/activate
  ```

- On Windows:
  ```
  myenv\Scripts\activate
  ```

Once activated, you will see `(myenv)` prefixed to your command prompt, indicating that you are now working within the virtual environment.

To install packages in the virtual environment, you can use `pip` as you normally would. The packages will be installed within the virtual environment, separate from your global Python installation.

To exit the virtual environment, simply run the `deactivate` command.

## virtualenv

`virtualenv` is another popular tool for creating virtual environments. It is compatible with both Python 2 and 3.

To install `virtualenv`, use `pip`:

```
pip install virtualenv
```

After installing `virtualenv`, navigate to your project directory in the terminal and run the following command to create a virtual environment:

```
virtualenv myenv
```

This command creates a new virtual environment named `myenv` in the current directory.

To activate the virtual environment with `virtualenv`, use the appropriate command for your operating system:

- On macOS and Linux:
  ```
  source myenv/bin/activate
  ```

- On Windows:
  ```
  myenv\Scripts\activate
  ```

Once activated, you will see `(myenv)` prefixed to your command prompt, indicating that you are now working within the virtual environment.

To install packages in the virtual environment, you can use `pip` just like you would with `venv`.

To exit the virtual environment, simply run the `deactivate` command.

## Choosing Between venv and virtualenv

Both `venv` and `virtualenv` are capable tools for creating virtual environments. If you are working with Python 3, `venv` is the recommended choice as it is a built-in module. However, if you are working with an older version of Python, you should opt for `virtualenv`.

Contextual Example:
Imagine you are working on two Python projects, Project A and Project B. Project A requires Python 3.9 and Package X version 1.0, while Project B requires Python 3.7 and Package X version 1.2. Without virtual environments, you would need to constantly switch between Python versions and install/uninstall the different versions of Package X to work on each project. With virtual environments, you can create separate environments for each project, allowing them to coexist peacefully. Thus, you can easily switch between the two projects without worrying about compatibility issues.

## Conclusion

Virtual environments, like `venv` and `virtualenv`, are essential tools for Python developers. They enable seamless project management by isolating dependencies, ensuring consistency, and preventing conflicts. By using virtual environments, developers can transition smoothly between projects and embrace the philosophy, features, and best practices of Python.