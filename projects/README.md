# Projects

You have the choice of 4 projects.

Navigate to the directory of the chosen project.

For ease of development, all the projects have docker files
that you can use to build and run a fully functioning container.
Each directory has a readme which explains in further detail how each
project should be tackled.

For a kick start, we have provided
you with some sample models for each project. The dockerfiles already
have the necessary dependencies to run each of the sample models. It
is highly encouraged to add more models to further develop the pipeline,
but one should keep in mind to take care to add any necessary dependenices
to the dockerfile.

The datasets for each usecase are mentioned in the readme for each project
and if there are extra instructions on how to use them, they are mentioned
in the readme of each file.

We also provide you with a sample assertion for each usecase given in the
readme file. You are tasked with implementing and thinking of more assertions
for each usecase.

## Using Docker

For all those who are unfamiliar with docker, this is a short tutorial to run the
dockerfiles and create containers. For ease of developent, all the containers will
install jupyter which allows you to use jupyter notebooks to test and run code.

To build a container, navigate to your chosen project directory.
E.g. `cd text`

Then you can run the following command to build the docker image:
`docker build -t your_image_name . `

You can replace `your_image_name` with whatever name you want.

Once the build is complemented, you now have to run the container. We give you
two ways to run the container here:
1. Jupyter Labs

    Run the following command `docker run -p 8888:8888 your_image_name`
    This will start up a container from your build image and it will epose the 8888
    port on your system. Following this you should see the following output:
    ```
    [I 2025-08-19 20:16:02.971 ServerApp] jupyter_lsp | extension was successfully linked.
    [I 2025-08-19 20:16:02.974 ServerApp] jupyter_server_terminals | extension was successfully linked.
    [I 2025-08-19 20:16:02.977 ServerApp] jupyterlab | extension was successfully linked.
    [I 2025-08-19 20:16:02.980 ServerApp] notebook | extension was successfully linked.
    [I 2025-08-19 20:16:02.983 ServerApp] Writing Jupyter server cookie secret to /root/.local/share/jupyter/runtime/jupyter_cookie_secret
    [I 2025-08-19 20:16:03.440 ServerApp] notebook_shim | extension was successfully linked.
    [I 2025-08-19 20:16:03.473 ServerApp] notebook_shim | extension was successfully loaded.
    [I 2025-08-19 20:16:03.475 ServerApp] jupyter_lsp | extension was successfully loaded.
    [I 2025-08-19 20:16:03.476 ServerApp] jupyter_server_terminals | extension was successfully loaded.
    [I 2025-08-19 20:16:03.485 LabApp] JupyterLab extension loaded from /usr/local/lib/python3.10/dist-packages/jupyterlab
    [I 2025-08-19 20:16:03.485 LabApp] JupyterLab application directory is /usr/local/share/jupyter/lab
    [I 2025-08-19 20:16:03.486 LabApp] Extension Manager is 'pypi'.
    [I 2025-08-19 20:16:03.555 ServerApp] jupyterlab | extension was successfully loaded.
    [I 2025-08-19 20:16:03.559 ServerApp] notebook | extension was successfully loaded.
    [I 2025-08-19 20:16:03.560 ServerApp] Serving notebooks from local directory: /
    [I 2025-08-19 20:16:03.560 ServerApp] Jupyter Server 2.16.0 is running at:
    [I 2025-08-19 20:16:03.560 ServerApp] http://48bff4dd8c67:8888/tree?token=`TOKENNUMBER`
    [I 2025-08-19 20:16:03.560 ServerApp]     http://127.0.0.1:8888/tree?token=`TOKENNUMBER`
    [I 2025-08-19 20:16:03.560 ServerApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
    [C 2025-08-19 20:16:03.564 ServerApp] 
        
        To access the server, open this file in a browser:
            file:///root/.local/share/jupyter/runtime/jpserver-1-open.html
        Or copy and paste one of these URLs:
            http://48bff4dd8c67:8888/tree?token=`TOKENNUMBER`
            http://127.0.0.1:8888/tree?token=`TOKENNUMBER`
    [I 2025-08-19 20:16:03.580 ServerApp] Skipped non-installed server(s): bash-language-server, dockerfile-language-server-nodejs, javascript-typescript-langserver, jedi-language-server, julia-language-server, pyright, python-language-server, python-lsp-server, r-languageserver, sql-language-server, texlab, typescript-language-server, unified-language-server, vscode-css-languageserver-bin, vscode-html-languageserver-bin, vscode-json-languageserver-bin, yaml-language-server
    ```
    Following this you can either follow the prompt on your given code IDE or copy paste
    the localhost url, i.e. the one containing `127.0.0.2:8888` into your chosen browser.
    If you follow the prompt given by your IDE, and you are prompted for a token, copy paste
    the `TOKENNUMBER` into the box. The `TOKENNUMBER` can be found in the places that I have
    highlighted in the output above.

2. Bash

    You can also run the container without needing to go to jupyter labs. Here just run the
    command: `docker run -it your_image_name bash`.
    This will redirect you to the bash shell of the container where you can run any python files
    that you need to test. Note that you will not be able to open jupyter notebooks from the 
    bash shell unless you use a IDE specific tool to attach your IDE to your running container.
    We shall not go into detail about that, but the option is available to those who know how or
    are willing to learn it.


As a reminder, it would be good to read up on docker containers and how to maintain them
during your process of development here: https://www.devopsroles.com/managing-docker-containers/
