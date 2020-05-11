# Embedded work repository 

# ROS package: |my_topics|

This is a simple executable file that is connected to the ROS network.
The initial code specifies which interpreter is going to be used, which is Python. 

It has a node that is initialized and registered with roscore to continually send a string type message.
The message is a counter that uses Int32, which has to be integer, from standard messages.
It keeps a max of 5 messages

It's set to run loops at 2 Hz which makes it get called twice a second. 
Doing this it adapts the wait time depending on how long the previous execution took.

It also has a separate node which subscribes to the topic the other node is pushing. It receives messages from the other node and prints it using callback. 


## Requirements

The file will work on Unix-based platforms such as Ubuntu. It works on ROS Distribution "ROS Melodic Morenia"

## Installation and configuration


In one terminal enter the following:
Catkin_make                             ### "to build the files"
source devel/setup.bash                 ### "to source the workspace"


## Getting started

In one terminal enter the following:
rosrun my_topics topic_publisher.py
rosrun my_topics topic_subscriber.py

In another terminal enter the following:
roscore

In a third terminal the following can be entered:
rostopic

## Usage
The following useful commands can be entered in the terminal. 

"rostopic list"            # Gives a list of published topics
"rostopic echo counter"    # Shows what is being published to the counter topic without stopping
"rostopic hz counter"      # Gives information on the publish average speed
"rostopic info counter"    # Gives information on the message type, number of subscribers/publishers, etc. 
"ctrl+c"                   # The loop can be shut down with
