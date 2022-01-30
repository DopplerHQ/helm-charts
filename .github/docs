# helm-charts
diff --git a/README.rst b/README.rst
index 84aaf73..c7c4045 100644
--- a/README.rst
+++ b/README.rst
@@ -4,7 +4,9 @@ Briefcase Linux AppImage Template
 A `Cookiecutter <https://github.com/cookiecutter/cookiecutter/>`__ template for
 building Python apps that will run under Linux, packaged as an AppImage.
 
-**This is the development version of the repository. It contains a template for Python 3.8**.
+**Python 3.5 has reached End Of Life. This repository branch is no longer maintained.**
+
+**This repository branch contains a template for Python 3.5**.
 Other Python versions are available by cloning other branches of repository.
 
 Using this template
@@ -24,7 +26,7 @@ However, if you *do* want use this template directly...
 
 2. Run ``cookiecutter`` on the template::
 
-    $ cookiecutter https://github.com/beeware/briefcase-linux-appimage-template --checkout 3.8
+    $ cookiecutter https://github.com/beeware/briefcase-linux-appimage-template --checkout 3.5
 
    This will ask you for a number of details of your application, including the
    `name` of your application (which should be a valid PyPI identifier), and
@@ -37,7 +39,7 @@ However, if you *do* want use this template directly...
    template. This will give you a self-contained Python install. If installed
    correctly, there should be a ``My Project/My
    Project.AppDir/usr/bin/python3`` binary, a ``My Project/My
-   Project.AppDir/usr/lib/python3.8`` directory, as well as some other
+   Project.AppDir/usr/lib/python3.5`` directory, as well as some other
    Python-related files.
 
    Alternatively, you can download the `Python-Linux-support`_ project, and
@@ -70,7 +72,7 @@ looks something like::
                     python3
                     ...
                 lib/
-                    python3.8/
+                    python3.5/
                     ...
                 share/
                     ...
@@ -109,6 +111,6 @@ directory on a desktop Python install.
 .. _cookiecutter: https://github.com/cookiecutter/cookiecutter
 .. _linuxdeploy: https://github.com/linuxdeploy/linuxdeploy
 .. _linuxdeploy AppImage: https://github.com/linuxdeploy/linuxdeploy/releases/download/continuous/linuxdeploy-x86_64.AppImage
-.. _Download the Python Linux support package for x86_64: https://briefcase-support.org/python?platform=linux&arch=x86_64&version=3.8
+.. _Download the Python Linux support package for x86_64: https://briefcase-support.org/python?platform=linux&arch=x86_64&version=3.5
 .. _Toga: https://beeware.org/project/projects/libraries/toga
 .. _GTK+: https://python-gtk-3-tutorial.readthedocs.io/
diff --git a/{{ cookiecutter.formal_name }}/Dockerfile b/{{ cookiecutter.formal_name }}/Dockerfile
index 756b942..7c71af3 100644
--- a/{{ cookiecutter.formal_name }}/Dockerfile	
+++ b/{{ cookiecutter.formal_name }}/Dockerfile	
@@ -7,29 +7,18 @@ WORKDIR /app
 ARG PY_VERSION
 ARG SYSTEM_REQUIRES
 
-# Install the deadsnakes PPA so we can get arbitrary Python versions
-RUN apt-get update -y && \
-    apt-get install -y \
-        software-properties-common \
-        dirmngr \
-        apt-transport-https \
-        lsb-release \
-        ca-certificates
-RUN apt-add-repository ppa:deadsnakes/ppa
-
 # Install git, Python, and any packages required
 RUN apt-get update -y && \
     apt-get install -y \
         git \
-        python${PY_VERSION}-dev \
-        python${PY_VERSION}-venv \
+        python3-dev \
+        python3-pip \
         ${SYSTEM_REQUIRES}
 
-# Install (and update) pip
-RUN python${PY_VERSION} -m ensurepip
-RUN python${PY_VERSION} -m pip install --upgrade pip
-RUN python${PY_VERSION} -m pip install --upgrade setuptools
-RUN python${PY_VERSION} -m pip install --upgrade wheel
+# Update pip
+RUN python3.5 -m pip install --upgrade pip
+RUN python3.5 -m pip install --upgrade setuptools
+RUN python3.5 -m pip install --upgrade wheel
 
 # Ensure Docker user UID:GID matches host user UID:GID (beeware/briefcase#403)
 ARG HOST_UID
