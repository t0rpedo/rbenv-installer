# rbenv installer

This tool is used to install `rbenv` and some plugins. It also provides
scripts to install required software to be able to compile **Ruby**.

Once executed, the script makes available the following plugins:

 - the `rbenv` [commands](https://github.com/sstephenson/rbenv#command-reference)
 - the `rbenv-vars` plugin [commands](https://github.com/sstephenson/rbenv-vars)
 - the `ruby-build` plugin [commands](https://github.com/sstephenson/ruby-build)
 - the `rbenv-installer` plugin

Commands provided by rbenv installer:

 - rbenv cleanup
 - rbenv bootstrap
 - rbenv bootstrap-ubuntu-10-04
 - rbenv bootstrap-ubuntu-12-04
 - rbenv plugin
 - rbenv plugins
 - rbenv update

See [here](https://github.com/sstephenson/rbenv) for more details on `rbenv`.

## Before Installing

Install `git` and `curl`:

- Git
- Curl

## Installing

### For users

Install [rbenv] and friends by running:

    curl https://raw.github.com/fesplugas/rbenv-installer/master/bin/rbenv-installer | bash

### For developers

You can test your in-development version of the rbenv-installer (on Github):

    rm -rf ~/.rbenv/plugins
    export RBENV_INSTALLER_AUTHOR=taqtiqa-mark
    export RBENV_INSTALLER_BRANCH=feature/plugin
    curl -L https://raw.github.com/$RBENV_INSTALLER_AUTHOR/rbenv-installer/$RBENV_INSTALLER_BRANCH/bin/rbenv-installer|bash

Similarly, you can set the `RBENV_AUTHOR` and `RBENV_PLUGIN_AUTHOR` Github names.
Both of these default to [sstephenson](https://github.com/sstephenson).

Default behavior is to install from the `master` branches. To install from:

 - the `abc` branch of [sstephenson/rbenv](https://github.com/sstephenson/rbenv)
 - the `xyz` branch of [fesplugas/rbenv-installer](https://github.com/fesplugas/rbenv-installer)
 - the `klm` branch of the plugins [sstephenson:rbenv-vars](https://github.com/sstephenson/rbenv-vars) and [sstephenson:ruby-build](https://github.com/sstephenson/ruby-build)

```
export RBENV_BRANCH=abc
export RBENV_INSTALLER_BRANCH=xyz
export RBENV_PLUGIN_BRANCH=klm
curl https://raw.github.com/fesplugas/rbenv-installer/master/bin/rbenv-installer | bash
```

## Managing a Ruby (rbenv usage)

Install Ruby `1.9.3-p374` and make it global:

    rbenv install 1.9.3-p374
    rbenv global 1.9.3-p374

Uninstall Ruby `1.9.3-p194`:

    rbenv uninstall 1.9.3-p194

See [here](https://github.com/sstephenson/ruby-build) for more details.

## Commands (provided by rbenv-installer)

Updating `rbenv` and `rbenv-installer`:

    rbenv update

Remove all the gems for the current Ruby:

    rbenv cleanup

To install a plugin use:

    rbenv plugin dcarley:rbenv-sudo

You can view more information on `rbenv plugin` use with:

    rbenv help plugin

If you are installing `rbenv` in Ubuntu you'll probably need to install some
required packages. You can use the provided `bootstrap` scripts.

    rbenv bootstrap-ubuntu-12-04
    rbenv bootstrap-ubuntu-10-04

To update `RubyGems` and install `bundler` and `rake`:

    rbenv bootstrap
