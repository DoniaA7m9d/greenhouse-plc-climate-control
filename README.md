# Greenhouse Climate Control – PLC Ladder Logic

Ladder logic program for automated greenhouse climate control,
covering temperature, humidity, ventilation, cooling, and shading.
Built and simulated in a mobile PLC ladder logic simulator.

## Features
- Temperature control: heater, exhaust fan, circulation fan
- Natural ventilation: side vents and roof vents (motorized, with limit switches)
- Evaporative cooling: cooling pad pump
- Humidification: fogging pump
- Light control: shade screen extend/retract
- Hysteresis on all thresholds (prevents rapid ON/OFF cycling)
- Safety: emergency stop, low water-level lockout, wind/rain vent lock, critical-temperature alarm
- Auto mode enable

## Setpoints (editable in the N file)
| Parameter | ON | OFF |
|---|---|---|
| Low temperature (heater) | < 15 °C | > 18 °C |
| Warm (vents open) | > 26 °C | < 24 °C |
| High (exhaust fan) | > 28 °C | < 26 °C |
| Very high (cooling pad) | > 30 °C | < 28 °C |
| Critical (alarm) | > 38 °C | < 35 °C |
| Low humidity (fogging) | < 60 % | > 68 % |
| High humidity | > 85 % | < 80 % |
| High light (shade) | > 600 W/m² | < 500 W/m² |

## Program Structure (MR – main routine, 37 rungs)
1. Rung 1: system enable (AutoMode AND NOT EmerStop)
2. Rungs 2–17: analog comparisons (AI values vs. N-file setpoints)
3. Rungs 18–25: state bits with seal-in hysteresis
4. Rungs 26–37: outputs and interlocks

## Files and Data
- AI: TempValue, HumValue, LightValue
- N: setpoints
- B: internal state bits
- I: switches and limit switches
- O: actuators and alarm

See docs/io_list.md for the full tag list.

## Tools
Mobile PLC ladder logic simulator (.plcs project file included).

## Limitations / Future Work
- Tested in simulation only, not on physical PLC hardware
- Planned: motor-run timers, sensor-failure detection, manual mode,
  VPD-based control, ESP32 gateway for sensor readings and Telegram alerts

## Author
Donia – Agricultural Engineering student (IoT & precision agriculture)
