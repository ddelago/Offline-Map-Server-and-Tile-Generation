# Offline-Map-Server-and-Tile-Generation
![alt text](https://github.com/ddelago/Offline-Map-Server-and-Tile-Generation/blob/master/map.png)
## Displaying the map
- The map page is static and will be rendered using the saved map tiles.
- The tile data is located in `map_generation/map_server/tiles`.
- The map icons are located in `map_generation/map_server/images`.

## Generating Map Tiles
1. To generate a new set of map tiles, first get a set of long/lat points that represents a bounding box. (2 pairs of points)
    - [Using this website will be helpful.](http://tools.geofabrik.de/calc/#type=geofabrik_standard&bbox=-97.151475,32.709637,-97.062211,32.749782&tab=1&proj=EPSG:4326&places=2)
2. Have Visual Studio installed. 
3. Open the `map_generation/GenerateTiles/GenerateTilesProject.sln` file in Visual Studio.
4. Update the coordinates you would like in the `Main` function of `GenerateTiles.cs` as well as the zoom levels you want.
5. Run the project in Visual Studio. This will create a folder called `tile-urls` with the urls that will be used to fetch map tiles from the osm server.
6. Run the `request_tiles.py` program from the `GenerateTiles` directory.
7. This will fetch the map tiles using the urls and create the appropriate map tile folder structure in `map_generation/mapServer/tiles` 
    - This process may take a very long time depending on your coordinates and the zoom levels that you requested.
8. Once all tiles have been downloaded. You can open the `index.html` file in a browser and view your offline map!
    - You can also embed this static website into other websites such as a dashboard.
9. To customize the usage of your map, such as feeding it coordinates to track, you can use the leaflet library included in `mapServer` to do so.
    - [More about leaflet here.](https://leafletjs.com/)
