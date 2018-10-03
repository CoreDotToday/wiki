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
import findspark
findspark.init()
import pyspark
```

```
$ vi ~/.bashrc
export SPARK_HOME=/opt/spark/spark-2.3.2-bin-hadoop2.7
export PATH=$SPARK_HOME/bin:$PATH
export PYSPARK_DRIVER_PYTHON=jupyter
export PYSPARK_DRIVER_PYTHON_OPTS=’notebook’
```

