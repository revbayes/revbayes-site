---
layout: home
title: Graphical User Interfaces
subtitle: Use RevBayes with a Graphical Interface
permalink: /gui-setup
code_layout: bash
---

{% section Graphical User Interfaces %}

There are two main graphical user interfaces (GUIs) that can be used with RevBayes. Below, installation instructions are listed for both.

{% section Jupyter Notebook %}

First, download and install Python 3 and the Jupyter Notebook. Installation instructions are available from the Jupyter Development team [here](https://jupyter.readthedocs.io/en/latest/install.html).


Now, use the [Downloads](https://revbayes.github.io/download) page to find RevBayes compilation instructions for your operating system. When building RevBayes, substitute

```
./build.sh -jupyter true
```

for the normal build step. This will generate an `rb-jupyter` executeable. Add this executeable to your system path.

Finally, clone the RevBayes Jupyter Kernel.

```
git clone https://github.com/revbayes/revbayes_kernel.git
```

Change directories into the `revbayes_kernel` directory and use

```
sudo python3 setup.py install
python3 -m revbayes_kernel.install
pip3 install metakernel
```
to deploy the kernel. Now, when launching a Jupyter Notebook, RevBayes should be an available language when starting a notebook.

Examples of RevNotebooks can be found in the RevNotebook [repository](https://github.com/revbayes/RevNotebooks).


{% section RStudio %}

Compile or download RevBayes as appropriate for your system above. Add RevBayes to your system path.

Download [R](https://cran.rstudio.com/) and [RStudio](https://rstudio.com/products/rstudio/download/). Once these are downloaded, start RStudio. Install the `devtools` package like so:

```
install.packages("devtools")
```

Use `devtools` to install RevKnitr:

```
devtools::install_github("revbayes/RevKnitr")
```

Once installation is complete, restart RStudio. `rb` should now be available as an RMarkdown language. For more information see.

If you are on Mac, you may need to start your RStudio session from the terminal with

```
open -a RStudio
```

in order for RStudio to find the RevBayes executeable.
