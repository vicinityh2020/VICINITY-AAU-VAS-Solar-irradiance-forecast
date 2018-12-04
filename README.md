# VICINITY-AAU-VAS-Solar-irradiance-forecast
This documentation describes the adapter of AAU VAS - Solar irradiance forecast.

# Infrastructure overview

Provide short-term prediction and reporting of solar irradiance for residences and utility who have PV panels to enhance the energy management system capability.
Adapter serves as the interface between VICINITY and LabVIEW enabling to use all required interaction patterns.

![Image text](https://github.com/YajuanGuan/pics/blob/master/SolarIrradianceForecast.png)

# Configuration and deployment

Adapter runs on Python 3.6.

# Adapter changelog by version
Adapter releases are as aau_adapter_x.y.z.py

## 1.0.0
Start version, it works with agent-service-full-0.6.3.jar. The VAS publishes an event with solar irradiance forecast in 15 mins.

# Functionality and API
## User can read the power generation of PV. 
### Endpoint:
            GET : /remote/objects/{oid}/properties/{pid}
### Return:
After executing GET method, a response can be received, for instance:  
properties/PV_ActivePower:
{  
    "value": "1",  
    "time": "2018-11-10 11:30:29"  
}

## Publish an event to the subscribers. 
### Endpoint:
            PUT : /remote/objects/{oid}/events/{eid}
Publish the with solar irradiance forecast for next 15 mins. 
### Return:
After subscribing the VAS successfully, the subscriber receives a response for instance:  
{  
    "value": "843",  
    "time": "2018-11-10 11:30:29"  
}
