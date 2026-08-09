# Tank Filling Automation

This is a small PLC project I made while learning CODESYS and Ladder Logic.

The idea was to make a simple tank filling system where the PLC controls an inlet valve based on the tank level and operator commands.

## What I worked on

I worked on:

- Basic Ladder Logic
- Digital inputs and outputs
- Manual and automatic modes
- Start and Stop logic
- Latching the filling command
- High level shutdown
- Emergency stop
- A 30 second filling timeout
- Alarm and tank full indications
- Testing the logic in CODESYS simulation

## Main Tags

| Tag | Description |
|---|---|
| PB_Start | Start pushbutton |
| PB_Stop | Stop pushbutton |
| LSL_101 | Low level switch |
| LSH_101 | High level switch |
| HS_Auto | Auto/Manual selector |
| PB_EStop | Emergency stop |
| XV_101 | Inlet solenoid valve |
| XL_Full | Tank full lamp |
| XA_Alarm | Alarm lamp |
| Fill_Request | Internal filling command |
| Fill_Timeout | Internal timeout flag |

## How it works

In automatic mode, the low level switch starts the filling operation. The valve opens and stays open until the high level switch is reached.

In manual mode, I can start the filling using the Start pushbutton and stop it using the Stop pushbutton.

I also added a 30 second timer so that if the tank does not reach the high level within that time, the filling stops and the alarm turns on.

The Emergency Stop also stops the filling and turns on the alarm.

## Testing

I tested the main parts of the logic using the CODESYS simulation.

- Manual start: PASS
- Manual latch: PASS
- Manual stop: PASS
- Automatic start: PASS
- High level shutdown: PASS
- Emergency stop: PASS
- Filling timeout: PASS

## Files

The CODESYS project is included in the repository.

The Excel file contains the I/O list, BFD, control philosophy, cause and effect table, PLC tags and test results.

The screenshots show some of the tests I ran while checking the ladder logic.
