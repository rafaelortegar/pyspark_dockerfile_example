# Using this repo

The idea of this repository is to give an example of using a dockerfile to create a jupyter notebook that will be able to use pyhon with pyspark, pandas and a set from a requirements.txt file.

# Setting up things

1. clone this repo.
2. add your requirements.txt file or update the existing one with your requirements.

The folders should have this structure:

github_project_root
├── LICENSE
├── README.md
├── dockerfiles
│   └── Dockerfile_jupyter_python_pyspark
├── notebooks
│   └── testing pyspark.ipynb
└── requirements.txt

# How to run the code:

1. Open a terminal
2. Go to the root of this repository
3. Run the following commands:


```bash
docker build -f dockerfiles/Dockerfile_jupyter_python_pyspark -t jupyter-pyspark .
```

```bash
docker run -p 8888:8888 -v $(pwd):/notebooks -it jupyter-pyspark
```

```bash
source /env/bin/activate
jupyter notebook --ip=0.0.0.0 --port=8888 --no-browser --allow-root
```

now you can run the test notebook on:
notebooks/testing pyspark.ipynb
