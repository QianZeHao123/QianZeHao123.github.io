---
title: 'About the Python Program Runtime Environment: A brief contrast between Conda and Docker'
date: 2022-11-17
permalink: /posts/2022/11/conda-docker-for-python/
tags:
  - Computer Science
---

![](/images/blog-20221117-condadocker.png)

# Conda for development environments and Docker for production environments

At least one thing is certain, I will not install Python interpreters and pip packages in computer systems, obsessive-compulsive means that installing different Python interpreters and third-party packages into the User directory is very "inelegant", and at the same time, Linux will also download some Python things as auxiliary tools when updating the system, so I usually write Python is a new environment.

## Development environment: conda

The development environment writes some Python scripts or replicates other people's papers, sometimes more sensitive to version dependencies, such as Python 3.7 or relatively new Python 3.10, may be installed third-party dependencies, under 3.7 can run normally and 3.10 will report errors...


And the same Python interpreter, I also like to configure different conda environments, such as scientific research drawing and data processing, I generally install the following third repository, such as: numpy pandas matplotlib scipy sympy jupyter, etc.; In the environment of some deep learning projects, I will install dependencies such as Pytorch Tensorflow, OpenCV, etc. In this way, the configuration of the conda environment is very refreshing, and the idea of your own project will be very clear, and you can directly conda activate [env] in which direction to do.


I have also tried a lot of Python virtual environment management tools, pipenv (brought into the pit by the book Flask to get started), venv, pyenv, after using a circle, I feel that the development environment is still conda is the most elegant, it is recommended to download miniconda instead of anaconda, small size is not so many packages!

## Production environment: It has to be Docker

ARM devices such as the Raspberry Pi have not succeeded in installing miniconda several times, and conda and its environment also take up the storage space of the Raspberry Pi. Therefore, usually some scheduled tasks run on RPi, I usually write code on the computer, run it under conda, write a dockerfile if there is no problem, and then package and send it to the Raspberry Pi, and finally run the Python code on the docker build & docker run on the Raspberry Pi docker~

