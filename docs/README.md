# True Energy Aps | Developer 

Quick links: 
* [This page](https://trueenergyaps.github.io/api/)
* [True Energy Web Site](https://trueenergy.dk)
* [True Energy Swagger Api Description](https://trueenergyapi.azurewebsites.net/swagger/index.html)

## Introduction
The True Energy Developer API currently offers access to electricity prices in Denmark incl. estimated Co2 emission. 

It's easy to get started and the API supports OData queries! Giving you a very flexible api with options to search, filter and more directly in the api request.

**Wan't to learn more about OData**
(Odata)[https://www.odata.org]

## Getting started

It's really easy to get started, head over to the [swagger page](https://trueenergyapi.azurewebsites.net/swagger/index.html) and click the **authorize** button and create or login with your exsiting account. 

When authorized you can query the API using Odata. 

## Understanding the data
The electricity in Denmark is spil into 2 seperat grids (area's) namely: DK1 (Jylland & Fyn) and DK2 (Sjælland)
When quering you can filter by area to the data you need. 

``` json
ElectricityPriceModel
{
  Area	string
  Hour	string($date-time)
  HourEnd	string($date-time)
  Price	number($double)
  Co2	number($double)
  DatePrice	number($double)
}
```

## Samples

A few quick odata query samples, to get you started:

**Get all electricity prices - orderby desc**
```
https://trueenergyapi.azurewebsites.net/api/v1/ElectricityPrices?$select=Area&$orderby=hour desc
```

**Get all electricity prices - when electricity is free in DK2 area**
```
https://trueenergyapi.azurewebsites.net/api/v1/ElectricityPrices?$filter=(area eq 'DK2') and (price lt 0 or price eq 0)&$orderby=hour desc
```

[edit page](https://github.com/TrueEnergyApS/developer/edit/master/docs/README.md)
