---
tags:
  - beachten
  - energie
  - speicher
LeistungPeak: 10kW
MeanTag: 5kWh
MeanMonat: 150kWh
MeanJahr: 1800kWh
---


| Typ | Relative Kapazität | Kapazität | Leistung | Effizienz | Kosten | Beschreibung|
|-|-|-|-|-|-|-|
|Glättung|1ms - 10s|`= ceil(10/3600 * number(this.LeistungPeak) * 1000)`Wh|`= this.LeistungPeak`|>=95%|5000 €/kWh|Auffangen von Lastspitzen|
|Kondensator|1m - 10m|`= number(this.LeistungPeak)/10`kWh|`= this.LeistungPeak`|>=95%|5000 €/kWh|Verlust"freie" Zwischenspeicherung|
|Chemisch|6h - 1d|`= number(this.MeanTag)`kWh|`= this.LeistungPeak`|>=90%|1500€/kWh|Ausgeleichen von Tagesschwankungen|
|Beliebig|5d - 15d|`= number(this.MeanMonat)/2`kWh|1kW|>=70%|500€/kWh|Ausgeleichen von Monatsschwankungen|
|Beliebig|1M - 3M|`= (3/12)*number(this.MeanJahr)`kWh|500W|>=50%|100€/kWh|Ausgeleichen von Jahresschwankungen|

## Parameter
- Typ: Art des Speichers.
- Relative Kapazität: Wie lange soll der Speicher verwendet werden können, bevor er erschöpft ist?
- Kapazität: maximale Größe des Speichers bei perfekter Effizienz
- Kosten: angestrebtes Ziel Pro Kilowatt.
- Leistung: Wie viel Energie soll umgesetzt werden können (laden/entladen)?
- Schadensausmaß: Wie gefährlich darf ein Fehlerfall werden?
- Schadenswahrscheinlichkeit: Wie oft darf ein Schadensfall im Mittel eintreten?