# Databases
My work in this category builds on the previous two categories by enhancing the server component to record temperature data to a time-series database and the browser interface to display a graph of recent temperature readings. While enhancing the artifact, I learned about the [time-series functionality in MongoDB](https://www.mongodb.com/time-series). I have previous experience with traditional collections in MongoDB from this computer science program and in my career, but I had not yet explored the new time-series support. Learning how to use the aggregation functionality to exploit the time-series storage format was challenging, but interesting. I also explored the use of the [Plotly JavaScript library](https://plotly.com/javascript/) for presenting graphs in the browser which I had not used previously. It was challenging to find an optimal data format for returning historical temperature data in a format directly suitable for the graphing library.

Building on the MongoDB database I used for the initial server implementation, I created a new collection using the time-series support found in the latest MongoDB release. This feature optimizes the collection for the storage of timed measurements and is well-suited to capturing temperature measurements in real time. The time-series collection works in conjunction with the aggregation facilities in MongoDB to allow for efficient reporting of historical data. With the new collection in place, I updated the server to record temperature readings whenever a change is sent from the thermostat and to request an update from the thermostat whenever a minute goes by without a change. Then I updated the web interface to show a graph of the recent temperature changes by dynamically querying the database for the average temperature recorded for 15-minute periods.

The complete source code for the server component including this enhancment is [available here](https://github.com/erik-mattheis-snhu/thermostat-server).

<hr />
<p align="center">
<span style="font-size: 80%; float: left; padding-bottom: 1em;">« <a href="../algorithms-and-data-structure">Algorithms and Data Structure</a> &nbsp;</span>
</p>
