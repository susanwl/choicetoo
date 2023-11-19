# Overview

As gentoo is becoming an RHEL clone, this repository aims to provide a few
ebuilds to restore alternative udev (e.g. eudev) implementations and provide
more init system choices.


# Installation

1. Add `choicetoo` repository to
[repos.conf](https://wiki.gentoo.org/wiki//etc/portage/repos.conf):

```
[choicetoo]
priority = 50
location = /var/db/repos/choicetoo
sync-type = git
sync-uri = https://github.com/susanwl/choicetoo.git
auto-sync = Yes
```

2. [Optional] Override `::gentoo` ebuilds by `::choicetoo``. See below.


# Overriding ::gentoo ebuilds

`choicetoo` provides alternative ebuilds for packages already available in
the master `gentoo` repository.
To ensure the priority of `choicetoo` ebuilds, add the following items to
[package.mask](https://wiki.gentoo.org/wiki//etc/portage/package.mask)

1. To enable alternative `udev` implementations, add to `packages.mask`

```
virtual/libudev::gentoo
virtual/udev::gentoo
```


