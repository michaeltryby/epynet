<p align="center">
  <img src="https://github.com/VitensTC/epynet/blob/master/logo.png" alt="Epynet Logo"/>
</p>


EPYNET is an object oriented wrapper around the EPANET 2.1 community edition hydraulic network solver.

## Features
- [x] Hydraulic calculations
- [x] Object oriented access to Nodes, Junctions, Reservoirs, Tanks, Links, Pipes, Valves and Pumps
- [x] Convienent access to simulation results such as flow, velocity and pressure through class properties
- [x] Manipulation of valve and pump settings
- [ ] [TODO] Manipulation of pipe, junction, reservoir and tank settings
- [ ] [TODO] Chemical calculations
- [ ] [TODO] Pattern creation and manipulation

## Example Usage
```python
# load a network
from epynet import Network
network = new Network('network.inp')
# solve network
network.solve()
# properties
print network.pipes['4'].flow
print network.nodes['1'].demand
# valve manipulation
network.valves['12'].set_setting(10)
# convinience properties
print network.pipes['5'].downstream_node.pressure
print network.nodes['1'].upstream_links[0].velocity
# iterating over network items
for reservoir in network.reservoirs:
  print reservoir.uid, reservoir.outflow
```

## Installation
* Clone or download repository
* ```python setup.py install```

## Requirements
* 64 bit Python 2.7
* Windows, OSX or Linux

## Unit Tests
| **Mac/Linux** | **Windows** |
|---|---|
| [![Build Status](https://travis-ci.org/VitensTC/epynet.svg?branch=master)](https://travis-ci.org/VitensTC/epynet) | [![Build status](https://ci.appveyor.com/api/projects/status/ewa92p50rw5u0yfd?svg=true)](https://ci.appveyor.com/project/AbelHeinsbroek/epynet) |

## Acknowledgements
This project makes use of the [EPANET 2.1](https://github.com/OpenWaterAnalytics/EPANET) community version and is (partly) derived from the [epanettools](https://github.com/asselapathirana/epanettools) package (Assela Pathirana) and the [epanet-python](https://github.com/OpenWaterAnalytics/epanet-python) library (Maurizio Cingi)

## About Vitens

Vitens is the largest drinking water company in The Netherlands. We deliver top quality drinking water to 5.6 million people and companies in the provinces Flevoland, Fryslân, Gelderland, Utrecht and Overijssel and some municipalities in Drenthe and Noord-Holland. Annually we deliver 350 million m³ water with 1,400 employees, 100 water treatment works and 49,000 kilometres of water mains.

One of our main focus points is using advanced water quality, quantity and hydraulics models to further improve and optimize our treatment and distribution processes.

## Licence

Copyright 2016 Vitens

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
