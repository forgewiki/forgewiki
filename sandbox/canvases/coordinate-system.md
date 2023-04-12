# Forge Canvas Coordinate System
The Forge Canvas in Halo uses a coordinate system to help players accurately position and align objects in their maps. Understanding this coordinate system is essential for creating a cohesive and visually pleasing map.

## Center
The center of the Forge Canvas is located at x: 0, y: 0, z: 1250. This is where the player's camera will be located when editing the map.

## Floor
The floor of the Forge Canvas is located at z: 500.

## Dimensions
The Forge Canvas has dimensions of x: 4000, y: 4000, z: 1500. However, it's important to note that if the terrain is uneven, the intersections will be at z: 500.

## Reflection Probe
The default reflection probe is located at 0,0,1000. It's important to avoid intersecting this point with map geometry, and to consider what is visible from this location, as wherever custom probes are not placed, this reflection will be used.

## Units
Units in the Forge Canvas are measured in feet.

#### Contributors
Captain Punch
Kwatzy