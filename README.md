rbenv installer
===============

This tool is used to install `rbenv` and some plugins. It also provides 
scripts to install required software to be able to compile **Ruby**.

Installed plugins are `rbenv-vars`, `ruby-build` & `rbenv-installer`.

Once executed, the script makes available, all `rbenv` [commands](https://github.com/sstephenson/rbenv#command-reference)
and the following `rbenv-installer` plugin specific commands:
 - rbenv cleanup
 - rbenv bootstrap
 - rbenv bootstrap-ubuntu-10-04
 - rbenv bootstrap-ubuntu-12-04
 - rbenv plugin
 - rbenv plugins
 - rbenv update

## Before Installing

Install `git` and `curl`:

    sudo apt-get -y install git-core curl


# Managing rbenv and rbenv-installer plugins

## Installing rbenv

### For users
Install [rbenv] and friends by running:

    curl https://raw.github.com/fesplugas/rbenv-installer/master/bin/rbenv-installer | bash

The friends installed by default are the plugins:

 - [sstephenson:rbenv-vars](https://github.com/sstephenson/rbenv-vars)
 - [sstephenson:ruby-build](https://github.com/sstephenson/ruby-build)

### For developers
Default behavior is to install from the `master` branches. To install from:

 - the `abc` branch of [sstephenson/rbenv](https://github.com/sstephenson/rbenv)
 - the `xyz` branch of [fesplugas/rbenv-installer](https://github.com/fesplugas/rbenv-installer)
 - the `klm` branch of the plugins [sstephenson:rbenv-vars](https://github.com/sstephenson/rbenv-vars) and [sstephenson:ruby-build](https://github.com/sstephenson/ruby-build)

````
export RBENV_BRANCH=abc
export RBENV_INSTALLER_BRANCH=xyz
export RBENV_PLUGIN_BRANCH=klm
curl https://raw.github.com/fesplugas/rbenv-installer/master/bin/rbenv-installer | bash
````

## Updating rbenv

To update `rbenv` and the plugins provided by this installer run:

    rbenv update

# Managing a Ruby

## Installing

Install Ruby `1.9.3-p194` and make it global:

    rbenv install 1.9.3-p194
    rbenv global 1.9.3-p194

### Cleanup a Ruby's Gems

Remove all the gems for the current Ruby:

    rbenv cleanup

# Managing Rbenv Plugins
## Installing (Updating) a plugin

### Example 1: Install then update+install

Default behavior is to install from the `master` branch.
Install the `rbenv-vars` plugin from [sstephenson/rbenv-vars](https://github.com/sstephenson/rbenv-vars):

    rbenv plugin sstephenson:rbenv-vars

Install multiple plugins and update rbenv-vars plugin (installed above):

    rbenv plugins sstephenson:rbenv-vars sstephenson:ruby-build

### Example 2: Install from a specific branch

Install the `xyz` plugin from the `develop` branch of ABC's repository `xyz`:

    export RBENV_PLUGIN_BRANCH=develop
    rbenv plugin abc:xyz

## Bootstrap

If you are installing `rbenv` in Ubuntu you'll probably need to install
required packages first:

    rbenv bootstrap-ubuntu-12-04
    rbenv bootstrap-ubuntu-10-04

To update `RubyGems` and install `bundler` and `rake`:

    rbenv bootstrap


## About rbenv

**rbenv** source code is available at <https://github.com/sstephenson/rbenv>

[rbenv]: https://github.com/sstephenson/rbenv
