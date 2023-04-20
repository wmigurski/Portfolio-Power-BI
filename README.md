# Portfolio project in Power BI - 


[Download PDF Dashboard](https://github.com/wmigurski/Portfolio-Power-BI/files/11286899/Portfolio.Wojtek.Migurski.pdf)

Also PBIX project available in this repository.


Data source: https://data.mendeley.com/datasets/8gx2fvg2k6/5  

## Description

My first portfolio project in Power BI. The goal was to create representative dashboards presenting key findings of exploratory analysis of the dataset. 

Data table consists of 52 columns.  
I created a Measure for OnTime% with the following code:

```
OnTimePercentage = 
VAR TotalShipments =
    CALCULATE(
        DISTINCTCOUNT(Orders[Order Id]),
        Orders[Delivery Status] <> "Shipping canceled"
    )
VAR OnTimeShipments =
    CALCULATE(
        DISTINCTCOUNT(Orders[Order Id]),
        Orders[Delivery Status] IN { "Advance shipping", "Shipping on time" },
        Orders[Delivery Status] <> "Shipping canceled"
    )
RETURN DIVIDE(OnTimeShipments, TotalShipments, 0)
```



