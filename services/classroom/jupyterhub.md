---
title: JupyterHub
icon: code-greater-than-or-equal
---
# Introduction

Brown's JupyterHub service  provides a convenient, cloud-hosted way to serve Jupyter Notebooks for multiple users. Notebooks are launched within a pre-configured computing environment; users do not need to install any software packages. This set-up free environment is ideal for courses and workshops where instructors intend for students to begin coding with minimal obstacles. Jupyter’s flexibility allows instructors to pick the preferred language for a particular context, including Python, Julia, R and many more. Regardless of the language chosen, the Jupyter interface remains the same. To learn more about using Jupyter Notebooks for teaching and learning, [please visit the guide.](https://jupyter4edu.github.io/jupyter-edu-book/jupyter.html)

On Brown's JupyterHub, each user is provided a persistent working directory and compute resource allocation. This means the environment you are provided is only accessible by yourself and OIT support staff. 

Once connected to JupyterHub servers, users enter an isolated workspace to write and run code. There are no time limit restrictions or specified lockout times, so feel free to use your personal JupyterHub server as needed and adhere to CCV's Computing Policies.

If you are an instructor, CCV can provide access to JupyterHub for your class or workshop, and Digital Learning and Design (DLD) can assist with integrating computational assignments into curricula. The implementation is supported by Brown OIT; please follow the link below to request an instance for your class. OIT staff will respond to your request to begin the setup process. We ask that requests for JupyterHub be made at least two months in advance of expected course deployment. 

<a href="https://docs.google.com/forms/d/e/1FAIpQLSct9rFCxLhPIezHI-RYRyEuSnvHrPZLMuUSFRTriIyd_3TAfA/viewform?usp=sf_link" class="button is-link">Request a Hub</a> <a href="https://docs.ccv.brown.edu/jupyterhub/" class="button is-link">Documentation</a>


## JupyterHub Vs Other Resources for Teaching

There are other environments that may be great alternatives for your teaching needs. [Google Colaboratory](https://colab.research.google.com/) provides a similar Jupyter-based notebook environment that is free to use, and depending on your needs may require no set up at all. It also provides free access to GPU and TPU programming, which can be great for deep learning courses. Other new and up-coming platforms such as [repl.it](https://repl.it) are also great alternatives for teaching and learning programming. To date, JupyterHub provides few benefits over these platforms. We list here a few of the differentiating features between Google Colab and JupyterHub to help you decide which choice is right for your course:

* Colab supports Python 3.x as the backend.
* JupyterHub can be configured to support [any language](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels) that has jupyter kernel support.
* With JupyterHub, you can pre-define the Docker container (and all the software) that is going to be running on the instances. Having a Docker container per class is a nice way to ensure reproducibility for students who may want to "take their compute environment with them" at the end of the semester.
* Colab comes bundled with most Python scientific software libraries, but you will have to re-install all non-standard libraries _every time_ you connect to an instance.
* Colab runs a notebook interface, JupyterHub open Jupyter Notebooks, markdown files, PDFs, scripts and a terminal window.
* Colab integrates nicely with your Google Drive and supports real-time collaboration
