# mybinderlaunch

Repo that works as a template to launch an instance of [mybinder.org](https://mybinder.org) in julia.

When you first launch [mybinder.org](https://mybinder.org), or after each new commit, a new sysimage is created at [mybinder.org](https://mybinder.org), and that takes a long time (several minutes). Subsequent launches reuse the sysimage and are spawned much quicker.

The idea here is to separate the setup files and the notebooks into different branches, so you only need to commit to the setup branch occasionally, when adding or removing packages. Only in those cases a new sysimage needs to be created. If you commit to a different branch, there is no need to rebuild the sysimage.

Thus, if you want to add notebooks or other working stuff, do that in a different branch. Changes in other branches do not require building a new sysimage. Then you can launch notebooks by accessing the sysimage build for the setup branch but pulling the notebooks from a different branch. This is accomplished seamlessly with the help of [nbgitpuller](https://jupyterhub.github.io/nbgitpuller/index.html). The only think you need it to properly set up the link to do that. You can generated one from [nbgitpuller link generator](https://jupyterhub.github.io/nbgitpuller/link#nbgitpuller-link-generator) or reuse an existing one.

For instance, in order to launch jupyter lab with [notebooks/index.ipynb](notebooks/index.ipynb) notebook in this branch, using the setup in branch `mybinderenv`, one needs the link

https://mybinder.org/v2/gh/rmsrosa/launchmybinder/mybinderenv?urlpath=git-pull%3Frepo%3Dhttps%253A%252F%252Fgithub.com%252Frmsrosa%252Flaunchmybinder%26urlpath%3Dlab%252Ftree%252Flaunchmybinder%252Fnotebooks%252Findex.ipynb%26branch%3Dmain

https://mybinder.org/v2/gh/rmsrosa/launchmybinder/mybinderenv?urlpath=git-pull?repo=https:://github.com/rmsrosa/launchmybinder&urlpath=lab/tree/launchmybinder/notebooks/index.ipynb&branch=main