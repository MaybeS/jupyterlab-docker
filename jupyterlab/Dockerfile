FROM python:3.8

# Install Jupyter
RUN pip install jupyter ipywidgets nodejs
RUN jupyter nbextension enable --py widgetsnbextension

# Install JupyterLab
RUN pip install jupyterlab && jupyter serverextension enable --py jupyterlab

RUN mkdir -p /opt/app/data
RUN mkdir -p /root/.jupyter
COPY etc/ /opt/app/etc/
COPY scripts.ipynb /opt/app/data/
COPY jupyter_notebook_config.py /root/.jupyter/

# Expose Jupyter port & cmd
EXPOSE 8888
CMD jupyter lab --ip=* --notebook-dir=/opt/app/data --allow-root
