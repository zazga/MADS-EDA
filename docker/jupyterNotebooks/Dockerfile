FROM jupyter/base-notebook:latest

# Install uv binary
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

# Set working directory inside the container
WORKDIR /home/jovyan/work

# Expose Jupyter port
EXPOSE 8888

# Start Jupyter when the container runs (no token for easy access)
#CMD ["start-notebook.sh", "--NotebookApp.token=''", "--NotebookApp.password=''"]

# Default to JupyterLab
ENV JUPYTER_ENABLE_LAB=yes
ENV PATH="/home/jovyan/work/uv_files/.venv/bin:$PATH"
