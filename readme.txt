/*
 * Author: Aldescu Marian
 * Course: Information Visualization
 */

Visualization implemented with D3.v6

In order to run the visualization:
- open a terminal in the same directory where this readme is located
- run: python3 -m http.server 8000
- open the path in a browser: http://localhost:8000/viz/subsets_analysis.html


The directories should have the following structure:

├── data
│   ├── missions.tsv
│   ├── places.tsv
│   └── users.tsv
├── vendor
│   └── d3
│       ├── API.md
│       ├── CHANGES.md
│       ├── d3.js
│       ├── d3.min.js
│       ├── LICENSE
│       └── README.md
└── viz
    └── subsets_analysis.html