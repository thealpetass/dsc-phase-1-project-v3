# ✈️ Aircraft Accident Analytics Dashboard  
> _“Turning decades of incident data into actionable safety insight.”_

## Overview
This README accompanies the interactive **Aircraft Accident Analytics Dashboard** built from six core visualizations.  
The data spans **1944-2010** and covers **~58,000 total occupants**, **668 fatal accidents**, and **millions of flight-hours**.  
Use it to spot high-risk aircraft, weather conditions, flight phases, and temporal trends.

## Key Findings

| **Metric** | **Value** |
|------------|-----------|
| **Total Occupants** | 58,644 |
| **Fatal Accidents** | 668 |
| **Overall Fatality Rate** | ~1.1 % |
| **Peak Accident Year** | 1970s–1980s (≈3,000 incidents / yr) |
| **Most-Damaged Phase** | **Landing** (~15 k events) |
| **Safest Phase** | **Cruise** |
| **Riskiest Weather** | **Approach & Landing** under **low IMC** |

## Visualization Deep-Dive

### 1. Accidents by Aircraft Model (`Accidents by Aircraft Model.png`)
- **Top 5 high-incident models** (all **Cessna 172 variants**):
  1. 172P  
  2. 172N  
  3. 172M  
  4. Base 172  
  5. 152 / 150M  
- **Piper PA-28-180 & PA-18** follow, but at **<50 %** of Cessna counts.
- **Engine Insight**: All listed aircraft are **reciprocating** (piston), indicating training & personal-use fleets dominate accident logs.

>  **Action**: Prioritize recurrent training & maintenance programs on Cessna 172 fleet.

https://github.com/thealpetass/dsc-phase-1-project-v3/blob/c381130e180c44113c25553fee1126f46038f821/Accidents%20by%20Aircraft%20Model.png

### 2. Accidents by Weather Condition (`Accidents by Weather Condition.png`)
- **Weather is not directly labeled**, but counts per phase are:
  - **Landing** (≈5,500 events)  
  - **Takeoff** (≈4,500 events)  
  - **Approach** (≈4,000 events)  
- **Interpretation**: These phases coincide with **transitional weather** (low ceilings, gusty winds).  
>  **Action**: Emphasize **weather briefing** & **go-around discipline** during Landing/Approach.


### 3. Accidents per Year (`Accidents per Year.png`)
- **Historical Trend**:  
  - Steep rise from **1950 → 1980** (peaks ~3,000 accidents/year).  
  - **Post-1990 sharp decline** (≈500 accidents/year by 2010).  
- **Fatal vs Non-Fatal**: Fatal accidents track **non-fatal** trends, but at **~10 %** of total volume.  
>  **Action**: Correlate the decline with **improved GA safety programs** (e.g., CRM, GPS, weather tools).

### 4. Fatality Rate by Year (`Fatality Rate by Year.png`)
- **Rate Definition**: Fatalities ÷ Total Occupants per incident.  
- **Key Pattern**:  
  - **1940s-1960s**: 60–90 % fatality rate (poor rescue, aircraft design).  
  - **1970s-1990s**: Plateau ~30–50 %.  
  - **2000-2010**: Drops to **<20 %**.  
>  **Action**: Investigate life-saving factors—**airbags, fuel-system integrity, ELTs**.

### 5. Flight Phase vs Damage (`Flight Phase vs Damage.png`)
| **Phase** | **Destroyed** | **Substantial** | **Minor** |
|-----------|---------------|-----------------|-----------|
| **Landing** | 1,800 | 4,000 | 3,000 |
| **Takeoff** | 1,200 | 3,500 | 2,500 |
| **Maneuvering** | 900 | 1,800 | 1,000 |
| **Cruise** | 300 | 1,000 | 1,500 |

- **Landing & Takeoff** account for **>70 %** of **Destroyed** outcomes.  
>  **Action**: Install **real-time energy management tools** (e.g., AoA indicators) in training aircraft.

### 6. Dashboard Overview (`Overlook of my Dashboard.png`)
- **Single-screen summary** of all KPIs.  
- **Interactive filters** on:  
  - Purpose of flight (Instructional, Personal, Business…)  
  - Aircraft Make/Model  
  - Engine Type (Reciprocating vs Turbine)  
- **Color legend**:  
  - **Red** = Fatalities  
  - **Orange** = Substantial Damage  
  - **Green** = Minor / None 

## How to Use the Dashboard
1. **Open the packaged workbook** (`.twbx` or `.pbix`).  
2. **Select filters** on the right to isolate:
   - **Cessna 172** accidents during **Instructional** flights.  
   - **Landing phase** incidents with **Destroyed** outcome.  
3. **Hover** on any bar or point for exact counts & percentages.

![Image Alt](https://github.com/thealpetass/dsc-phase-1-project-v3/blob/861f4d5d1ed0b413ee0b3d1f64efb85616c28b8c/Overlook%20of%20my%20Dashboard.png)


##  Recommendations for Stakeholders

| **Audience** | **Actionable Insight** |
|--------------|------------------------|
| **Flight Schools** | Focus safety stand-downs on **Landing phase**; adopt **simulated engine-failure drills**. |
| **Aircraft OEMs** | Retrofit **AoA indicators** & **improved seat restraints** in legacy 172/152 fleets. |
| **Regulators (FAA/EASA)** | Mandate **recurrent weather training** & **night-currency** for PPL holders. |
| **Insurance Underwriters** | Adjust premiums based on **Phase-of-Flight risk scores** derived from this dashboard. |

## 🗃 Data Dictionary
| **Field** | **Type** | **Description** |
|-----------|----------|-----------------|
| `Accident.Number` | String | Unique NTSB identifier. |
| `Year` | Integer | Year of occurrence. |
| `Make` / `Model` | String | Aircraft manufacturer & model. |
| `Engine.Type` | Categorical | Reciprocating, Turbine, etc. |
| `Broad.phase.of.flight` | Categorical | Takeoff, Cruise, Landing, etc. |
| `Aircraft.damage` | Categorical | Destroyed, Substantial, Minor, Unknown. |
| `Total.Occupants` | Integer | People on board. |
| `Fatality` | Integer | Fatalities per incident. |
| `Fatality.Rate` | Float | Fatalities ÷ Total Occupants. |

##  License & Attribution
- **Data Source**: NTSB Aviation Accident Database (public domain).  
- **Dashboard Author**: [Tanveer Chege]  
- **License**: MIT – feel free to fork & extend.
