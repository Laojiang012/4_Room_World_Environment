# 4 Types of 4-Room-World Environment
This folder contains in totall **4 Types of 4-Room-World Environment** which are extenstions of discrete 4-Room-Grid World proposed in [Sutton et al., AI1991].

## Virtual Environment
### 1. FourRoomGridWorld
In 4-Room Grid World, the state and action are discrete value.
>The cells of the grid corresponds to the states of the environment of four rooms as shown in **4Room World Screenshot**. From any state the agent can perform one of four actions, **up**, **down**, **left** or **right**, which have a stochastic effect. With probability 2/3, the actions cause the agent to move one cell in the corresponding direction, and with probability 1/3, the agent moves instead in one of the other three directions, each with probability 1/9. In either case, if the movement would take the agent into a wall then the agent remians in the same cell. Rewards are **zero** on all state transitions except transiting into goal state which has reward **one**. 
* Observation Space: gym.spaces.Discrete(104)
   * 100 ordinary floor states
   * 4 hallways
* Action Space: gym.spaces.Discrete(4)
   * up: 0
   * down: 1
   * left: 2
   * right: 3
* Reward: 
   * 1: in goal state
   * 0: in other states
* Implemented in `Environment/FourRoomGridWorld.py`
* Scene: `FourRoomScene/4_room_world.ttt`

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  <img src="https://github.com/LinghengMeng/4_Room_World_Environment/blob/master/Images/4Room_axis_Legend.png" width="250" height="250" /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <img src="https://github.com/LinghengMeng/4_Room_World_Environment/blob/master/Images/4Room_Legend.png"  height="250" /> 

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; (a) State &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (b) Action and Goal

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **Figure 1. 4-Room Grid World**

### 2. FourRoomContinuousWorld
In 4-Room continuous World, the state and action are continuous value.
* Observation Space: gym.spaces.Box()
   * x-position: [-1, 1] corresponding to axis [-6, 6] in V-REP scene.
   * y-position: [-1, 1] corresponding to axis [-6, 6] in V-REP scene.
* Action Space: gym.spaces.BOx()
   * orientation: [-1, 1] corresponding to [- &pi;, &pi;] in V-REP scene.
   * stride: [-1, 1] corresponding to [0, 1] in V-REP scene.
* Reward: 
   * 1: in goal region
   * 0: in other positions
* Implemented in `Environment/FourRoomGridWorld.py`
* Scene: `FourRoomScene/4_room_world.ttt`

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  <img src="https://github.com/LinghengMeng/4_Room_World_Environment/blob/master/Images/4Room_Continuous_World_State_Legend.png" width="250"  /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <img src="https://github.com/LinghengMeng/4_Room_World_Environment/blob/master/Images/4Room_Continuous_World_Action_Legend.png"  height="250" /> 

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; (a) State &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (b) Action and Goal

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **Figure 2. 4-Room Continuous World**

### 3. FourRoomOverheadVisionWorld
In 4-Room Overhead Vision World, the states are a sequence of images coming from a vision sensor overlooking the whole world.
* Observation Space: gym.spaces.Box()
   * Image: 
* Action Space: gym.spaces.Box()
   * orientation: [-1, 1] corresponding to [- &pi;, &pi;] in V-REP scene.
   * stride: [-1, 1] corresponding to [0, 1] in V-REP scene.
* Implemented in `Environment/FourRoomOverheadVisionWorld.py`
* Scene: `4_room_overhead_vision_world.ttt`

### 4. FourRoomFirstPersonVisionWorld
In 4-Room First Person Vision World, the states are a sequence of image coming from eye (i.e. a vision sensor attached on participant's head) of participant which can only partially observe the state of the world.
* Observation Space: gym.spaces.Box()
   * Image: 
* Action Space: gym.spaces.Box()
   * orientation: [-1, 1] corresponding to [- &pi;, &pi;] in V-REP scene.
   * stride: [-1, 1] corresponding to [0, 1] in V-REP scene.
* Implemented in `Environment/FourRoomOverheadVisionWorld.py`
* Scene: `4_room_first_person_vision_world.ttt`



## Reference
[Sutton, Richard S., Doina Precup, and Satinder Singh. "Between MDPs and semi-MDPs: A framework for temporal abstraction in reinforcement learning." Artificial intelligence 112, no. 1-2 (1999): 181-211.](https://ac.els-cdn.com/S0004370299000521/1-s2.0-S0004370299000521-main.pdf?_tid=5e385c67-79e7-4e07-af80-d4bb0abbbb93&acdnat=1534771730_5258b8e295835695ebde7f6976d1291d)
