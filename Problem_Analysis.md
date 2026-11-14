# Problem Analysis and SDG Notes

## The community problem
Flooding is one of the most frequent and dangerous hazards in Sierra Leone, especially in Freetown and the Western Area during the rainy season. Drains overflow, streams rise and water enters homes, often with very little warning.

## Who is affected
- Residents of low-lying and informal settlements (for example Kroo Bay)
- Children, the elderly, market traders and small farmers
- Local councils and disaster officers, who must respond without clear local information

## Why the problem exists
- Unplanned building on floodplains and steep slopes
- Drains blocked by solid waste
- Loss of tree cover on the hills
- Intense seasonal rainfall made worse by climate change
- Weak systems for turning measurements into warnings that ordinary people can understand and act on

## How FloodWatch SL addresses the problem
A trained community monitor enters four facts: community name, rainfall in the last 24 hours (mm), water level (% of drain or river capacity) and whether the area has flooded before. The system validates the entries, classifies the risk as LOW, MODERATE, HIGH or SEVERE, shows a plain-language alert message, saves a record and gives a final summary.

The threshold values in the design (for example 50 mm and 100 mm of rain) are illustrative. They must be calibrated with experts from the Sierra Leone Meteorological Agency and the National Disaster Management Agency before real use.

## Computational thinking
- **Decomposition:** collect data, check data, calculate risk, adjust for history, create message, store record, summarise
- **Pattern recognition:** more rain and a fuller drain or river mean higher risk; areas that flooded before are likely to flood again
- **Abstraction:** soil type, slope and exact map position are left out; only rainfall, water level and flood history are used
- **Algorithm design:** steps are ordered, repeated for every community and tested with sample scenarios

## Sustainable Development Goals
- **SDG 11 (Sustainable Cities and Communities), target 11.5:** reduce deaths and people affected by disasters, including water-related disasters
- **SDG 13 (Climate Action), target 13.1:** strengthen resilience and adaptive capacity to climate-related hazards

## Open source and Digital Public Goods
The project is published under the MIT licence so that anyone can inspect, reuse and improve the flood-warning rules. It could become a Digital Public Good by using an open licence, clear documentation, open data formats (CSV) and community-level data only (no personal details).

## Reference
GFDRR (2017) Sierra Leone: Rapid Damage and Loss Assessment of August 14th, 2017 Landslides and Floods in the Western Area.
