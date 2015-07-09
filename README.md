* Travis-CI dependency resolution test: [![Travis dependency resolution test](https://travis-ci.org/choderalab/conda-recipes.svg?branch=master)](https://travis-ci.org/choderalab/conda-recipes)
* Jenkins `osx` build: [![Jenkins `osx` build](https://jenkins.choderalab.org/job/conda-choderalab-release-osx-2/badge/icon)](https://jenkins.choderalab.org/job/conda-choderalab-release-osx-2/) [[console log]](https://jenkins.choderalab.org/job/conda-choderalab-release-osx-2/lastBuild/consoleFull)
* Jenkins `linux` build: [![Jenkins `linux` build](https://jenkins.choderalab.org/job/conda-choderalab-release-linux-vagrant/badge/icon)](https://jenkins.choderalab.org/job/conda-choderalab-release-linux-vagrant/) [[console log]](https://jenkins.choderalab.org/job/conda-choderalab-release-linux-vagrant/lastBuild/consoleFull)
* Appveyor-CI `windows` builds [![Appveyor Build status](https://ci.appveyor.com/api/projects/status/tsjbbgtobpbb4xps?svg=true)](https://ci.appveyor.com/project/rmcgibbo/conda-recipes)

conda-recipes
-------------

Recipes for building binary conda packages for (c/)python components created by the Chodera lab.
Built binaries from these recipes are hosted on [binstar.org](https://binstar.org/choderalab).

To install packages run,

```
# Add my channel
$ conda config --add channels http://conda.binstar.org/choderalab

# Install one of our packages, like MDTraj
conda install mdtraj

# Or OpenMM
conda install openmm
```

To build a single Chodera lab conda package:

```
conda build packagename
```

To build all Chodera lab conda packages for all versions of python, you can use the
included script:

```
./conda-build-all ./*
```

To upload to the Chodera lab binstar org, use

```
binstar upload -u choderalab package.bz2
```

Command taken from this forum post: [From Binstar Forums](https://groups.google.com/a/continuum.io/forum/#!topic/conda/uYtVRGW--iU)

To upload multiple packages to the test channel (for beta testing / pre-release)

```
binstar login  # workaround bug in binstar login.
binstar upload /home/vagrant/miniconda/conda-bld/linux-64/*.bz2  -u choderalab --channel test
```

