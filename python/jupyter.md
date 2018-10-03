<!-- TITLE: Jupyter -->
<!-- SUBTITLE: A quick summary of Jupyter -->

# Jupyter
```
$ pip install -U jupyter
```

# ipykernel
```
$ pip install ipykernel
$ jupyter kernelspec list
$ sudo jupyter kernelspec install-self
$ python -m pip install ipykernel
```

### 가상환경 추가
노트북에서 보이는 환경 선택을 추가할 수 있음.
```
python -m ipykernel install --user --name [virtualEnv] --display-name "[displayKenrelName]"
```

##### kernel.json (Default)
```
{
 "argv": [
  "/home/khkim/anaconda3/bin/python",
  "-m",
  "ipykernel_launcher",
  "-f",
  "{connection_file}"
 ],
 "display_name": "PySpark",
 "language": "python"
}
```

##### kernel.json (PySpark)
```
{
 "display_name": ${KERNEL_NAME},
 "language": "python",
 "argv”: [ ${PYSPARK_DRIVER_PYTHON}, "-m", "ipykernel", "-f", "{connection_file}" ],
 "env": {
    "SPARK_HOME": ${SPARK_HOME},
    # sets the search path for importing python modules
    "PYTHONPATH": ${SPARK_HOME}/python/:${SPARK_HOME}/python/lib/py4j-0.10.4-src.zip,
    "PYSPARK_DRIVER_PYTHON": ${PYSPARK_DRIVER_PYTHON},
    "PYSPARK_PYTHON": ${PYSPARK_PYTHON},
    "PYSPARK_SUBMIT_ARGS": ${PYSPARK_SUBMIT_ARGS},
    # specifying the location to a python script, that will be run by python
    # before starting the python interactive mode (interpreter)
    "PYTHONSTARTUP": ${SPARK_HOME}/python/pyspark/shell.py
 }
}
```
https://anchormen.nl/blog/big-data-services/pyspark-jupyter-kernels/

# Matplotlib
## Font List
```
import matplotlib.font_manager
matplotlib.font_manager.findSystemFonts(fontpaths=None, fontext='ttf')
```

> http://wiki.core.today/linux/basic#font-installation

# Graphviz
## Installation
### Mac
```
brew install graphviz
pip install --install-option="--include-path=/usr/local/include/" --install-option="--library-path=/usr/local/lib/" pygraphviz
```

# PySpark
`pip install findspark`를 하고 import 해서 사용할 것.


```
$ vi ~/.bashrc
export SPARK_HOME=/opt/spark/spark-2.3.2-bin-hadoop2.7
export PATH=$SPARK_HOME/bin:$PATH
export PYSPARK_DRIVER_PYTHON=jupyter
export PYSPARK_DRIVER_PYTHON_OPTS=’notebook’
```

##### Example in Jupyter Notebook
```
import findspark
findspark.init()
import pyspark
```