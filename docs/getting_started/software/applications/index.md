---
title: Software Applications # Title displayed at the top of the page
template: software_applications.html #custom template
hide:
    - toc # hides the table of contents on the page
---

<!--This page used custom template software_applications.html see software_applications.md-->

## Software from Modules

'Modules' are a convenient way to provide access to the wide range of applications we have already installed on the cluster.

| Command                               | Description                                          | Example                                |
| ------------------------------------- | ---------------------------------------------------- | -------------------------------------- |
| `module load <module name>`           | Loads <module name>, (default version)               | `module load Python`                   |
| `module load <module name>/<version>` | Loads <module name>, <version>                       | `module load Python/3.11.6-foss-2023a` |
| `module purge`                        | Removes all loaded modules                           |                                        |
| `module list`                         | Lists currently loaded modules.                      |                                        |
| `module spider`                       | Lists all _available_ modules.                       |                                        |
| `module spider <module name>`         | Searches (fuzzy) available modules for <module name> | `module spider python`                 |

For a full list of module commands run `man module` or visit the [lmod documentation](https://lmod.readthedocs.io/en/latest/010_user.html).


### EESSI

Through Modules/LMOD we have provided a mirror of the software packages curated by the [European Environment for Scientific Software Installations (EESSI)](https://www.eessi.io/docs/)

There are currently 2 EESSI modules available on the cluster - `eessi/2023.06` and the default `eessi/2025.06`. For a full list of what software is available through these please refer to the [Software available in EESSI page](https://www.eessi.io/docs/available_software/)

#### Using the EESSI modules

In order to browse or load the modules provided through EESSI, you must first load the relevant EESSI module. The current offerings can be seen with `module avail eessi`. Then load the module e.g. `module load eessi/2025.06`. Once the EESSI module is loaded the `module spider` and `module avail` commands will search through the modules supplied by EESSI.


## List of Modules/Applications provided by eResearch Support
