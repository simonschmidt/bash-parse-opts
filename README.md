Bash (long) option parser
===============

Argument parser for --long-options

Example
---------------

    $ cat example
    #!/usr/bin/env bash
    source parse_options
    
    options[foo]="foo default"
    options_flags=('verbose')
    parse_options "$@"
    
    for k in "${!options[@]}"; do
      echo "$k:${options[$k]}"
    done
    
    $ ./example --verbose --bar --bar-value --empty-option ''
    verbose:on
    bar:--bar-value
    foo:12
    empty-option:


## Settings

The settings are provided through the environment

### options

Associative array of default values, declared when sourcing the script.
This is also where the parsed result is stored.

    options[some-option]="some value"

### options\_flags

Array of options to be interpreted as flags, i.e. that have no value

    options_flags=('debug' 'enable-foo')

### options\_force

If set to 'yes' an error will be thrown on unknown options

    options_force='yes'

