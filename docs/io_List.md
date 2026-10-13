# Greenhouse PLC - Full Documentation

## 1. Digital Inputs (I)

| Address | Tag | الوصف |
| :--- | :--- | :--- |
| I:0/0 | AutoMode | مفتاح الوضع الأوتوماتيكي |
| I:0/1 | EmerStop | مفتاح الطوارئ |
| I:0/2 | WaterLevelLow | حساس انخفاض منسوب المياه |
| I:0/3 | WindRain | حساس الرياح/المطر |
| I:0/4 | SideVentOpenLS | نهاية شوط الفتحة الجانبية مفتوحة |
| I:0/5 | SideVentClosedLS | نهاية شوط الفتحة الجانبية مقفولة |
| I:0/6 | RoofVentOpenLS | نهاية شوط فتحة السقف مفتوحة |
| I:0/7 | RoofVentClosedLS | نهاية شوط فتحة السقف مقفولة |
| I:0/8 | ShadeExtLS | نهاية شوط فرد الشاشة |
| I:0/9 | ShadeRetLS | نهاية شوط لم الشاشة |

## 2. Analog Inputs (AI)

| Address | Tag | الوصف |
| :--- | :--- | :--- |
| AI:0 | TempValue | حساس الحرارة |
| AI:1 | HumValue | حساس الرطوبة |
| AI:2 | LightValue | حساس الإضاءة |

## 3. Digital Outputs (O)

| Address | Tag | الوصف |
| :--- | :--- | :--- |
| O:0/0 | Heater | السخان |
| O:0/1 | CircFan | مروحة التقليب |
| O:0/2 | ExhaustFan | مروحة الطرد |
| O:0/3 | SideVentOpen | موتور فتح الفتحة الجانبية - فتح |
| O:0/4 | SideVentClose | موتور فتح الفتحة الجانبية - قفل |
| O:0/5 | CoolPadPump | طلمبة خلايا التبريد |
| O:0/6 | FogPump | طلمبة الضباب |
| O:0/7 | AlarmBuzzer | جرس الإنذار |
| O:0/8 | RoofVentOpen | موتور فتحة السقف - فتح |
| O:0/9 | RoofVentClose | موتور فتحة السقف - قفل |
| O:0/10 | ShadeExtend | موتور ستارة التظليل - فرد |
| O:0/11 | ShadeRetract | موتور ستارة التظليل - لم |

## 4. Setpoints (N)

| Address | Tag | القيمة | الوصف |
| :--- | :--- | :--- | :--- |
| N:0 | TempLowOn | 15 | تشغيل السخان |
| N:1 | TempLowOff | 18 | فصل السخان |
| N:2 | TempWarmOn | 26 | فتح التهوية |
| N:3 | TempWarmOff | 24 | قفل التهوية |
| N:4 | TempHighOn | 28 | تشغيل مراوح الطرد |
| N:5 | TempHighOff | 26 | فصل مراوح الطرد |
| N:6 | TempVHighOn | 30 | تشغيل التبريد |
| N:7 | TempVHighOff | 28 | فصل التبريد |
| N:8 | TempCritOn | 38 | إنذار حرارة حرجة |
| N:9 | TempCritOff | 35 | فصل إنذار الحرارة |
| N:10 | HumLowOn | 60 | تشغيل الضباب |
| N:11 | HumLowOff | 68 | فصل الضباب |
| N:12 | HumHighOn | 85 | رطوبة عالية |
| N:13 | HumHighOff | 80 | فصل تهوية الرطوبة |
| N:14 | LightHighOn | 600 | فرد التظليل |
| N:15 | LightHighOff | 500 | لم التظليل |

## 5. Internal Bits - System States (B)

| Address | Tag | الوصف |
| :--- | :--- | :--- |
| B:0/0 | SystRun | حالة تشغيل النظام |
| B:0/1 | TempLow | حالة برودة |
| B:0/2 | TempWarm | حالة دفء - تهوية |
| B:0/3 | TempHigh | حالة حرارة عالية |
| B:0/4 | TempVHigh | حالة حرارة عالية جدا |
| B:0/5 | TempCrit | حالة حرارة حرجة |
| B:0/6 | HumLow | حالة رطوبة منخفضة |
| B:0/7 | HumHigh | حالة رطوبة عالية |
| B:0/8 | LightHigh | حالة إضاءة عالية |

## 6. Internal Bits - Comparison Results (C)

