<p align="center">
    <img src="https://raw.githubusercontent.com/yWorks/yfiles-jupyter-graphs/main/screenshots/yfiles-jupyter-graphs-logo.svg" alt='yFiles Graphs for Jupyter logo'  width="400px" style='max-width: 400px'>
</p>

[![PyPI version](https://badge.fury.io/py/yfiles-jupyter-graphs.svg)](https://badge.fury.io/py/yfiles-jupyter-graphs)

A graph diagram visualization widget for Jupyter Notebooks and Labs powered by [yFiles for HTML](https://www.yworks.com/yfiles-overview?utm_campaign=yfiles4jupyter&utm_source=github&utm_medium=readme).

Easily visualize graphs from various sources: [Networkx](https://networkx.org/)✅, [igraph](https://igraph.org/python/)✅, [neo4j](https://pypi.org/project/neo4j/)✅, [pygraphviz](https://pygraphviz.github.io/)✅, and any structured Python dictionaries and lists. Many more formats supported indirectly via [Networkx imports](https://networkx.org/documentation/stable/reference/readwrite/index.html#reading-and-writing-graphs)!

![A screenshot showing the yFiles graph widget in a jupyter lab notebook](https://raw.githubusercontent.com/yWorks/yfiles-jupyter-graphs/main/screenshots/yfiles-jupyter-graphs-introduction.png)

## Requirements
- [python](https://www.python.org/) >= 3.6
- [jupyter](https://jupyter.org/install) notebook or lab
- [ipywidgets](https://github.com/jupyter-widgets/ipywidgets) >= 7.6.0, <8

## Installation

If you already have Jupyter installed, just `pip install` the prebuilt extension from the [Python Package Index](https://pypi.org/).

```bash
pip install yfiles_jupyter_graphs
```

If you want to start clean and get a fresh new Jupyter Lab with the widget readily installed and available, you can use [`docker`](https://www.docker.com/), too:

Form a shell, create a docker image that contains all that is required:

```bash
mkdir yfiles-jupyter && cd yfiles-jupyter
echo -e "FROM jupyter/scipy-notebook\nRUN pip install yfiles-jupyter-graphs" > Dockerfile
docker build -t yfiles-jupyter-graphs-on-docker .
```

(the above has been tested successfully with `scipy-notebook:lab-3.4.7` and `yfiles-jupyter-graphs==1.2.1`), but we want to make sure that it will also work with  upcoming versions - file an issue if it doesn't work for you!)

You can then create a fresh new instance of your server from this image like so:

```bash
docker run -it -p 8888:8888 --name yfiles-jupyter yfiles-jupyter-graphs-on-docker
```

## Usage

In a notebook which has the wiget installed in the server, in a Python cell, you can then do this:

```python
"""Execute in jupyter notebook or jupyter lab"""
from yfiles_jupyter_graphs import GraphWidget
# shows empty widget
GraphWidget()
```

You can find the full documentation [here](https://yworks.github.io/yfiles-jupyter-graphs/).

## Features
<table>
    <tr>
        <td><a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/neighborhood.ipynb"><img src="https://raw.githubusercontent.com/yWorks/yfiles-jupyter-graphs/main/screenshots/neighborhood.png" title="See Node Neighborhood" alt="neighborhood sidebar"></a>
        <a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/neighborhood.ipynb">See Node Neighborhood</a></td>
        <td><a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/layouts.ipynb"><img src="https://raw.githubusercontent.com/yWorks/yfiles-jupyter-graphs/main/screenshots/layouts.png" title="Choose Graph Layout" alt="layouts"></a>
        <a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/layouts.ipynb">Choose Graph Layout</a></td>
    </tr>
    <tr>
        <td><a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/sidebar.ipynb"><img src="https://raw.githubusercontent.com/yWorks/yfiles-jupyter-graphs/main/screenshots/data.png" title="Investigate Nodes and Edges Data" alt="data sidebar"></a>
        <a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/sidebar.ipynb">Investigate Nodes or Edges Data</a></td>
        <td><a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/sidebar.ipynb"><img src="https://raw.githubusercontent.com/yWorks/yfiles-jupyter-graphs/main/screenshots/search.png" title="Search for Nodes or Edges" alt="search sidebar"></a>
        <a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/sidebar.ipynb">Search for Nodes or Edges</a></td>
    </tr>
    <tr>
        <td><a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/import_from_networkx.ipynb"><img src="https://raw.githubusercontent.com/yWorks/yfiles-jupyter-graphs/main/screenshots/importer.png" title="Import Graph Data" alt="importer"></a>
        <a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/import_from_networkx.ipynb">Import Graph Data</a></td>
        <td><a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/element_color_mapping.ipynb"><img src="https://raw.githubusercontent.com/yWorks/yfiles-jupyter-graphs/main/screenshots/element_color_mapping.png" title="Make Data Dependent Property Changes" alt="element color mapping"></a>
        <a href="https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/examples/element_color_mapping.ipynb">Make Data Dependent Property Changes</a></td>
    </tr>
</table>

For example code look [here](https://github.com/yWorks/yfiles-jupyter-graphs/tree/master/examples).

## Documentation
You can find the documentation [here](https://yworks.github.io/yfiles-jupyter-graphs/).

## Code of Conduct
This project and everyone participating in it is governed by the [Code of Conduct](https://github.com/yWorks/yfiles-jupyter-graphs/blob/master/CODE_OF_CONDUCT.md).
By participating, you are expected to uphold this code.
Please report unacceptable behavior to [contact@yworks.com](mailto:contact@yworks.com).

## Feedback
This widget is by no means perfect.
If you find something is not working as expected
we are glad to receive an issue report from you.
Please make sure to [search for existing issues](https://github.com/yWorks/yfiles-jupyter-graphs/search?q=is%3Aissue+repo%3AyWorks%2Fyfiles-jupyter-graphs&type=issues) first
and check if the issue is not an unsupported feature or known issue.
If you did not find anything related, report a new issue with necessary information.
Please also provide a clear and descriptive title and stick to the issue templates.
See [issues](https://github.com/yWorks/yfiles-jupyter-graphs/issues).

## Dependencies
- [yFiles for HTML](https://www.yworks.com/yfiles)
- [@ctrl/tinycolor](https://github.com/scttcper/tinycolor)
- [@jupyter-widgets/base](https://github.com/jupyter-widgets/ipywidgets)
- [@mdi/js](https://github.com/Templarian/MaterialDesign-JS)
- [json-viewer-js](https://github.com/renhongl/json-viewer-js)

## License
See [LICENSE](https://github.com/yWorks/yfiles-jupyter-graphs/blob/main/LICENSE.md) file.
