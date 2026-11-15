# Algorithm: FloodWatch SL

## Input, Processing, Output
| Input | Processing | Output |
|---|---|---|
| Community name | Validate every input | Risk label |
| Rainfall in last 24 hours (mm) | Calculate base risk score | Alert message |
| Water level (% of capacity) | Adjust score for flood history | Saved record |
| Flood-prone area? (Y/N) | Convert score to label, build message, save record, update counters | Final summary |

## Constants
| Constant | Value | Meaning |
|---|---|---|
| RAIN_MODERATE | 50 | Rainfall (mm in 24 hours) at which risk starts to rise |
| RAIN_HEAVY | 100 | Rainfall counted as heavy |
| LEVEL_ELEVATED | 70 | Water level (% of capacity) counted as elevated |
| LEVEL_CRITICAL | 90 | Water level counted as critical |
| MAX_RAIN | 500 | Largest rainfall value accepted |
| MAX_LEVEL | 150 | Largest water-level value accepted |

## Variables
| Variable | Data type | Purpose |
|---|---|---|
| communityName | String | Community being assessed |
| rainfall | Real | Rainfall in last 24 hours (mm) |
| waterLevel | Real | Water level (% of capacity) |
| isFloodProne | Boolean | TRUE if the area has flooded before |
| baseScore, finalScore | Integer | Risk score 0 (LOW) to 3 (SEVERE) |
| riskLabel, message | String | Text shown to the user |
| riskCounts | Array of 4 Integers | Communities at each risk level |
| totalCount | Integer | Total communities assessed |

## Step-by-step algorithm
1. Start the system. Set totalCount to 0 and all four risk counters to 0.
2. Ask for the community name. If the name is DONE, go to step 14.
3. Ask for the rainfall in the last 24 hours. Check that it is a number from 0 to 500. If not, show an error and ask again.
4. Ask for the water level (% of capacity). Check that it is a number from 0 to 150. If not, show an error and ask again.
5. Ask whether the area is flood-prone (Y or N). Repeat until the answer is Y or N.
6. Calculate baseScore: 3 (SEVERE) if rainfall is at least 100 AND water level is at least 90; otherwise 2 (HIGH) if rainfall is at least 100 OR water level is at least 90; otherwise 1 (MODERATE) if rainfall is at least 50 OR water level is at least 70; otherwise 0 (LOW).
7. If the area is flood-prone AND baseScore is less than 3, add 1 to get finalScore. Otherwise finalScore equals baseScore.
8. Convert finalScore to a risk label (LOW, MODERATE, HIGH or SEVERE).
9. Build the alert message that matches finalScore.
10. Display the risk label and the alert message.
11. Save the record (date and time, community, rainfall, water level, label).
12. Add 1 to the counter for finalScore and add 1 to totalCount.
13. Go back to step 2.
14. Display the summary: total assessed, the count at each level and a priority notice if any community is SEVERE.
15. Stop.
