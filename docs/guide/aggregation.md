# Data Aggregations

[[toc]]

## Aggregations

In this guide we display the measurements that are recorded and how the measurements are aggregated. For both the daily and hourly data endpoints we describe which values are aggregated as a mean, maximum, or minimum recorded value over the specified time range

The aggregations referred to here are available via the [data](https://api.arable.cloud/api/v2/doc#operation/get_data) endpoint

----

### Daily

| Metric                                 | Variable Name            | Aggregation Function                                                            |
|----------------------------------------|--------------------------|---------------------------------------------------------------------------------|
| Air Temp                               | meant                    | mean                                                                            |
| Air Temp                               | maxt                     | max                                                                             |
| Air Temp                               | mint                     | min                                                                             |
| Air Temp                               | maxt_time                | time of maximum temperature in the day                                          |
| Air Temp                               | mint_time                | time of minimum temperature in the day                                          |
| Relative Humidity                      | mean_rh                  | mean                                                                            |
| Relative Humidity                      | max_rh                   | max                                                                             |
| Relative Humidity                      | min_rh                   | min                                                                             |
| Relative Humidity                      | rh_at_maxt               | rh value at time of maximum air temperature                                     |
| Relative Humidity                      | rh_at_mint               | rh value at time of minimum air temperature                                     |
| Sea Level Pressure                     | slp                      | mean                                                                            |
| Dew Temp                               | tdew                     | mean                                                                            |
| Dew Temp                               | max_tdew                 | max                                                                             |
| Dew Temp                               | tdew_at_mint             | tdew value at time of minimum air temperature                                   |
| Vapor Pressure                         | ea                       | mean                                                                            |
| Vapor Pressure Deficit                 | vpd                      | mean                                                                            |
| Evapotranspiration                     | et                       | sum                                                                             |
| Crop Evapotranspiration                | etc                      | sum                                                                             |
| Shortwave Downwelling                  | swdw                     | `sum(total seconds * swdw)/1e6`                                                 |
| Daily Light Integral                   | dli                      | `sum(total seconds * pardw)/1e6`                                                |
| Sunshine Duration                      | sunshine_duration        | sum of swdw above 120 / 12                                                      |
| Temperature Below (canopy/ground)      | mean_tbelow              | mean                                                                            |
| Temperature Below (canopy/ground)      | lfairdelta               | mean difference between air temperature and below temperature around solar noon |
| Normalized Difference Vegetative Index | ndvi                     | value of NDVI +/- 1 hour of solar noon                                          |
| Chlorophyll Index                      | cl                       | value of CI +/- 1 hour of solar noon                                            |
| Wind Speed                             | wind_speed               | mean                                                                            |
| Wind Speed                             | wind_speed_max           | max                                                                             |
| Wind Speed                             | wind_speed_min           | min                                                                             |
| Wind Direction                         | wind_direction           | mean                                                                            |
| Wind Heading                           | wind_heading             | mean                                                                            |
| Precipitation                          | precip                   | sum                                                                             |
| Precipitation Hours                    | precip_hours             | sum                                                                             |
| Crop Water Demand                      | crop_water_demand        | `precip - etc`                                                                  |
| Flow Rate                              | flow_rate                | mean                                                                            |
| Heat Stress                            | heat_stress              | `len(hot_daytime_hours) / len(daytime_hours)`                                   |
| Heat Stress Hours                      | heat_stress_hours        | `len(hot_daytime_hours)`                                                        |
| Irrigation Volume                      | irrigation_volume        | irrigation volume per day in cubic meters (m3)"                                 |
| Irrigation Runtime Hours               | irrigation_runtime_hours | no. of houts irrigation occurred in that day                                    |
| Last Irrigation Time                   | last_irrigation_time     | timestamp indicating last irrigation time of the day                            |
| Crop Coefficient                       | kc                       | factor to calculate ETc from ET                                                 |
| Leaf Wetness                           | lfw                      | sum                                                                             |
| Quality                                | low_quality              | true for low data quality                                                       |
| Sample Percentage                      | sample_pct               | count                                                                           |


### Hourly / Local Hourly

| Metric                            | Variable Name  | Aggregation Function                        |
|-----------------------------------|----------------|---------------------------------------------|
| Air Temp                          | tair           | mean                                        |
| Air Temp                          | maxt           | max                                         |
| Air Temp                          | mint           | min                                         |
| Temperature Above                 | tabove         | mean                                        |
| Temperature Below (canopy/ground) | tbelow         | mean                                        |
| Sea Level Pressure                | slp            | mean                                        |
| Relative Humidity                 | rh             | mean                                        |
| Relative Humidity                 | max_rh         | max                                         |
| Relative Humidity                 | min_rh         | min                                         |
| Relative Humidity                 | rh_at_maxt     | rh value at time of maximum air temperature |
| Relative Humidity                 | rh_at_mint     | rh value at time of minimum air temperature |
| Dew Temp                          | tdew           | mean                                        |
| Dew Temp                          | max_tdew       | max                                         |
| Pressure                          | p              | mean                                        |
| Vapor Pressure                    | ea             | mean                                        |
| Vapor Pressure Deficit            | vpd            | mean                                        |
| Evapotranspiration                | et             | sum                                         |
| Crop Evapotranspiration           | etc            | sum                                         |
| Precipitation Rate                | prate          | sum                                         |
| Shortwave Downwelling             | swdw           | mean                                        |
| Shortwave Upwelling               | swuw           | mean                                        |
| Longwave Downwelling              | lwdw           | mean                                        |
| Longwave Upwelling                | lwuw           | mean                                        |
| PAR Downwelling                   | pardw          | mean                                        |
| PAR Upwelling                     | paruw          | mean                                        |
| Spectrometer Band Downwelling     | b1dw           | mean                                        |
| Spectrometer Band Upwelling       | b1uw           | mean                                        |
| Spectrometer Band Downwelling     | b2dw           | mean                                        |
| Spectrometer Band Upwelling       | b2uw           | mean                                        |
| Spectrometer Band Downwelling     | b3dw           | mean                                        |
| Spectrometer Band Upwelling       | b3uw           | mean                                        |
| Spectrometer Band Downwelling     | b4dw           | mean                                        |
| Spectrometer Band Upwelling       | b4uw           | mean                                        |
| Spectrometer Band Downwelling     | b5dw           | mean                                        |
| Spectrometer Band Upwelling       | b5uw           | mean                                        |
| Spectrometer Band Downwelling     | b6dw           | mean                                        |
| Spectrometer Band Upwelling       | b6uw           | mean                                        |
| Spectrometer Band Downwelling     | b7dw           | mean                                        |
| Spectrometer Band Upwelling       | b7uw           | mean                                        |
| Leaf Wetness                      | lfw            | sum                                         |
| Quality                           | low_quality    | true for low data quality                   |
| Sample Percentage                 | sample_pct     | count                                       |
| Wind Speed                        | wind_speed     | mean                                        |
| Wind Speed                        | wind_speed_max | max                                         |
| Wind Speed                        | wind_speed_min | min                                         |
| Wind Direction                    | wind_direction | mean                                        |
| Wind Heading                      | wind_heading   | mean                                        |


### Sentek Daily / Sentek Hourly


| Metric      | Variable Name    | Aggregation Function |
|-------------|------------------|----------------------|
| Moisture    | moisture_0_max   | max                  |
| Moisture    | moisture_0_mean  | mean                 |
| Moisture    | moisture_0_min   | min                  |
| Moisture    | moisture_1_max   | max                  |
| Moisture    | moisture_1_mean  | mean                 |
| Moisture    | moisture_1_min   | min                  |
| Moisture    | moisture_2_max   | max                  |
| Moisture    | moisture_2_mean  | mean                 |
| Moisture    | moisture_2_min   | min                  |
| Moisture    | moisture_3_max   | max                  |
| Moisture    | moisture_3_mean  | mean                 |
| Moisture    | moisture_3_min   | min                  |
| Moisture    | moisture_4_max   | max                  |
| Moisture    | moisture_4_mean  | mean                 |
| Moisture    | moisture_4_min   | min                  |
| Moisture    | moisture_5_max   | max                  |
| Moisture    | moisture_5_mean  | mean                 |
| Moisture    | moisture_5_min   | min                  |
| Moisture    | moisture_6_max   | max                  |
| Moisture    | moisture_6_mean  | mean                 |
| Moisture    | moisture_6_min   | min                  |
| Moisture    | moisture_7_max   | max                  |
| Moisture    | moisture_7_mean  | mean                 |
| Moisture    | moisture_7_min   | min                  |
| Moisture    | moisture_8_max   | max                  |
| Moisture    | moisture_8_mean  | mean                 |
| Moisture    | moisture_8_min   | min                  |
| Moisture    | moisture_9_max   | max                  |
| Moisture    | moisture_9_mean  | mean                 |
| Moisture    | moisture_9_min   | min                  |
| Moisture    | moisture_10_max  | max                  |
| Moisture    | moisture_10_mean | mean                 |
| Moisture    | moisture_10_min  | min                  |
| Moisture    | moisture_11_max  | max                  |
| Moisture    | moisture_11_mean | mean                 |
| Moisture    | moisture_11_min  | min                  |
| Moisture    | moisture_12_max  | max                  |
| Moisture    | moisture_12_mean | mean                 |
| Moisture    | moisture_12_min  | min                  |
| Moisture    | moisture_13_max  | max                  |
| Moisture    | moisture_13_mean | mean                 |
| Moisture    | moisture_13_min  | min                  |
| Moisture    | moisture_14_max  | max                  |
| Moisture    | moisture_14_mean | mean                 |
| Moisture    | moisture_14_min  | min                  |
| Salinity    | salinity_0_max   | max                  |
| Salinity    | salinity_0_mean  | mean                 |
| Salinity    | salinity_0_min   | min                  |
| Salinity    | salinity_1_max   | max                  |
| Salinity    | salinity_1_mean  | mean                 |
| Salinity    | salinity_1_min   | min                  |
| Salinity    | salinity_2_max   | max                  |
| Salinity    | salinity_2_mean  | mean                 |
| Salinity    | salinity_2_min   | min                  |
| Salinity    | salinity_3_max   | max                  |
| Salinity    | salinity_3_mean  | mean                 |
| Salinity    | salinity_3_min   | min                  |
| Salinity    | salinity_4_max   | max                  |
| Salinity    | salinity_4_mean  | mean                 |
| Salinity    | salinity_4_min   | min                  |
| Salinity    | salinity_5_max   | max                  |
| Salinity    | salinity_5_mean  | mean                 |
| Salinity    | salinity_5_min   | min                  |
| Salinity    | salinity_6_max   | max                  |
| Salinity    | salinity_6_mean  | mean                 |
| Salinity    | salinity_6_min   | min                  |
| Salinity    | salinity_7_max   | max                  |
| Salinity    | salinity_7_mean  | mean                 |
| Salinity    | salinity_7_min   | min                  |
| Salinity    | salinity_8_max   | max                  |
| Salinity    | salinity_8_mean  | mean                 |
| Salinity    | salinity_8_min   | min                  |
| Salinity    | salinity_9_max   | max                  |
| Salinity    | salinity_9_mean  | mean                 |
| Salinity    | salinity_9_min   | min                  |
| Salinity    | salinity_10_max  | max                  |
| Salinity    | salinity_10_mean | mean                 |
| Salinity    | salinity_10_min  | min                  |
| Salinity    | salinity_11_max  | max                  |
| Salinity    | salinity_11_mean | mean                 |
| Salinity    | salinity_11_min  | min                  |
| Salinity    | salinity_12_max  | max                  |
| Salinity    | salinity_12_mean | mean                 |
| Salinity    | salinity_12_min  | min                  |
| Salinity    | salinity_13_max  | max                  |
| Salinity    | salinity_13_mean | mean                 |
| Salinity    | salinity_13_min  | min                  |
| Salinity    | salinity_14_max  | max                  |
| Salinity    | salinity_14_mean | mean                 |
| Salinity    | salinity_14_min  | min                  |
| Temperature | temp_0_max       | max                  |
| Temperature | temp_0_mean      | mean                 |
| Temperature | temp_0_min       | min                  |
| Temperature | temp_1_max       | max                  |
| Temperature | temp_1_mean      | mean                 |
| Temperature | temp_1_min       | min                  |
| Temperature | temp_2_max       | max                  |
| Temperature | temp_2_mean      | mean                 |
| Temperature | temp_2_min       | min                  |
| Temperature | temp_3_max       | max                  |
| Temperature | temp_3_mean      | mean                 |
| Temperature | temp_3_min       | min                  |
| Temperature | temp_4_max       | max                  |
| Temperature | temp_4_mean      | mean                 |
| Temperature | temp_4_min       | min                  |
| Temperature | temp_5_max       | max                  |
| Temperature | temp_5_mean      | mean                 |
| Temperature | temp_5_min       | min                  |
| Temperature | temp_6_max       | max                  |
| Temperature | temp_6_mean      | mean                 |
| Temperature | temp_6_min       | min                  |
| Temperature | temp_7_max       | max                  |
| Temperature | temp_7_mean      | mean                 |
| Temperature | temp_7_min       | min                  |
| Temperature | temp_8_max       | max                  |
| Temperature | temp_8_mean      | mean                 |
| Temperature | temp_8_min       | min                  |
| Temperature | temp_9_max       | max                  |
| Temperature | temp_9_mean      | mean                 |
| Temperature | temp_9_min       | min                  |
| Temperature | temp_10_max      | max                  |
| Temperature | temp_10_mean     | mean                 |
| Temperature | temp_10_min      | min                  |
| Temperature | temp_11_max      | max                  |
| Temperature | temp_11_mean     | mean                 |
| Temperature | temp_11_min      | min                  |
| Temperature | temp_12_max      | max                  |
| Temperature | temp_12_mean     | mean                 |
| Temperature | temp_12_min      | min                  |
| Temperature | temp_13_max      | max                  |
| Temperature | temp_13_mean     | mean                 |
| Temperature | temp_13_min      | min                  |
| Temperature | temp_14_max      | max                  |
| Temperature | temp_14_mean     | mean                 |
| Temperature | temp_14_min      | min                  |


### Irrigation Runtime Hourly / Irrigation Runtime Daily

| Metric    | Variable Name     | Aggregation Function |
|-----------|-------------------|----------------------|
| Duration  | duration_seconds  | sum                  |


### Location Irrigation Forecast Daily

| Metric                  | Variable Name     | Aggregation Function     |
|-------------------------|-------------------|--------------------------|
| Evapotranspiration      | et                | sum                      |
| Crop Evapotranspiration | etc               | sum                      |
| Precipitation           | precip            | sum                      |
| Crop Water Demand       | crop_water_demand | `precip - etc`           |
| Relative Humidity       | rh                | mean                     |
| Air Temp                | maxt              | max                      |
| Air Temp                | mint              | min                      |
| Dew Temp                | tdew              | mean                     |
| Growing Degree Day      | gdd               | `avg(maxt, mint) - 10))` |
| Forecasted Runtime      | fcst_run_time     | sum                      |
