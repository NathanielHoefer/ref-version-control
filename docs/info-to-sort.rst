===============================================================================
Info to Sort
===============================================================================

.. contents:: Table of Contents

Add, Commit, Push Command
*************************

Rather than using three separate commands to add, commit, and push to a remote repository,
an alias command can be created that will execute all three.

To do so, execute the following command which will add it to the alias list within the ``.gitconfig`` file:

.. code-block:: bash

    git config --global alias.cmp '!f() { git add -A && git commit -m "&@" && git push; }; f'

Git Ignore
**********

Frequently, there are files or directories that should not be committed to a repository.
These files may be temporary or specific to a local machine.
To prevent these files from being added automatically, a ``.gitignore`` file must placed in the root of the git repository.

.. code-block:: bash
    :caption: ``.gitignore``

    # Sphinx
    *_build/

    # Pycharm
    *.idea/
    *.pyc