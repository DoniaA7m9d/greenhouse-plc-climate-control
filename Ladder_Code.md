# Greenhouse PLC - Ladder Logic Program (37 Rungs)

Rung 1 : System Enable

|---] [--- AutoMode ---] / [--- EmerStop ----------------( SystRun )---|

COMPARISON BLOCKS (Rungs 2-17)

Rung 2   LES TempValue TempLowOn      DN=cTLowOn
|---[LES TempValue TempLowOn]--------------------------------( cTLowOn )---|

Rung 3   GRT TempValue TempLowOff     DN=cTLowOff
|---[GRT TempValue TempLowOff]-------------------------------( cTLowOff )---|

Rung 4   GRT TempValue TempWarmOn     DN=cTWarmOn
Rung 5   LES TempValue TempWarmOff    DN=cTWarmOff
Rung 6   GRT TempValue TempHighOn     DN=cTHighOn
Rung 7   LES TempValue TempHighOff    DN=cTHighOff
Rung 8   GRT TempValue TempVHighOn    DN=cTVHighOn
Rung 9   LES TempValue TempVHighOff   DN=cTVHighOff
Rung 10  GRT TempValue TempCritOn     DN=cTCritOn
Rung 11  LES TempValue TempCritOff    DN=cTCritOff
Rung 12  LES HumValue HumLowOn         DN=cHLowOn
Rung 13  GRT HumValue HumLowOff        DN=cHLowOff
Rung 14  GRT HumValue HumHighOn        DN=cHHighOn
Rung 15  LES HumValue HumHighOff       DN=cHHighOff
Rung 16  GRT LightValue LightHighOn    DN=cLightOn
Rung 17  LES LightValue LightHighOff   DN=cLightOff

STATE BITS WITH SEAL-IN (Rungs 18-25)
(Run OR Self) AND /Stop -> State

Rung 18  (cTLowOn OR TempLow)     AND /cTLowOff    → (TempLow)
Rung 19  (cTWarmOn OR TempWarm)   AND /cTWarmOff   → (TempWarm)
Rung 20  (cTHighOn OR TempHigh)   AND /cTHighOff   → (TempHigh)
Rung 21  (cTVHighOn OR TempVHigh) AND /cTVHighOff  → (TempVHigh)
Rung 22  (cTCritOn OR TempCrit)   AND /cTCritOff   → (TempCrit)
Rung 23  (cHLowOn OR HumLow)      AND /cHLowOff    → (HumLow)
Rung 24  (cHHighOn OR HumHigh)    AND /cHHighOff   → (HumHigh)
Rung 25  (cLightOn OR LightHigh)  AND /cLightOff   → (LightHigh)

OUTPUTS (Rungs 26-37)

Rung 26  SystRun, TempLow, /TempHigh, /TempCrit          → (Heater)
Rung 27  SystRun, TempHigh                               → (ExhaustFan)
Rung 28  SystRun, (TempHigh OR HumHigh)                  → (CircFan)
Rung 29  SystRun, TempWarm, /WindRain, /SideVentOpenLS, /SideVentClose → (SideVentOpen)
Rung 30  SystRun, /TempWarm, /SideVentClosedLS, /SideVentOpen          → (SideVentClose)
Rung 31  SystRun, TempWarm, /WindRain, /RoofVentOpenLS, /RoofVentClose → (RoofVentOpen)
Rung 32  SystRun, /TempWarm, /RoofVentClosedLS, /RoofVentOpen           → (RoofVentClose)
Rung 33  SystRun, TempVHigh, /HumHigh, /WaterLevelLow    → (CoolPadPump)
Rung 34  SystRun, HumLow, /HumHigh, /WaterLevelLow       → (FogPump)
Rung 35  SystRun, LightHigh, /ShadeExtLS, /ShadeRetract  → (ShadeExtend)
Rung 36  SystRun, /LightHigh, /ShadeRetLS, /ShadeExtend  → (ShadeRetract)
Rung 37  (TempCrit OR WaterLevelLow)                     → (AlarmBuzzer)
