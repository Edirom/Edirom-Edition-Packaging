# Edirom-Edition-Packaging

This repo provides ant based packaging instructions for creating a XAR-package of digital music editions for Edirom Online.

## Prerequisites

1. Java
2. Apache Ant
3. Edition data directory

The packaging is driven by Apache Ant. As Apache Ant is a Java library you need Java installed on your build system. For detailed system requirements please see: [https://ant.apache.org/manual/install.html#sysrequirements](https://ant.apache.org/manual/install.html#sysrequirements)

To see whether it is available on your system open your commandline interface and execute the following command:

```bash
ant -v
```

If ant is available you should see an output to the commandline starting with something similar to:

```bash
Apache Ant(TM) version 1.10.11 compiled on July 10 2021
```

If Apache Ant is not available you might want to visit the following website for installation instructions: [https://ant.apache.org/manual/install.html](https://ant.apache.org/manual/install.html)

Finally, of course you need a directory containing your edition data.

## Usage

The Edirom-Edition-Packaging build process can be called from the commandline interface. It provides several build targets, e.g. for building, creating a XAR-archive, or cleaning your build environment.

Generally you have to supply the path to your edition data directory to the build process. This is done by adding  `-Duri.edition=/PATH/TO/YOUR/EDITION/DATA/DIRECTORY` when calling ant, e.g.:

```bash
ant -Duri.edition=/Volumes/Edition/my-edirom-edition xar
```

The essential part of the packaging process is the use of the properties files `build.properties` (providing default definitions) and an optional `local.properties` file (located in your edition's data directory) that can be used for overriding the defaults from `build.properties` when building locally. You can either manually copy the `build.properties` file to your edition data directory or use Apache Ant to do so by running: 

```bash
ant -Duri.edition=/PATH/TO/YOUR/EDITION/DATA/DIRECTORY properties.local.create
```

If you want to create a XAR-archive from your edition data directory that can be installed in eXist-db execute the following command:

```bash
ant -Duri.edition=/PATH/TO/YOUR/EDITION/DATA/DIRECTORY properties.local.create
```

## License

This repository is dual licensed under the terms of the [GNU General Public License version 3 (GPL-3.0)](https://opensource.org/licenses/GPL-3.0) and [Creative Commons Attribution 4.0 International License (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/)