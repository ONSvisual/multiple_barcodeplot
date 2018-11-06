# Barcode plot
Multiple barcode plots with dropdown ([demo](https://onsvisual.github.io/multiple_barcodeplot/barcode/index.html))

![Barcode plot](https://user-images.githubusercontent.com/2945099/48061368-95e65d80-e1b6-11e8-9492-0b6bf93ca9f6.png)

The files for each chart should be of the following format:

![file structure](https://user-images.githubusercontent.com/2945099/48061578-5b30f500-e1b7-11e8-9178-b56837943395.png)

### Data file
The data should be in the following format

| AREACD    | AREANM               | CareHomeBeds | CareJobs |
| --------- | -------------------- | ------------ | -------- |
| E06000001 | Hartlepool           | 1.12         | 9684     |
| E06000002 | Middlesbrough        | 13.83        | 9159     |
| E06000003 | Redcar and Cleveland | 10.91        | 10279    |
| E06000004 | Stockton-on-Tees     | 9.56         | 7065     |
| ... | ... | ... | ... |
| England | England | 7.81 |5046|



The `AREACD` and `AREANM` columns are used to create identifiers in the data and generate a dropdown. Other columns are used to create barcodes.

### Config

Open the `config.json` file with your favourite text editor. 

#### essentials

These contain the main variables which the chart will need and will possibly need changing for each new chart.

```"graphic_data_url": "data.csv"```points to the file that has the data. 



```  
"sourceText":["The spatial distribution of industries in Great Britain: 2015"],
"sourceURL":["https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/employmentandemployeetypes/articles/thespatialdistributionofindustriesingreatbritain/2015"],
```
Sets the text and link for the source.



```"highlight":"England"```sets the line to highlight, e.g. England average.


```
"chartTitles":[
"Care home beds",
"Adult social care jobs",
"Adult home care received",
"Adult day care attended",
"Unpaid care",
"Satistfaction with care"
]
```
Sets the titles for each barcode

```
"chartUnits":[
": % for aged 75 and over",
": per 100,000 population aged 18+",
": per 100,000 population aged 18+",
": per 100,000 population aged 18+",
": number of unpaid care providers?",
": % extremely or very satisfied"
],
```
Sets the unit for each barcode

```
"dataFormats":[".1f",",.0f",",.0f",".0f",",.0f",".3p"],
```
Sets how d3 should handle the number formats for each barcode.

```
"height_sm_md_lg" : [70,70,70],
```
Sets the height for each barcode at different screen sizes. The first number corresponds to small screens, second to medium and last one to large.

```
"xAxisScales":[
[0,30],
[1000,34000],
[280,3000],
[0,1150],
[7000,22000],
[0.45,1.06]
]
```
Sets the x-axis for each barcode

#### optional
```
"margin_sm": [20, 0, 20, 0],
"margin_md": [20, 0, 20, 0],
"margin_lg": [20, 0, 20, 0],
```
Sets the margins for each barcode at different screen sizes

```"mobileBreakpoint" : 550```
Sets the width for the small breakpoint