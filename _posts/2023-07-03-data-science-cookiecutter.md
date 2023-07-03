---
layout: post
author: rgalindor
title: MLOps project template
subtitle: A free Data Science cookiecutter template
excerpt: Free template with cookiecutter for MLOps with poetry
background: '/img/posts/crop-faceless-dev-on-software.jpg'
comments: true
usemathjax: true
---

Some organizations succesfully implement _Machine Learning_ into their day to day operations. It is not a secret that the majority (more than 80%) of the ML projects never end in productive stages. So, how these organizations achieve ML productive implementation? There is no simple answer to this question, rather they rely in cultural adoption of MLOps.

## MLOps

A culture requires that members of an organization are able to communicate between each others with a common language and they work together to a common goal. So this is not the tech stack, nor a software role that a data scientist can perform by himself/herself. [MLOPS](https://www.datacamp.com/courses/mlops-concepts) involves a series of practices that helps an ML project to manage process focused on developing, deploying, monitoring and mantaining machine learning models.

To succesfully deploy a model into productive stage, it is required that a set of different highly specialized roles work together, among other roles this is an example list of important roles for MLOps implementation:

- Subject Matter Experts
- Data Engineers
- Data Scientists
- ML Engineers
- Software Engineers
- Project Managers
- Site Reliability Engineers
- QA Engineers
- Businness Analysts
- UX Designers
- Product Owners
- Tech Writers

## Project requirements

It has been stated that MLOps allow the interoperability between different proceesses:

### Developing

It is important to continually develop new models. These models require to guarantee repeatibility and reproducibility. There is a lot of best practices that lies on data reliability, such as governance, versioning, just to mention a couple of them. 

### Deploying

Scalability is a key factor to keep in mind at this stage. However there are other factors such as availability that requires automation of these processes to a succesful implementation.

### Monitoring

The models would decrease their performance, this could be because new data could be evolving to a point that the productive model is no longer succesful to predict accurately new records. So it is very important to keep track on the historical performance of every model. Evaluations and obserbability are key points on this processes.

### Mantaining

The project is alive so there could be new people being introduced to the project, and people leaving it. Mantaining the code, the model and processes is very important to allow the future improvements for the project.

## How to set up a project

As a data scientist you probably would require a quick way to start up a new project with a template that automates the initial setting up. Sometimes this could be overwhelming, nonetheless thanks to some tools like `Poetry` for dependecy managements in `Python` and also `cookiecutter` for project templates.

Those are the only requirements, but if you execute the following lines you must be able to continue:

```bash
curl -sSL https://install.python-poetry.org | python3 -
poetry --version
```

```bash
pip install cookiecutter # you can also use conda to encapsulate this
```


Then you are ready to call for the [Data Science template](https://github.com/rgalindor/data-science-cookiecutter):

```bash
cookiecutter https://github.com/rgalindor/data-science-cookiecutter --checkout main
```

This would prompt you to set interactively a new `git` repository. Once you finnished the setup you would be able to install the base dependencies and start working on your new environment.

```bash
cd <your-local-repo>
poetry install
```


And thats it! You can start to create your own models and starting their lifecycle!

> [Photo](https://www.pexels.com/photo/crop-faceless-developer-working-on-software-code-on-laptop-5926382/?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels) by Sora Shimazaki from Pexels