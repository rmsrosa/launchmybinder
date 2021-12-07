# mybinderlaunch

Repo to launch an instance of [mybinder.org](https://mybinder.org) in julia.

When you first launch it, or after each new commit in this branch, a new sysimage is created in [mybinder.org](https://mybinder.org), and that takes a long time (several minutes). Subsequent launches reuse this sysimage and are ready much quicker.

If you want to add notebooks, do that in a new branch. Changes in separate branches do not require building a new sysimage. Then you can launch notebooks directly from a different branch  thanks to [nbgitpuller](https://jupyterhub.github.io/nbgitpuller/index.html). It loads the contents of a different branch from the sysimage created with this branch. The link to pull this up can be generated from [nbgitpuller link generator](https://jupyterhub.github.io/nbgitpuller/link#nbgitpuller-link-generator)