| Address | Tag | مصدر المقارنة |
| :--- | :--- | :--- |
| B:0/9 | cTLowOn | LES TempValue < TempLowOn |
| B:0/10 | cTLowOff | GRT TempValue > TempLowOff |
| B:0/11 | cTWarmOn | GRT TempValue > TempWarmOn |
| B:0/12 | cTWarmOff | LES TempValue < TempWarmOff |
| B:0/13 | cTHighOn | GRT TempValue > TempHighOn |
| B:0/14 | cTHighOff | LES TempValue < TempHighOff |
| B:0/15 | cTVHighOn | GRT TempValue > TempVHighOn |
| B:1/0 | cTVHighOff | LES TempValue < TempVHighOff |
| B:1/1 | cTCritOn | GRT TempValue > TempCritOn |
| B:1/2 | cTCritOff | LES TempValue < TempCritOff |
| B:1/3 | cHLowOn | LES HumValue < HumLowOn |
| B:1/4 | cHLowOff | GRT HumValue > HumLowOff |
| B:1/5 | cHHighOn | GRT HumValue > HumHighOn |
| B:1/6 | cHHighOff | LES HumValue < HumHighOff |
| B:1/7 | cLightOn | GRT LightValue > LightHighOn |
| B:1/8 | cLightOff | LES LightValue < LightHighOff |

---
## 7. Ladder Logic Program (37 Rungs)
Rung 1
┤AutoMode├─┤/EmerStop├────────(SystRun)

--- بلوكات المقارنة (بدون شروط، DN = الـ bit) ---
Rung 2   LES TempValue TempLowOn     DN=cTLowOn
Rung 3   GRT TempValue TempLowOff    DN=cTLowOff
Rung 4   GRT TempValue TempWarmOn    DN=cTWarmOn
Rung 5   LES TempValue TempWarmOff   DN=cTWarmOff
Rung 6   GRT TempValue TempHighOn    DN=cTHighOn
Rung 7   LES TempValue TempHighOff   DN=cTHighOff
Rung 8   GRT TempValue TempVHighOn   DN=cTVHighOn
Rung 9   LES TempValue TempVHighOff  DN=cTVHighOff
Rung 10  GRT TempValue TempCritOn    DN=cTCritOn
Rung 11  LES TempValue TempCritOff   DN=cTCritOff
Rung 12  LES HumValue   HumLowOn     DN=cHLowOn
Rung 13  GRT HumValue   HumLowOff    DN=cHLowOff
Rung 14  GRT HumValue   HumHighOn    DN=cHHighOn
Rung 15  LES HumValue   HumHighOff   DN=cHHighOff
Rung 16  GRT LightValue LightHighOn  DN=cLightOn
Rung 17  LES LightValue LightHighOff DN=cLightOff

--- الحالات (seal-in) : (شرط التشغيل OR نفسها) AND /شرط الفصل ---
Rung 18  (cTLowOn OR TempLow)     AND /cTLowOff    → (TempLow)
Rung 19  (cTWarmOn OR TempWarm)   AND /cTWarmOff   → (TempWarm)
Rung 20  (cTHighOn OR TempHigh)   AND /cTHighOff   → (TempHigh)
Rung 21  (cTVHighOn OR TempVHigh) AND /cTVHighOff  → (TempVHigh)
Rung 22  (cTCritOn OR TempCrit)   AND /cTCritOff   → (TempCrit)
Rung 23  (cHLowOn OR HumLow)      AND /cHLowOff    → (HumLow)
Rung 24  (cHHighOn OR HumHigh)    AND /cHHighOff   → (HumHigh)
Rung 25  (cLightOn OR LightHigh)  AND /cLightOff   → (LightHigh)

--- المخرجات ---
Rung 26  SystRun, TempLow, /TempHigh, /TempCrit          → (Heater)
Rung 27  SystRun, TempHigh                               → (ExhaustFan)
Rung 28  SystRun, (TempHigh OR HumHigh)                  → (CircFan)
Rung 29  SystRun, TempWarm, /WindRain, /SideVentOpenLS,
         /SideVentClose                                  → (SideVentOpen)
Rung 30  SystRun, /TempWarm, /SideVentClosedLS,
         /SideVentOpen                                   → (SideVentClose)
Rung 31  SystRun, TempWarm, /WindRain, /RoofVentOpenLS,
         /RoofVentClose                                  → (RoofVentOpen)
Rung 32  SystRun, /TempWarm, /RoofVentClosedLS,
         /RoofVentOpen                                   → (RoofVentClose)
Rung 33  SystRun, TempVHigh, /HumHigh, /WaterLevelLow    → (CoolPadPump)
Rung 34  SystRun, HumLow, /HumHigh, /WaterLevelLow       → (FogPump)
Rung 35  SystRun, LightHigh, /ShadeExtLS, /ShadeRetract  → (ShadeExtend)
Rung 36  SystRun, /LightHigh, /ShadeRetLS, /ShadeExtend  → (ShadeRetract)
Rung 37  (TempCrit OR WaterLevelLow)                     → (AlarmBuzzer)
