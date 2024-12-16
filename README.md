# Using this repo

The purpose of this repository is to provide an example of using a Dockerfile to create a Jupyter Notebook environment capable of running Python with PySpark, Pandas, and packages specified in a `requirements.txt` file.

# Setting up things

1. Clone this repository.
2. Add your `requirements.txt` file or update the existing one with your desired dependencies.

The folder structure should look like this:
```
github_project_root
├── LICENSE
├── README.md
├── dockerfiles
│   └── Dockerfile_jupyter_python_pyspark
├── notebooks
│   └── testing pyspark.ipynb
└── requirements.txt
```

# How to run the code:

1. Open a terminal.
2. Navigate to the root of this repository.
3. Run the following commands:


```bash
# Build the Docker image
docker build -f dockerfiles/Dockerfile_jupyter_python_pyspark -t jupyter-pyspark .

# Run the Docker container
docker run -p 8888:8888 -v $(pwd):/notebooks -it jupyter-pyspark

# Activate the virtual environment
source /env/bin/activate

# Start Jupyter Notebook
jupyter notebook --ip=0.0.0.0 --port=8888 --no-browser --allow-root
```

4. Open the test notebook located at: `notebooks/testing_pyspark.ipynb`.
