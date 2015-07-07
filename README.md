# TwinCAT3_StopWatch
Function block with a timer functionality. Similar to a stopwatch.

#INPUTS
START         : BOOL;
RESET         : BOOL;

The rising-edge of START input will trigger the time counting to start. The falling-edge of the START input will stop the time counting.
The rising-edge of the RESET input will reset all values to zero. If the timer is already running, it will stop the timer, then set the value to zero.

To start again, retrigger the START input.

#OUTPUTS
ELAPSED_TIME  : TIME;

The ELAPSED_TIME output is the current stopwatch time. The type is of the IEC61131 standard type TIME. The smallest unit is 1ms.

Internally, the stopwatch will count the time based on the PLC's cycle time. However, due to the resolution of the TIME type, internally, it will only count the time once the 1ms resolution is reached.


