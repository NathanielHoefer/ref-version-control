===============================================================================
Git
===============================================================================

.. contents:: Table of Contents

Git Submodules
**************

Submodules are simply referenced repositories used within a parent repository.

`Git Submodule <https://git-scm.com/docs/git-submodule>`_ - Link to Git Submodule Documentation.

Creating submodules
-------------------

Execute the following commands to create submodules within your current repository

.. code-block:: bash

    cd /path/to/parent-repo
    git submodule add <git path>
    git commit -m "Add: Submodule"

Updating submodules
-------------------

Commits can be made to submodules just as though you are working in the original repository.
It requires a ``commit``/``push`` within the submodule directory.

Updating submodules from parent
-------------------------------

Since changes to the submodules are not automatically reflected in the parent repository,
the changes must be pulled.
Execute the following command from the parent directory to update all of the submodules at once.

.. code-block:: bash

    git submodule update --recursive --remote

Cloning Repositories with Submodules
------------------------------------

When cloning a repository with a submodules, the submodules will not automatically be cloned.
To have a fully populated local repository, execute one of the following commands:

#. .. code-block:: bash

        git clone --recursive <remote repo>

#. .. code-block:: bash

        git clone <remote repo>
        git submodule init
        git submodule update --recursive --remote

Removing Ignored Files
**********************

There are times when files are committed and pushed that should have been ignored.
To remove them from the repository, execute the following command:

.. code-block:: bash

    git rm --cached <file>

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