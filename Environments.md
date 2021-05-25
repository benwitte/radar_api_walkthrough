# Anaconda, Python and Environments

When working in python, it's highly recommended each project is set up with its own environment (full Anaconda documentation on environments [here](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands)). This is because python, unlike R, has a less centralized nature when it comes to downloading things.

For **in-depth explanations** on why this is and best practices, I recommend these resources:

- [Python Virtual Environments: A Primer](https://realpython.com/python-virtual-environments-a-primer/)
- [Environments, Conda, Pip, aaaaah! - Managing Python environments without a headache](https://towardsdatascience.com/environments-conda-pip-aaaaah-d2503877884c)
- [Using Pip in a Conda Environment](https://www.anaconda.com/blog/using-pip-in-a-conda-environment)


## Setting up a New Environment with Anaconda

1. Open Anaconda, click on the **Environments** tab on the left.

2. Towards the bottom left, click **Create**. Name your environment and choose its location.

3. Make sure your new environment is selected now, **not base (root).**

4. Click the **Home** tab on the left and install **JupyterLab.** You can also install Jupyter Notebook, but it has less functionality than JupyterLab.

5. While that's installing, open your terminal/command line interface.

6. Type and run the following command: `conda activate <name_of_your_environment>`

7. Use conda and pip to install all necessary packages. As a rule, install conda first and pip second. **If there's a conda version of a package as well as a pip version, install the conda version.** If you want to install all packages from a .txt file as is considered a best practice, the second resource above explains how to do that.

8. When you're done working on the project, simply type and run: `conda deactivate`