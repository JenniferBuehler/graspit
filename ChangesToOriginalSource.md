All changes applied to this fork which have not been merged in with the original yet:

- Catkin-stuff in the CMakeLists.txt, and the graspitConfig.cmake in cmake/

- class EGPlanner:
    * egPlanner.cpp
        - added method *runPlannerLoop()* which essentially does the same as *startThread()* (without starting a thread) and then calling *run()*.
          this was needed because all QObjects have to be created by the same thread which also runs the planning. So we cannot run the planning
          as originally with *EGPlanner* (out of the method *EGPlanner::sensorCB*). 
    * egPlanner.h
        - added method *runPlannerLoop()* (see description in source file)

