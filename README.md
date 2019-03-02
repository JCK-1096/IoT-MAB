# IOT-MAB: Decentralized Intelligent Resource Allocation Approach for LoRaWAN Networks

## Introduction
IoT-MAB is a discrete-event simulator based on SimPy for simulating intelligent distributed resource allocation in LoRa networks and to analyse scalability. We also combine the classed and functions for Physical layer of LoRA. 

## Installation
It is recommend to use virtualenv to keep your Python environment isolated, together with virtualenvwrapper to make working with virtual environments much more pleasant, e.g.:

```python
$ pip install virtualenvwrapper
...
$ export WORKON_HOME=~/.virtualenvs
$ mkdir -p $WORKON_HOME
$ source /usr/local/bin/virtualenvwrapper.sh
$ mkvirtualenv -p python3 iot_mab
```

You can install the required packages using the provided requirements.txt file:

```python
(lorasim)$ pip install -r requirements.txt
```

## Usage

### Synopsis

```python
python3 IoT_MAB.py <nrNodes> <nrIntNodes> <nrBS> <initial> <radius> <AvgSendTime> <horizonTime>
<packetLength> <freqSet> <sfSet> <powerSet> <captureEffect> <interSFInterference> <infoMode> <logdir> <exp_name>
```

Example:

```python
python3 IoT_MAB.py --nrNodes 5 --nrIntNodes 5 --nrBS 1 --initial UNIFORM --radius 2000 --AvgSendTime 360000 --horizonTime 10  --packetLength 50 --freqSet '867300' --sfSet '7 8'  --powerSet "14"  --captureEffect 1  --interSFInterference 1 --infoMode NO --logdir logs --exp_name exp1
```
### Description
nrNodes

number of nodes to simulate.

nrIntNodes

number of smart nodes to simulate. nrIntNodes must be smaller than nrNodes

nrBS

number of base station.

initial

initial probability for learning process, which is *UNIFORM* for uniform distribution or *RANDOM* for random distribution.

radius

radius to simulate in metre.

AvgSendTime

average sending interval in milliseconds.

horizonTime

number of iteration to simulate. The simulation time is **horizonTime x AvgSendTime**

packetLength

length of packet to simulate in bytes

sfSet

set of SF to simulate, must be between 7 and 12

freqSet

set of frequency to simulate.

powerSet

set of power to simulate.

captureEffect

capture effect (power collision) or not.

interSFInterference

inter-sf interference.

infoMode

information mode to simulate.

logdir

name of folder to store simulations.

exp_name

name of folder to store scenario.

### Output

The result of every simulation run will be appended to a file named prob..._X.csv, whereby prob..._X. The data file is then plotted into .png file by using matplotlib.

## Changelogs