# BCI_control_car
## Overview
Since alpha waves will appear when people are in the resting stage, subjects can control the car to move by opening or closing their eyes.

## Introduction
- 1 car movement needs 2 EEG recordings
  -  Alpha wave: action trigger
      ```Python
      peak_alpha = the sum of frequency in alpha wave / the sum of the frequency in 3-30 Hz  
      if (peak_alpha > threshold): 
        action_code = 1              # eyes closed
      else: 
        action_code = 0              # eyes opened
      ```
- Direction of movement of the car after two EEG recordings
  | Movement direction | subject's action | action_code |
  | -------- | -------- | -------- |
  | Forward     | eyes opened --> closed     | 0，1     |
  | Turn right     | eyes opened --> opened     | 0，0     |
  | Turn left     | eyes closed --> opened     | 1，0     |

## How to run
- set up EEG cap and Arduino car
- run `python ./src/utils.py`

## Reference
- For recording EEG signal: https://github.com/HeosSacer/SSVEP-Brain-Computer-Interface/tree/master
