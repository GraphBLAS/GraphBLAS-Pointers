## pygraphblas installation guide

1. Install the required versions of SuiteSparse:GraphBLAS and LAGraph.

    ```bash
    export JOBS=$(nproc)
    curl -s -L  http://faculty.cse.tamu.edu/davis/GraphBLAS/GraphBLAS-3.1.1.tar.gz | tar -xz && \
        cd GraphBLAS-3.1.1 && \
        make library \
        && make install
    git clone --branch 22July2019 https://github.com/GraphBLAS/LAGraph.git && \
        cd LAGraph && \
        make library \
        make install
    ```

1. Install pip.

    ```bash
    sudo apt install python3-pip
    ```

1. Install Python packages.

    ```bash
    pip3 install setuptools pytest pytest-cov ipdb RISE graphviz numba contextvars install colorama
    ```

1. Install pygraphblas:

    ```bash
    python3 setup.py install --user
    ```
