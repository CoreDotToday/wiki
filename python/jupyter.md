<!-- TITLE: Jupyter -->
<!-- SUBTITLE: A quick summary of Jupyter -->

# Jupyter
```
$ pip install ipykernel
$ jupyter kernelspec list
$ sudo jupyter kernelspec install-self
$ python -m pip install ipykernel
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
`pip install --install-option="--include-path=/usr/local/include/" --install-option="--library-path=/usr/local/lib/" pygraphviz`