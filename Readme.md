# Spojit&#344; - Intelligently link development artifacts

The **spojitr** (spojit &#345;&#237;zen&#237;) tool and workflow engine assists in creating trace links between development artifacts stored issue tracking systems (ITS) and version control systems (VCS).
The current implementation specifically targets the combination of _Git_ as VCS and _Atlassian Jira_ as ITS, but the underlying [spojit](https://github.com/michaelrath-work/spojit) library is independent of particular implementations.

## Quick Start

We created an [interactive demonstration](demo.asciidoc) within a docker container to get a first impression about **spojitr** and its capabilities.
Further, you can watch an introduction video on youtube **TODO LINK**.

## Local installation

### Requirements

**Spojitr** depends on the following 3rd party tools and libraries:

* git
* Java Runtime environment (JRE) >= 8.0
* python >= 3.6
* [spojit](https://github.com/michaelrath-work/spojit)
* [Weka](https://www.cs.waikato.ac.nz/ml/weka/) >= 3.8
* [Weka run helper](https://github.com/michaelrath-work/weka-run-helper)

[`requirements.txt`](requirements.txt) contains the list of required `python packages` that are available via `pip` and can be installed using `pip3 install -r requirements.txt`.

### Installation

1. Clone the **spojitr** repository and copy th folder `spojitr_install` folder to your desired installation location
2. Install `spojit`

    ```bash
    git clone https://github.com/michaelrath-work/spojit.git
    cd spojit
    python3 setup.py bdist_wheel
    cp -v dist/spojit-*.whl /data/spojitr_install/3rd
    pip3 install /data/spojitr_install/3rd/spojit-*.whl
    ```

3. Install `weka run helper`

    ```bash
    git clone https://github.com/michaelrath-work/weka-run-helper.git
    ```

    Copy the `run_weka.py` file to the your `spojitr_install/3rd` folder (see step 1)

4. Copy the `weka.jar` file of the weka installation to your `spojitr_install/3rd` folder (see step 1)

5. Install additional NLTK data files from within a python shell

    ```python
    >>> import nltk
    >>> nltk.download("stopwords")
    >>> nltk.download("word_tokenize")
    >>> nltk.download("punkt")
    ```

6. Run `install.sh` within your `spojitr_install` folder (see step 1) to export the `SPOJITRPATH` variable and register the `spojitr` tools in your shell (bash) environment

## Command line usage

In a terminal, type `spojitr -h` to get a list of the available commands and options.

The material presented in [quick start](#Quick-Start), especially the [interactive demonstration](demo.asciidoc) and the video shows how to use **spojitr**.
