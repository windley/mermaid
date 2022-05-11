# Tutorials

This is  list of publicly available Tutorials for using Mermaid.JS, forked from the [Mermaid Github repo](https://mermaid-js.github.io/). This is intended as a basic introduction for the use of the Live Editor for generating diagrams, and deploying Mermaid.JS through HTML. I (@windley) have added commentary as quotes based on my exploration. 

**Note that these tutorials might display an older interface, but the usage of the live-editor will largely be the same.**

For most purposes, you can use the [Live Editor](https://mermaid-js.github.io/mermaid-live-editor), to quickly and easily render a diagram.


## Live-Editor Tutorials
The definitions that can be generated the Live-Editor are also backwards-compatible as of version 8.7.0.
> I recommend you play with Mermaid using the Live-Editor while reading the [Mermaid docs](https://mermaid-js.github.io/mermaid/#/). The LiveEditor will show you the diagram as you type. You can copy the Mermaid text to your Markdown doc later if you need to. 

[Chris Chinchilla: Hands on - Text-based diagrams with Mermaid](https://www.youtube.com/watch?v=4_LdV1cs2sA)

> Chris explores the Mermaid interface in real time. He's literally figuring it out on camera, which I guess is his schtick. If you want a guided tour of the [Mermaid Docs](https://mermaid-js.github.io/mermaid/#/) and learn by watching other people try things, this is a useful tutorial. 

[GitLab Unfiltered: How to Create Mermaid Diagrams](https://www.youtube.com/watch?v=SQ9QmuTHuSI&t=438s)

> Giuliana Lucchesi from the GitLab shows how to use Mermaid to create diagrams in Gitlab. Gitlab includes support for Mermaid. Giulianna walks through her design process for flowcharts, graphs, diagrams, etc. She started in LucidChart, but moved to Mermaid because it can be iterated, versioned, etc. [Mermaid can be integrated](https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/) in Github Markdown files as well. I found this useful for understanding posibilities. 

[GitLab Unfiltered: Emilie adds a mermaid diagram to the handbook](https://www.youtube.com/watch?v=5RQqht3NNSE)

> Emile solves a specific problem as a Mermaid newbie. Again, she's using the Live-Editor and looking at docs to get the results she wants. The pace is a little slow, but the concepts are clear. An interesting feature of this tutorial is that the diagram she creates is not hierarchical, but cyclical. This is realtively short, so it might be a good place to start. 

[World of Zero: I Learn How To Build Flowcharts and Signal Diagram's in Mermaid.JS](https://www.youtube.com/watch?v=7_2IroEs6Is&t=207s)

> Another newbie exploration video. I think this is a good, short (~20 min) introduction to flowcharts and sequence diagrams. 

[Eddie Jaoude: Can you code your diagrams?](https://www.youtube.com/watch?v=9HZzKkAqrX8?t=43)

> Short (~6min) introduction to using Mermaid for sequence diagrams. 


## Mermaid with HTML
Examples are provided in [Getting Started](n00b-gettingStarted.md)

**CodePen Examples:**

https://codepen.io/CarlBoneri/pen/BQwZzq

https://codepen.io/tdkn/pen/vZxQzd

https://codepen.io/janzeteachesit/pen/OWWZKN


## Mermaid with Text Area

https://codepen.io/Ryuno-Ki/pen/LNxwgR

## Mermaid in open source docs

[K8s.io Diagram Guide](https://kubernetes.io/docs/contribute/style/diagram-guide/)

[K8s.dev blog: Improve your documentation with Mermaid.js diagrams](https://www.kubernetes.dev/blog/2021/12/01/improve-your-documentation-with-mermaid.js-diagrams/)


## Jupyter Integration with mermaid-js

Here's an example of Python integration with mermaid-js which uses the mermaid.ink service, that displays the graph in a Jupyter notebook.

```python
import base64
from IPython.display import Image, display
import matplotlib.pyplot as plt

def mm(graph):
  graphbytes = graph.encode("ascii")
  base64_bytes = base64.b64encode(graphbytes)
  base64_string = base64_bytes.decode("ascii")
  display(Image(url="https://mermaid.ink/img/" + base64_string))

mm("""
graph LR;
    A--> B & C & D;
    B--> A & E;
    C--> A & E;
    D--> A & E;
    E--> B & C & D;
""")
```

**Output**

![Example graph of the Python integration](img/python-mermaid-integration.png)
