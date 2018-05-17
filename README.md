SublimeLinter-rubocop
=========================

[![Build Status](https://travis-ci.org/SublimeLinter/SublimeLinter-rubocop.svg?branch=master)](https://travis-ci.org/SublimeLinter/SublimeLinter-rubocop)

This linter plugin for [SublimeLinter](https://github.com/SublimeLinter/SublimeLinter) provides an interface to [rubocop](https://github.com/bbatsov/rubocop). It will be used with files that have the `ruby`, `ruby on rails`, `rspec`, `betterruby`, `better rspec`, `ruby experimental` or `cucumber steps` syntaxes.

## Installation
SublimeLinter must be installed in order to use this plugin.

Please use [Package Control](https://packagecontrol.io) to install the linter plugin.

Before using this plugin, you must ensure that `rubocop` (0.34.0 or later) is installed on your system. To install `rubocop`, do the following:

1. Install [Ruby](http://ruby-lang.org).

1. Install `rubocop` by typing the following in a terminal:
   ```
   [sudo] gem install rubocop
   ```

1. If you are using `rvm` or `rbenv`, ensure that they are loaded in your shell’s correct startup file. See [here](http://sublimelinter.com/en/latest/troubleshooting.html#adjusting-shell-startup-files) for more information.

In order for `rubocop` to be executed by SublimeLinter, you must ensure that its path is available to SublimeLinter. The docs cover [troubleshooting PATH configuration](http://sublimelinter.com/en/latest/troubleshooting.html#finding-a-linter-executable).

## Settings
- SublimeLinter settings: http://sublimelinter.com/en/latest/settings.html
- Linter settings: http://sublimelinter.com/en/latest/linter_settings.html

You can configure rubocop exactly the way you would from the command line, using `.rubocop.yml` configuration files. For more information, see the [rubocop documentation](https://github.com/bbatsov/rubocop#configuration).

To override the config file path, you would add this to the Sublime Linter User Settings:

```json
{
    "linters": {
        "rubocop": {
            "args": ["--config", "path/to/config.yml"]
        }
    }
}
```

### Bundler
If you are using Bundler and would like to use the locked rubocop version (which will also allow you to use `inherit_gem` in `rubocop.yml`, in case you are inheriting from another gem in the project), you must set `use_bundle_exec` to true:

```json
{
    "linters": {
        "rubocop": {
            "use_bundle_exec": true
        }
    }
}
```

### Rails
If you are using Rails and would like to use the bin/rubocop version, you must set `use_rails_bin` to true:

```json
{
    "linters": {
        "rubocop": {
            "use_rails_bin": true
        }
    }
}
```
