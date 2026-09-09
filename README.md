# Youth Unemployment | ILO 2026 Report

An exploration of youth unemployment using **2025 estimates published by the International Labour Organization (ILO) in August 2026**, with an Excel dataset for a Power BI visualization.

The project focuses on the challenges young people face when entering the labour market. **2026 in the repository name refers to the report's publication year, not the year measured by the dataset.**

## Project status

The dataset and documentation are available. The Power BI report and chart will be created and added by the repository owner later.

## Data snapshot

All rates below refer to people aged **15–24 in 2025**, measured as a share of the youth labour force.

| Region | Youth unemployment rate |
| --- | ---: |
| World | 12.4% |
| Northern America | 9.8% |
| Northern, Southern and Western Europe | 15.0% |

The ILO also reports approximately **67 million unemployed young people worldwide** in 2025. These figures come from the [ILO news release published on 11 August 2026](https://www.ilo.org/resource/news/youth-unemployment-rises-young-people-face-harder-road-decent-work).

## Dataset

Download [youth-unemployment.xlsx](data/youth-unemployment.xlsx). The workbook contains the named Excel table **`YouthUnemployment`** on the `Data` worksheet. Source notes sit outside that table.

| Field | Data type | Meaning |
| --- | --- | --- |
| `Region` | Text | World total or selected geographic region |
| `Year` | Whole number | Reference year: 2025 |
| `AgeGroup` | Text | Age range: 15–24 |
| `UnemploymentRate` | Decimal number | Rate stored as a fraction: `0.124` represents `12.4%` |
| `UnemployedPeople` | Whole number, nullable | Rounded world count: `67000000`; regional counts are unavailable in the cited release |

The workbook is a manually transcribed, three-row extract from the ILO release, not a complete ILO database export. Blank counts mean unavailable, not zero.

## Build the chart in Power BI

1. Open Power BI Desktop and connect to the Excel workbook.
2. Select the named table `YouthUnemployment`, rather than the entire worksheet, to exclude the source notes.
3. Check the column types against the data dictionary above. Format `UnemploymentRate` as a percentage with one decimal place.
4. Create a horizontal bar chart with `Region` as the category and `UnemploymentRate` as the value. With one row per region, `Max` returns the supplied rate without adding rates together.
5. Start the value axis at zero and show data labels. State **2025 estimates, ages 15–24** in the title or subtitle.
6. Optionally add a card for `UnemployedPeople`, filtered to `Region = World`, to display approximately 67 million.

For connection instructions, see [Microsoft's documentation on connecting to Excel in Power BI Desktop](https://learn.microsoft.com/en-us/power-bi/connect-data/desktop-connect-excel).

Suggested chart title: **Youth unemployment: a difficult first step**.

## Methodology and limitations

- The unemployment rate uses the youth labour force as its denominator, not all people aged 15–24.
- The world total overlaps the regional observations. Do not add the world and regional counts or sum their unemployment rates.
- The European observation covers Northern, Southern and Western Europe. It is not an EU-only or all-Europe figure.
- The dataset compares selected regions for one year. It cannot show a time trend or establish the causes of unemployment.
- Youth unemployment does not directly measure employers' experience requirements or the outcomes of all first-time job applicants.
- The source contains rounded estimates. The workbook has no automatic refresh connection.

## Sources

- [ILO: Youth unemployment rises as young people face a harder road to decent work](https://www.ilo.org/resource/news/youth-unemployment-rises-young-people-face-harder-road-decent-work) — 11 August 2026; the direct source for all values in this dataset.
- [ILO: Global Employment Trends for Youth 2026: Back to the future](https://www.ilo.org/publications/major-publications/global-employment-trends-youth-2026) — the accompanying report and broader analysis.
- [ILOSTAT](https://ilostat.ilo.org/) — official labour statistics portal for further research.

## Repository contents

```text
README.md
LICENSE
data/
  youth-unemployment.xlsx
```

## License and attribution

This repository includes an [MIT License](LICENSE). ILO source material remains subject to its own applicable terms. Cite the ILO report when using or sharing the data. This is an independent project and is not affiliated with or endorsed by the ILO.
