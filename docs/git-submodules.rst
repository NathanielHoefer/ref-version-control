===============================================================================
Git Submodules
===============================================================================

Submodules are simply referenced repositories used within a parent repository.

`Git Submodule <https://git-scm.com/docs/git-submodule>`_ - Link to Git Submodule Documentation.

Creating submodules
*******************

Execute the following commands to create submodules within your current repository

.. code-block:: bash

    cd /path/to/parent-repo
    git submodule add <git path>
    git commit -m "Add: Submodule"

Updating submodules
*******************

Commits can be made to submodules just as though you are working in the original repository.
It requires a ``commit``/``push`` within the submodule directory.

Updating submodules from parent
*******************************

Since changes to the submodules are not automatically reflected in the parent repository,
the changes must be pulled.
Execute the following command from the parent directory to update all of the submodules at once.

.. code-block:: bash

    git submodule update --recursive --remote

Cloning Repositories with Submodules
************************************

When cloning a repository with a submodules, the submodules will not automatically be cloned.
To have a fully populated local repository, execute one of the following commands:

#. .. code-block:: bash

        git clone --recursive-submodules -j8 <remote repo>



#. .. code-block:: bash

        git clone <remote repo>
        git submodule init
        git submodule update --recursive --remote
