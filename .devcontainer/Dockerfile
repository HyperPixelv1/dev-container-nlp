FROM mcr.microsoft.com/devcontainers/anaconda:1-3

WORKDIR /workspace

# Copy environment.yml (if found) to a temp location so we update the environment. Also
# copy "noop.txt" so the COPY instruction does not fail if no environment.yml exists.
COPY environment.yml* /tmp/conda-tmp/

RUN apt-get update

RUN apt-get update && apt-get -y install git procps build-essential curl swig
RUN conda init bash
RUN conda update -n base conda -y
RUN conda env create --file /tmp/conda-tmp/environment.yml
RUN conda install ipython_genutils
RUN conda install ipykernel
RUN ipython kernel install --user --name=env1


