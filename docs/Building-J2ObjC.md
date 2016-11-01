---
title: Building J2ObjC
layout: docs
---

# Building J2ObjC

### Requirements

- Apple Mac OS X system
- Latest version of [Xcode](https://developer.apple.com/xcode/index.php)
- Apache Maven
- (Recommended but not required) Google Protocol Buffer source

Note: Maven is no longer distributed with Xcode's command-line tools. Here is [a well-written installation guide by Pankaj Kumar](http://www.journaldev.com/2348/how-to-install-maven-on-mac-os-x-mavericks-10-9).

### Building J2ObjC

To build from a command-line in a Terminal window, run:

    $ make dist

to build just the translator and libraries,

    $ make frameworks

to build the full distribution (including frameworks),

    $ make protobuf_dist

to build the protocol buffer compiler and runtime for J2ObjC, and

    $ make all_dist

to build everything that is included in the project's distribution bundles.

#### Optional Setup for Protocol Buffers

To build the optional protocol buffer compiler and runtime, first clone the [GitHub google/protobuf
repository](https://github.com/google/protobuf).
Next, define the `PROTOBUF_ROOT_DIR` environment variable to point to the top-level directory of that cloned repository. 

### Testing J2ObjC

To test from a command-line in a Terminal window, run:

    $ make test

to run translator and library unit tests, and

    $ make test_all

to run all unit tests, including for protocol buffers.

### Cleaning/Resetting a Build

    $ make clean

to remove all files generated by the build.

### Parallel Builds

The J2ObjC build supports parallel builds, which are specified using the `-j<n>` flag, where _n_ is the maximum number of concurrent tasks. The maximum depends on how fast/powerful your system is; we suggest starting with `-j4`. Increase the number to shorten build times if your system can handle it, and decrease it if make fails with system errors.