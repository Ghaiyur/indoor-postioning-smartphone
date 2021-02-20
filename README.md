# Indoor Postioning Smartphone

## Introduction 

Your smartphone goes everywhere with you—whether driving to the grocery store or shopping for holiday gifts. With your permission, apps can use your location to provide contextual information. You might get driving directions, find a store, or receive alerts for nearby promotions. These handy features are enabled by GPS, which requires outdoor exposure for the best accuracy. Yet, there are many times when you’re inside large structures, such as a shopping mall or event center. Accurate indoor positioning, based on public sensors and user permission, allows for a great location-based experience even when you aren’t outside.

Accurate indoor localization has the potential to transform our lives indoors in a similar way that GPS transformed the way people live, work and play outdoors. Despite significant advances in indoor localization technologies over the past two decades, many problems still remain to be solved toward building cost-effective and scalable solutions.

## Data source 

Consists of dense indoor signatures of WiFi, geomagnetic field, iBeacons etc., as well as ground truth (waypoint) (locations) collected from hundreds of buildings in Chinese cities. The data found in path trace files (*.txt) corresponds to an indoor path between position p_1 and p_2 walked by a site-surveyor.

During the walk, an Android smartphone is held flat in front of the surveyors body, and a sensor data recording app is running on the device to collect IMU (accelerometer, gyroscope) and geomagnetic field (magnetometer) readings, as well as WiFi and Bluetooth iBeacon scanning results. A detailed description of the format of trace file is shown, along with other details and processing scripts, at this github link. In addition to raw trace files, floor plan metadata (e.g., raster image, size, GeoJSON) are also included for each floor.

A note on data quality: In the training files, you may find occasionally that a line is missing the ending newline character, causing it to run on to the next line. It is up to you how you want to handle this issue. This issue is not found in the test data.

## Files

- train - training path files, organized by site and floor; each path files contains the data of a single path on a single floor
- test - test path files, organized by site and floor; each path files contains the data of a single path on a single floor, but without the waypoint (x, y) data; the task of this competition is, for a given site-path file, predict the floor and waypoint locations at the timestamps given in the sample_submission.csv file
- metadata - floor metadata folder, organized by site and floor, which includes the following for each floor:
   - floor_image.png
   - floor_info.json
   - geojson_map.json
