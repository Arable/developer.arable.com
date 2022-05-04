# Data Aggregations

[[toc]]

## Aggregations

In this guide we display the measurements that are recorded and how the measurements are aggregated. For both the daily and hourly data endpoints we describe which values are aggregated as a mean, maximum, or minimum recorded value over the specified time range

The aggregations referred to here are available via the [data](https://api.arable.cloud/api/v2/doc#operation/get_data) endpoint

----

### Table: Daily 

| Metric  | Variable Name  | Aggregation Function  |
|---|---|---|
| Air Temp | meant | mean | 
| Air Temp | maxt | max | 
| Air Temp | mint | min | 
| Air Temp | maxt_time | time of maximum temperature in the day |
| Air Temp |  mint_time | time of minimum temperature in the day |
| Relative Humidity| rh_mean | mean | 
| Relative Humidity| rh_max | max |
| Relative Humidity| rh_at_maxt | rh value at time of maximum air temperature | 
| Relative Humidity| rh_at_mint | rh value at time of minimum air temperature |
| Sea Level Pressure | slp | mean
| Dew Temp | tdew | mean |
| Dew Temp | max_tdew | max |
| Dew Temp | tdew_at_mint | tdew value at time of minimum air temperature |
| Vapor Pressure | ea | mean |
| Vapor Pressure Deficit | vpd | mean | 
| Evapotranspiration | et | sum |
| Crop Evapotranspiration | etc | sum |
| Shortwave Downwelling | swdw | `sum(total seconds * swdw)/1e6` |
| Daily Light Integral | dli | `sum(total seconds * pardw)/1e6` |
| Sunshine Duration | sunshine_duration | sum of swdw above 120 / 12 |
| Temperature Below (canopy/ground) | mean_tbelow | mean |
| Temperature Below (canopy/ground) | lfairdelta | mean difference between air temperature and below temperature around solar noon |
| Normalized Difference Vegetative Index | ndvi | value of NDVI +/- 1 hour of solar noon |
| Chlorophyll Index | ci | value of CI +/- 1 hour of solar noon |
| Wind Speed | wind_speed | mean |
| Wind Speed | wind_speed_max | max |
| Wind Direction | wind_direction | mean |
| Precipitation | precip | mean |




### Local Hourly / Hourly
| Metric  | Variable Name  | Aggregation Function  |
|---|---|---|
| Air Temp | tair | mean | 
| Air Temp | maxt | max | 
| Air Temp | mint | min |
| Temperature Below (canopy/ground) | tbelow | mean |
| Sea Level Pressure | slp | mean |
| Relative Humidity| rh | mean | 
| Relative Humidity| min_rh | min |
| Relative Humidity| rh_at_maxt | rh value at time of maximum air temperature |
| Dew Temp | tdew | mean |
| Vapor Pressure | ea | mean |
| Vapor Pressure Deficit | vpd | mean | 
| Evapotranspiration | et | sum |
| Crop Evapotranspiration | etc | sum |
| Shortwave Downwelling | swdw | mean |
| Shortwave Upwelling | swuw | mean |








