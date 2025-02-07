.. _host-setup:

Build Environment
---------------------

|SPN| build is supported on both Windows and Linux environments


.. _running-on-linux:

Building on Linux
^^^^^^^^^^^^^^^^^^^^

Supported environment: **Ubuntu Linux 18.04 LTS**

Install the following software:

* GCC 7.3 or above
* Python 3.6 or above
* NASM 2.12.02 or above
* IASL 20190509
* OpenSSL
* Git


Build Tools Download - Ubuntu
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install required packages on Ubuntu::

  $ sudo apt-get install -y build-essential iasl python uuid-dev nasm openssl gcc-multilib qemu git


Build using Dockers (Optional)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can also consider Dockers containers to build |SPN|. See :ref:`misc_setup_docker` for more details.



.. _running-on-windows:

Building on Windows
^^^^^^^^^^^^^^^^^^^^^

Supported environment: **Microsoft Visual Studio 2015 or Microsoft Visual Studio 2017 Community**

Install the **exact** versions (if specified) of the following tools to the designated directories:

* Python 3.6 - **C:\\Python36**
* NASM 2.12.02 - **C:\\Nasm**
* IASL 20190509 - **C:\\ASL**
* OpenSSL - **C:\\openssl**
* Git (ex. GitBash)

.. _sbl-keys:

|SPN| Keys Generation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Generate |SPN| keys and this is pre-requiste before |SPN| build:

Generate SBLKeys::

  python $(SBL_ROOT)\BootloaderCorePkg\Tools\GenerateKeys.py -k $SBL_KEY_DIR

Set of private and public keys would be generated for specified key sizes:

.. note:: Replace OS Test Public keys generated OS1_TestKey_Pub_RSA2048.pem/OS1_TestKey_Pub_RSA3072.pem keys with respective public keys used in signing OS Image


Build Tools Download - Windows
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Python 3.6.x 64 bit version.

|https://www.python.org/downloads/windows/|

.. |https://www.python.org/downloads/windows/| raw:: html

   <a href="https://www.python.org/downloads/windows/" target="_blank">https://www.python.org/downloads/windows/</a>

.. note::
  Add Python to the PATH

  Python version 3.6.6 is the tested version.



IASL 20190509-64

|https://acpica.org/sites/acpica/files/iasl-win-20190509.zip|

.. |https://acpica.org/sites/acpica/files/iasl-win-20190509.zip| raw:: html

   <a href="https://acpica.org/sites/acpica/files/iasl-win-20190509.zip" target="_blank">https://acpica.org/sites/acpica/files/iasl-win-20190509.zip</a>

unzip then copy files to C:\\asl

**Require:** Install to C:\\Asl


Nasm 2.12.02

|https://www.nasm.us/pub/nasm/releasebuilds/2.12.02/|

.. |https://www.nasm.us/pub/nasm/releasebuilds/2.12.02/| raw:: html

   <a href="https://www.nasm.us/pub/nasm/releasebuilds/2.12.02/" target="_blank">https://www.nasm.us/pub/nasm/releasebuilds/2.12.02/</a>

**Require:** Install to C:\\Nasm


Openssl (latest)

Download latest win64 version from |https://wiki.openssl.org/index.php/Binaries|)

.. |https://wiki.openssl.org/index.php/Binaries| raw:: html

   <a href="https://wiki.openssl.org/index.php/Binaries" target="_blank">https://wiki.openssl.org/index.php/Binaries</a>


**Require:** Install to C:\\Openssl

.. note::
  Set environment variable OPENSSL_PATH to openssl directory where openssl.exe is present.
  For example: set OPENSSL_PATH=C:\\Openssl\\bin


Git on Windows

Install Git or add its executable path in your PATH environment if already exists.

Here is GitBash as an example.

Download GitBash from |https://git-scm.com|

.. |https://git-scm.com| raw:: html

   <a href="https://git-scm.com" target="_blank">https://git-scm.com</a>

Below are **RECOMMENDED** options. For others, it's okay to use default selected option.

Make sure **"Git LFS (Large File Support)"** is selected.

.. image:: /images/gitbash_components.png
   :alt: Make sure "Git LFS (Large File Support)" is selected

Make sure **"Git from the command line..."** is selected.

.. image:: /images/gitbash_path_env.png
   :alt: Make sure "Git from the command line..." is selected

Make sure **"Checkout as-is, commit as-is"** is selected.

.. image:: /images/gitbash_line_ending.png
   :alt: Make sure "Checkout as-is, commit as-is" is selected
