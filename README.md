# Flow Ratio Tuning Tool 🛠️

A simple, browser-based utility for 3D printing flow calibration.


This tool is used to tune the correct flow ratio (%) for any nozzle size based on your measured wall-thickness test results. 
It supports both single-point calculation and multi-point linear regression for more accurate tuning.

## Features

- Predict optimal flow ratio for any nozzle size
- Single-point calculation
  - Uses direct proportional scaling
- Multi-point calculation
  - Uses linear regression (y = mx + b)
- Add/remove unlimited data points
- Error handling for invalid input or degenerate regression cases
- Classic Win95-inspired UI (Lucida Console aesthetics)
- Fully client-side, no dependencies, no data sent anywhere
- Mobile-friendly layout with touch-optimized controls

## How It Works

### Single Data Point

If you enter only one test result, the tool uses a simple ratio:

`predicted_flow = (target_nozzle / measured_wall) * measured_flow`

### Multiple Data Points

If you enter 2 or more results, the tool performs linear regression:

`y = mx + b`

Where:

- x = measured wall thickness
- y = required flow ratio
- m, b are computed using least squares

Then the tool predicts:

`predicted_flow = m * nozzle_size + b`
