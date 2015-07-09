.. _toolbox:

Toolbox CLI
===========

The toolbox is a CLI (command line interface) tool that is used to do
administration tasks. Toolbox executables are located in ``$XP_INSTALL/toolbox``
folder. Use ``toolbox.sh`` for mac/unix environments and ``toolbox.bat``
for windows environments.

To get help for the commands, just type the following::

  $ toolbox.sh

  usage: toolbox <command> [<args>]

  The most commonly used toolbox commands are:
      delete-snapshots   Deletes snapshots, either before a given timestamp or by name.
      dump               Export every branch in specified repository.
      export             Export node from a branch in a repository.
      help               Display help information
      import             Import nodes from an export into a repository branch.
      list-snapshots     Returns a list of existing snapshots with name and status.
      reindex            Reindex content in search indices for the given repository and branches.
      restore            Restores a snapshot of a previous state of the repository.
      snapshot           Stores a snapshot of the current state of the repository.

  See 'toolbox help <command>' for more information on a specific command.

To get help for a specific command, you can type ``toolbox.sh help <command>``, like::

  $ toolbox.sh help import

Here's a list of all the commands that you can do with the toolbox:

.. toctree::
   :maxdepth: 1

   snapshot
   restore
   list-snapshots
   delete-snapshots
   export
   import
   reindex
   dump