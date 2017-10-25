### Install Jupyter using
 [http://jupyter.readthedocs.io/en/latest/install.html]

## Installing PySpark locally

Download spark from [Spark Download](https://spark.apache.org/downloads.html)

Install [Java SDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html)

For **Mac** users using [Homebrew](http://brew.sh/):

```
$ brew install apache-spark
```
<br>


For **Linux** users

Add the following in `bashrc`
```
export SPARK_HOME=$PATH/spark-2.2.0-bin-hadoop2.7
export PATH=$SPARK_HOME/bin:$PATH

export PYSPARK_DRIVER_PYTHON=jupyter
export PYSPARK_DRIVER_PYTHON_OPTS='notebook'
```

For Windows users please refer [Spark On Windows](https://github.com/Yotabites/meetup/blob/master/Spark/Spark_on_Windows_ReadMe.md)


For Windows users

```
PYSPARK_PYTHON = your_path_to_anaconda\Anaconda3\envs\pyspark\python.exe
### Add below two Lines to run pyspark in jupyter
PYSPARK_DRIVER_PYTHON = your_path_to_anaconda\Anaconda3\envs\pyspark\Scripts\jupyter.exe
PYSPARK_DRIVER_PYTHON_OPTS = notebook
```


Description of Files: 

[Meetup_Pyspark_Github.ipynb]() is the pyspark Notebook
[meetup.csv]() is the meetup CSV file.