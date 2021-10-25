# Fright_transport_data_analysis

Belgian lorries having a Maximum Authorized Mass exceeding 3.5 tonnes must pay a kilometer charge. Every road user who is not exempt from the toll must then install an On-Board Unit (OBU) recording the distance that a lorry travels within Belgium.
On average more than 140,000 trucks are detected per working day on the national roads. Each OBU device sends a message approximately every 30 seconds. Each data record contains an anonymous Identifier (ID resetting every day at 2 a.m. UTC), the Timestamp, the GPS Position (latitude, longitude), the Speed (engine), and the Direction (compass).

The OBU data require a pre-processing step to predict the traffic conditions at network scale since the trucks recorded positions may refer not only to streets but also to areas where trucks perform the daily activity (e.g. loading/unloading goods, stopping at depots’ parking slot).
In this regard, we first retrieved all the necessary streets from OpenStreetMap with Module osmnx. Then, mappping the GPS points on their corresponding road segments to obtain only the data belonging to the streets of interest.
Finally, we performed a resample at different time granularities where, for each segment and time step, we counted the number of trucks present and their average speed.
