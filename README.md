<!--
  Copyright 2019, Data61
  Commonwealth Scientific and Industrial Research Organisation (CSIRO)
  ABN 41 687 119 230.

  This software may be distributed and modified according to the terms of
  the BSD 2-Clause license. Note that NO WARRANTY is provided.
  See "LICENSE_BSD2.txt" for details.

  @TAG(DATA61_BSD)
-->
# seL4-deprecated-manifests

For pinned versions of projects that once worked together but now have dependencies
located in the SEL4PROJ/seL4-deprecated repository.

Provides manifests for versions of projects that use libraries or configurations
that are no longer maintained in the main repositories but may still have downstream
dependencies.

Use at your own discretion.

## Checkout and build instructions

These instructions are for checking out and building the projects referred to by the manifests
in this repository that can still use the deprecated libraries in seL4-deprecated.

### camkes-arm-vm-manifest.xml

This manifest checks out a version of the camkes-arm-vm project that uses libsel4arm-vmm as a virtualisation
library instead of the newer libsel4vm.

```sh
repo init -u https://github.com/SEL4PROJ/seL4-deprecated-manifests.git -m camkes-arm-vm-manifest.xml
repo sync
(cd projects/vm && git am 0001-Use-deprecated-library-paths.patch)
mkdir build
cd build
../init-build.sh
ninja
```

### camkes-vm-examples-manifest.xml

This manifest checks out a version of the camkes-vm-examples project that uses libsel4vmm as a virtualisation
library instead of the newer libsel4vm.

```sh
repo init -u https://github.com/SEL4PROJ/seL4-deprecated-manifests.git -m camkes-vm-examples-manifest.xml
repo sync
(cd projects/vm && git am 0001-Use-deprecated-libraries.patch)
mkdir build
cd build
../init-build.sh
ninja
```
