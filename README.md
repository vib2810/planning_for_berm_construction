# Planning for Autonomous Berm Construction in Lunar-like Terrains
## Course Project for 16-782 Planning and Decision Making in Robotics

### Team Members
- Vibhakar Mohta (vmohta)
- Hariharan Ravichandran (hravicha)

### Pre-requisites:
1. Install Docker
2. Add Docker to Sudoers


## Instructions to Run Code
### Opening a terminal with docker
1. Run docker-compose up:
```
cd <path_to_repo>
docker-compose up
```
2. Attach a terminal to the docker container
```
cd scripts
bash autonomy_terminal.sh
```

### Running the code
NOTE: Run the commands inside the docker container terminal

0. Build the package with symlink install
```
colcon build --packages-up-to lx_planning --symlink-install
```
1. Start the task optimizer node:
```
ros2 run lx_planning task_optimizer_node
```
2. Call the task optimizer node with the desired yaml file name to call the task optimizer with:
```
python3 src/lx_packages/lx_planning/src/call_task_optimizer.py <map_yaml_name>
```
3. Run the animation script:
```
python3 src/lx_packages/lx_planning/animation/animate.py <map_yaml_name>
```
Video is saved as `animation_<map_yaml_name>.mp4` in the bags folder

Note:
Run these to maps reproduce results in the report
- env_5_4
- env_5_10
- env_5_16
