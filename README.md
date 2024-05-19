# ROS1 repository contains all the package for base ros1

## Build commands
```
git clone ...
cd ros1
catkin build
```

## Known issues
### For the issue in log4xx shaerd_mutex try this
Their proposed solution is to modify /usr/include/log4cxx/boost-std-configuration.h, from this:

#define STD_SHARED_MUTEX_FOUND 1
#define Boost_SHARED_MUTEX_FOUND 0

to this:

#define STD_SHARED_MUTEX_FOUND 0
#define Boost_SHARED_MUTEX_FOUND 1

Which it works
Also according to the tracker, this should be resolved upstream, but I guess the build hasn't made it to the arch repository yet, so this should be a temporary fix and should be fixed whenever the log4cxx is updated.