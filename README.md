# tiling-routing-engine

This module creates routes which are optimized for gravel cycling. Uses omsnx with data tiles from OpenSteetMap to find routes (primary and alternative) between 2 given points.

Since all calculation is done real-time, other data (traffic, user feedback, environment conditions) can be easily integrated simply by including it in the weight calculation function. More transportation modes can also be added easily with new weight functions.

## How Does it Work?
- Supporting a wide region poses the challenge of maintaining low route calculation time, as loading the full network into RAM is not scalable.
- My solution involves utilizing small data tiles, each covering an area of 20 $km^2$, which can be dynamically loaded as required.
- By analyzing the origin and destination points of a given query, data tiles can be loaded as needed to process the request.
- This streamlined approach ensures optimal resource utilization even when facing concurrent requests from different regions.

<img width="1400" src="https://github.com/andreytakhtamirov/tiling-routing-engine/assets/70922688/1ee9a395-ad05-4f09-944d-7c1faec589cc">

An example of 8 routes, shown with [Leaflet](https://github.com/Leaflet/Leaflet), along with their surface metrics. Note how there are so many different paths that are better than what Google will give you (at least for gravel cycling)!


## Supported Regions
The area in blue shown below:
![range_1](https://github.com/andreytakhtamirov/tiling-routing-engine/assets/70922688/9db4146e-74a8-44da-bb5d-1ffd4fd29063)
<img width="1136" alt="calgary" src="https://github.com/andreytakhtamirov/tiling-routing-engine/assets/70922688/d0200d81-d4b4-4bd8-b6a0-fdf2cdd79142">
