# singularity-jupyter-typescript

A Singularity container of Jupyter notebook for datascience + typescript, 
created by converting an official Docker image 
[jupyter/datascience-notebook](https://hub.docker.com/r/jupyter/datascience-notebook/),
and [yunabe/tslab Jupyter kernel](https://github.com/yunabe/tslab).


## Usage

Build the Singularity image as follows:

```
git clone https://github.com/oogasawa/singularity-jupyter-typescript
cd singularity-jupyter-typescript
sudo singularity build . singularity-jupyter-typescript.sif Singularity
```


Start the server as follows:

```
singularity instance start singularity-jupyter-typescript.sif sing_typescript
```

Enter (attach) the Singularity container:

```
# List the running containers.
singularity instance list

# Attach the container
singularity shell instance://sing_typescript
```

Start the Jupyter notebook (or Jupyter Lab) from within the Singularity prompt.

```
$ singularity shell instance://sing_typescript
Singularity> jupyter lab --port=50000
[I 01:28:50.619 LabApp] JupyterLab extension loaded from /opt/conda/lib/python3.8/site-packages/jupyterlab
[I 01:28:50.619 LabApp] JupyterLab application directory is /opt/conda/share/jupyter/lab
[I 01:28:50.621 LabApp] Serving notebooks from local directory: /home/oogasawa/tmp3/singularity-jupyter-typescript
[I 01:28:50.621 LabApp] The Jupyter Notebook is running at:
[I 01:28:50.621 LabApp] http://mayfly:50000/?token=056ea4ee0e654429927ef2a0696a10100c623fbc7b4a8ee4
[I 01:28:50.621 LabApp]  or http://127.0.0.1:50000/?token=056ea4ee0e654429927ef2a0696a10100c623fbc7b4a8ee4
[I 01:28:50.621 LabApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 01:28:50.624 LabApp]

    To access the notebook, open this file in a browser:
	    file:///home/oogasawa/.local/share/jupyter/runtime/nbserver-25-open.html
	Or copy and paste one of these URLs:
		http://mayfly:50000/?token=056ea4ee0e654429927ef2a0696a10100c623fbc7b4a8ee4
	  or http://127.0.0.1:50000/?token=056ea4ee0e654429927ef2a0696a10100c623fbc7b4a8ee4					 
```

Then you can access the Jupyter software http://localhost:50000/ .

Stop the server (and return to the bash prompt) by Ctrl-C, and stop the container as follows:

```
singularity instance stop sing_typescript
```


