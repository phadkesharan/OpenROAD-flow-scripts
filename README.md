# OpenROAD Flow

[![Build Status](https://jenkins.openroad.tools/buildStatus/icon?job=OpenROAD-flow-scripts-Public%2Fpublic_tests_all%2Fmaster)](https://jenkins.openroad.tools/view/Public/job/OpenROAD-flow-scripts-Public/job/public_tests_all/job/master/)

OpenROAD Flow is a full RTL-to-GDS flow built entirely on open-source tools.
The project aims for automated, no-human-in-the-loop digital circuit design
with 24-hour turnaround time.

## Install on Windows Locally using WSL

### WSL Installation 
- Download WSL for windows [documentation here](https://docs.microsoft.com/en-us/windows/wsl/install).
- Install UBUNTU from windows store

### Downloading and building openRoad-flow-scripts

Access the wsl ubuntu terminal
- Clone this fork of the open-road-flow-scripts repo :
`git clone --recursive https://github.com/phadkesharan/OpenROAD-flow-scripts.git`

- Download Dependencies
`cd OpenROAD-flow-scripts/tools/OpenROAD`
`./etc/DependencyInstaller.sh -dev`

- Install following python packages using pip
	- time
	- tcl
	- libffi-devel
	- padas
- Install KLayout `https://www.klayout.de/` OR use `sudo apt install klayout`

- Clone and Build
- Navigate to root directory openRoad-flow-scripts  : `cd ../../`
- Build `./build_openroad.sh --local`

### Verifying installation

- setup environment variables : `source ./setup_env.sh`
- yosys: `yosys -help`
- openroad: `openroad -help`


### Running Complete flow on Designs
- Navigate to flow directory `cd flow`
- Copy the path to config file for prefered design from the makefile 
	Eg `./designs/sky130hd/ibex/config.mk`
- Run the make with the config path : `make DESIGN_CONFIG=<config file path>`
	Eg : `make DESIGN_CONFIG=./designs/sky130hd/ibex/config.mk`
## Using the Flow

- See the OpenROAD [documentation here](https://openroad.readthedocs.io/en/latest/).
- How to [start using OpenROAD flow here](https://openroad.readthedocs.io/en/latest/user/GettingStarted.html).
- Our [user guide here](https://openroad.readthedocs.io/en/latest/user/UserGuide.html).
- Our [Flow Tutorial here](https://openroad.readthedocs.io/en/latest/tutorials/FlowTutorial.html).

## Citing this Work

If you use this software in any published work, we would appreciate a citation!
Please use the following references:

```
@article{ajayi2019openroad,
  title={OpenROAD: Toward a Self-Driving, Open-Source Digital Layout Implementation Tool Chain},
  author={Ajayi, T and Blaauw, D and Chan, TB and Cheng, CK and Chhabria, VA and Choo, DK and Coltella, M and Dobre, S and Dreslinski, R and Foga{\c{c}}a, M and others},
  journal={Proc. GOMACTECH},
  pages={1105--1110},
  year={2019}
}
```

A copy of this paper is available
[here](http://people.ece.umn.edu/users/sachin/conf/gomactech19.pdf) (PDF).

```
@inproceedings{ajayi2019toward,
  title={Toward an open-source digital flow: First learnings from the openroad project},
  author={Ajayi, Tutu and Chhabria, Vidya A and Foga{\c{c}}a, Mateus and Hashemi, Soheil and Hosny, Abdelrahman and Kahng, Andrew B and Kim, Minsoo and Lee, Jeongsup and Mallappa, Uday and Neseem, Marina and others},
  booktitle={Proceedings of the 56th Annual Design Automation Conference 2019},
  pages={1--4},
  year={2019}
}
```

A copy of this paper is available
[here](https://vlsicad.ucsd.edu/Publications/Conferences/371/c371.pdf) (PDF).

If you like the tools, please give us a star on our GitHub repos!

## License

The OpenROAD-flow-scripts repository (build and run scripts) has a BSD 3-Clause License.
The flow relies on several tools, platforms and designs that each have their own licenses:

- Find the tool license at: `OpenROAD-flow-scripts/tools/{tool}/` or `OpenROAD-flow-scripts/tools/OpenROAD/src/{tool}/`.
- Find the platform license at: `OpenROAD-flow-scripts/flow/platforms/{platform}/`.
- Find the design license at: `OpenROAD-flow-scripts/flow/designs/src/{design}/`.

