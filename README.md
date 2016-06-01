
# SyncTime Simulink function

Cross platform, for simulation and embedding

Produces epoch based timestamp and syncs the model to a given period

# Usage

Specify dt as the period: if dt=0 just measure time otherwise sleeps a variable time to align with the dt

# Internals

- Linux: clock_gettime(CLOCK_REALTIME, &spec);
- OSX: gettimeofday(&TV, NULL);
- Windows: GetSystemTimeAsFileTime base + GetTickCount or QueryPerformanceCounter 

# TODO
Make Windows use GetSystemTimeAsFileTime always if needed