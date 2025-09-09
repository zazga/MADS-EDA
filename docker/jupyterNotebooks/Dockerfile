FROM jupyter/base-notebook:latest

# Set working directory inside the container
WORKDIR /home/jovyan/work

# Copy requirements file into the image
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose Jupyter port
EXPOSE 8888

# Start Jupyter when the container runs (no token for easy access)
CMD ["start-notebook.sh", "--NotebookApp.token=''", "--NotebookApp.password=''"]

