# Vaccum-Cleaner

## Description
This repository contains a university course exercise that involves simulating an automatic vacuum cleaner. The exercise includes implementing two separate algorithms and a simulator. The algorithms will be compiled into shared object files (.so), and the simulator will generate an executable to run the simulation.


## Usage
### Building the Project
To build the project, Ensure the script has execution permissions:
```sh
chmod +x ./build_all.sh
```
Run the following script:
```sh
./build_all.sh
```
Alternatively, you can build each project manually:
```sh
# Build Algorithm A
cd ./206510398_208278945_A
mkdir build
cd build
cmake ..
make
cd ../../

# Build Algorithm B
cd ./206510398_208278945_B
mkdir build
cd build
cmake ..
make
cd ../../

# Build Simulator
cd ./Simulator
mkdir build
cd build
cmake ..
make
cd ../../
```

### Simulator
To execute the simulator, run:
```sh
./<path to Simulator>/build/myrobot
```
You can execute the program from any directory. The output files will be stored in the current working directory (CWD).

#### Flags:
- `-house_path`: Directory containing `.house` files. Defaults to CWD if not specified.
- `algo_path`: Directory containing `.so` files. Defaults to CWD if not specified.
- `num_threads`: Maximum number of threads to use. Defaults to 10 if not specified.
- `summary_only`: Generate only the summary CSV file and error files, without generating other output files. Defaults to false.
-`log`: Create a log file for each algorithm-house pair. Defaults to false.

### Simulation
To run a specific simulation with a house and output file:
```sh
python3 ./<path to Simulation>/Simulation.py ./<houseName>.house ./<outputName>.txt
```

## Output File
The output file format is a text file named <HouseName>-<AlgorithmName>.txt with the following structure:
```sh
NumSteps = <NUMBER>
DirtLeft = <NUMBER>
Status = <FINISHED/WORKING/DEAD>
InDock = <TRUE/FALSE>
Score = <NUMBER>
Steps:
<list of characters in one line, no spaces, from: NESWsF>
```
- `NumSteps`: Number of steps taken
- `DirtLeft`: Amount of dirt left
- `Status`: Simulation status (FINISHED/WORKING/DEAD)
- `InDock`: Whether the robot is in the docking station at the end (TRUE/FALSE)
- `Score`: Computed score based on the simulation



