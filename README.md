# vlc_player_ros
**vlc player in ros**

## **Dependence**

```cmd
sudo apt-get install vlc
pip install python-vlc
```



## Ros Interface

### Action 

server name: **vlc_player**

type: vlc_player_ros/VlcPlayerAction

```python
# Expanded Definition of vlc_player_ros/VlcPlayerAction
# Define the goal
string path  # absolute path of the audio file
string rate  # played rate 
string volume # played volume 0~100 
---
# Define the result
string path
string state # state can be: NothingSpecial, Opening, Buffering, Playing, Paused, Stopped, Ended, Error
---
# Define a feedback message
string path
string state
```



### Topic

name: **vlc_pause**

relation: subscribed 

type:  std_msgs/Bool

```python
# Expanded Definition of std_msgs/Bool
bool data # True: to pause; False: to resume
```

