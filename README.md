# nRF52 Simulator

## Overview
Example simulation of an nRF52840 DK (PCA10056) device using [Renode](https://github.com/renode/renode)

## Installation

### Linux

Download the latest linux-portable release of Renode from [the releases section](https://github.com/renode/renode/releases/tag/v1.12.0)

```
$ wget https://github.com/renode/renode/releases/download/v1.12.0/renode-1.12.0.linux-portable.tar.gz
$ mkdir renode_portable
$ tar xf renode-1.12.0.linux-portable.tar.gz -C renode_portable --strip-components=1
```

Add `renode` to the system path

```
$ cd renode_portable && export PATH="`pwd`:$PATH"
```

Verify the installation

```
$ renode -v
Renode, version 1.12.0.37823 (44d6786a-202104022100)
```

The complete installation instructions for Renode are described in the [Renode project README](https://github.com/renode/renode/blob/master/README.rst#installation)

## Running Examples

Clone this repository

```
$ git clone https://github.com/gregfolker/nrf52-simulator.git
```

From the root of the repository start the emulation with `renode`. This will launch an instance of the CLI for Renode along with a
console that displays the output of uart0

```
$ renode scripts/nrf52840.resc
```

From the Renode CLI, load the pre-compiled example binary you wish to run into flash

```
(nRF52840) sysbus LoadBinary @bin/hello-world.bin 0x00
```

Start the emulation

```
(nRF52840) start
```

## Resources

[Renode Documentation](https://renode.readthedocs.io/en/latest/index.html)

[nRF52840 Product Specification](https://infocenter.nordicsemi.com/topic/struct_nrf52/struct/nrf52840.html?cp=4_0)

[Nordic nRF5 SDK](https://www.nordicsemi.com/Products/Development-software/nRF5-SDK/Download#infotabs)
