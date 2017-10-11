## Spark in Windows: ##

Below are the steps to run spark in windows.
<br>
#### Required Downloads: #####

* Download Spark distribution you want directly from [Apache](https://spark.apache.org/downloads.html "apache page").
2. Extract the `tar.gz` or `.tgz` files using `7zip`.
3. Download Hadoop binaries from the [here](http://hadoop.apache.org/releases.html "Hadoop") the version you want  extract it.
4. In order to run Hadoop on windows there are two special files `winutils.exe` and `hadoop.dll` needed. Download these files [here](https://github.com/steveloughran/winutils "hadoop utils") and place in hadoop bin folder that extracted from the above step. 
<br>
#### Required Configurations: ###

After downloading all the above, there are few configurations changes
<br>
#### Hadoop configurations: ####

Couple of parameters need to be updated in `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd`

* Set `JAVA_HOME` as per the version of java. Hadoop does not like spaces in `JAVA_HOME`. <br>

	** `set JAVA_HOME=C:\PROGRA~1\Java\jdk1.8.0`**
		
* Set `HADOOP_CLASSPATH` as `%HADOOP_HOME%\share\hadoop\tools\lib\*` to access the required jar files to hadoop commands. <br>
	
	**`set HADOOP_CLASSPATH=%HADOOP_HOME%\share\hadoop\tools\lib\*`**

<br>	
Now you can test your hadoop by running simple hadoop commands like **`hadoop fs -ls /tmp`**
<br>
<br>
#### Spark configurations: ####

* Set `HADOOP_HOME` and `SPARK_HOME` which should point to the hadoop and spark path that we extracted in the above steps
	    
		set HADOOP_HOME=\hadoop-3.0.0-alpha4	
		set SPARK_HOME=\spark-2.1.0-bin-without-hadoop
		set PYTHON_HOME=\python
		
* Set `SPARK_DIST_CLASSPATH` = run `"bin\hadoop classpath"`.

 Then copy the output of that and set this. It should look like below
```sh 
"E:\XXXXXX\hadoop-3.0.0-alpha4\etc\hadoop;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\common;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\common\lib\*;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\common\*;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\hdfs;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\hdfs\lib\*;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\hdfs\*;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\yarn;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\yarn\lib\*;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\yarn\*;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\mapreduce\*;;E:\XXXXXX\hadoop-3.0.0-alpha4\share\hadoop\tools\lib\*;"
```
* Set python home in the environment variables and run **python**
* Run Spark using **`\bin\spark-shell`** or **`\bin\pyspark`**

Now you can play with spark in windows.   
<br>