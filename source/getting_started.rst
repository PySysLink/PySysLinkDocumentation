PySysLink: Getting Started
==========================

Welcome to the **PySysLink** documentation!

This guide walks you through installing and running PySysLink with basic C++ block support.

---

Installation (Quickstart with Docker)
-------------------------------------

To test PySysLink inside a clean containerized environment, use Docker with Ubuntu 22.04:

.. code-block:: bash

    docker run -it --rm ubuntu:22.04 /bin/bash

Then run the following commands to install Python, PySysLink, and required block plugins:

**1. Install base system packages and Python:**

.. code-block:: bash

    apt update
    apt install -y python3 python3-pip wget git
    pip install pysyslink_base

**2. Prepare plugin directory layout:**

.. code-block:: bash

    cd /usr/local/lib/
    mkdir -p pysyslink_plugins/block_type_supports/basic_cpp_support_0_1_0
    mkdir -p pysyslink_plugins/basic_blocks_basic_cpp_0_1_0

**3. Download plugin artifacts:**

**Basic C++ Block Type Support:**

.. code-block:: bash

    cd /usr/local/lib/pysyslink_plugins/block_type_supports/basic_cpp_support_0_1_0

    wget https://github.com/PySysLink/BlockTypeSupportsBasicCpp/releases/download/v0.1.0/basic_cpp_support.0_1_0.pslkbtsp.yaml
    wget https://github.com/PySysLink/BlockTypeSupportsBasicCpp/releases/download/v0.1.0/libBlockTypeSupportsBasicCppSupport-0.1.0.so
    wget https://github.com/PySysLink/BlockTypeSupportsBasicCpp/releases/download/v0.1.0/libBlockTypeSupportsBasicCppSupport-0.1.0.so.0.1.0

**Basic C++ Block Library:**

.. code-block:: bash

    cd /usr/local/lib/pysyslink_plugins/basic_blocks_basic_cpp_0_1_0

    wget https://github.com/PySysLink/BlockLibrariesBasicBlocksBasicCpp/releases/download/v0.1.0/basic_blocks_basic_cpp.0_1_0.pslkp.yaml
    wget https://github.com/PySysLink/BlockLibrariesBasicBlocksBasicCpp/releases/download/v0.1.0/libBlockLibrariesBasicBlocksBasicCpp-0.1.0.so
    wget https://github.com/PySysLink/BlockLibrariesBasicBlocksBasicCpp/releases/download/v0.1.0/libBlockLibrariesBasicBlocksBasicCpp-0.1.0.so.0.1.0

---

Example Execution
-----------------

Clone the Python bindings and run the example script:

.. code-block:: bash

    cd /home

    git clone https://github.com/PySysLink/PySysLinkBasePythonBindings.git
    cd PySysLinkBasePythonBindings/examples/
    python3 test_continuous.py

---

Troubleshooting: GLIBCXX Compatibility Errors
---------------------------------------------

If you encounter an error like:

::

    /lib/x86_64-linux-gnu/libstdc++.so.6: version `GLIBCXX_3.4.32' not found

This means the `.so` plugin was compiled with a newer GCC/libstdc++ than your system provides.

**What Introduced `GLIBCXX_3.4.30` and `GLIBCXX_3.4.32`?**

- ``GLIBCXX_3.4.30``: Introduced in **GCC 12** (April 2022)
- ``GLIBCXX_3.4.32``: Introduced in **GCC 13** (April 2023)

**Solutions:**

1. **Upgrade libstdc++:**

   .. code-block:: bash

       sudo add-apt-repository ppa:ubuntu-toolchain-r/test
       sudo apt update
       sudo apt install libstdc++6

2. **Use Ubuntu 22.04 or newer**, where GCC 11 or 12 is the default.

3. **Compile plugins with gcc-9 or gcc-10** for better backward compatibility.

---

Roadmap
---------------------------------------------

Improve editor visuals:

* Block rotation
* Fix triangle blocks
* Arrows on links
* Proper port positioning
* Multi-output links
* Align grid
* Copy paste

High level systems:

* Subsystems
* Subsystem references

Installation:

* Installation utility, kind of a simple package manager for plugins

PySysLinkBase:

* Profile performance, improve
* FMI export (check version)

BlockTypeSupports:

* FMI support (check version)
* Python blocks
* Check best way to integrate hardware, sockets...

Others:

* Code generation from low level system


---

**Happy simulating!** 🚀
