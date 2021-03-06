# puppet-users

#### Table of Contents

1. [Overview](#overview)
2. [Parameters](#parameters)
3. [Usage](#usage)
4. [Limitations](#limitations)
5. [Contributors](#contributors)
6. [Release Notes](#releasenotes)

## Overview

This module manages users and ssh keys. Both authorized_keys and ssh keys are supported.
Requires stdlib and works with puppet >= 2.7

## Parameters

The following parameters are supported:

* **user**: User name, defaults to the resource name if not present.
* **groups**: Groups to which the user belongs. Primary group should not be listed here.
* **uid**: User ID.
* **gid**: Group ID.
* **group**: Primary group name.
* **homepath**: Home dir path, defaults to '/home'.
* **authorized_keys**: Hash of optional authorized keys.
  - Example: { "root-key-1" => { key => '`<public key>`', type => 'ssh-rsa', user => 'root' } }
* **keys**: Hash of optional keys.
  - Example: { "root-key-1" => { priv => '`<private key>`', pub => '`<public key>`', type => 'ssh-rsa', user => 'root' } }
* **ensure**: Ensure present or absent for this user

Valid types for keys are `ssh-rsa` and `ssh-dsa`


## Usage

Sample usage:

```
users {'foo':
   ensure => present
}
```

## Limitations

Tested on RedHat and derivatives only.

## Contributors

* https://github.com/desalvo/puppet-users/graphs/contributors

## Release Notes

**0.1.1**

* Fix typo in dependencies

**0.1.0**

* Initial version.
