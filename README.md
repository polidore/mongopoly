Mongopoly!
=========

This is for people who like polling.  Polling?  Aren't we supposed to be real time in 2014? Maybe. 

Real time or push is great for data that changes infrequently, and it's almost required for apps that edit the same data from multiple clients. 

I argue that push isn't great in the following situation: 

* Very high frequency updates
* Clients that only display the current state of the data model

Some examples are trading platforms, market data systems, monitoring apps.  These apps want to be reasonably up to date, but they don't want 100 updates per second (or per millisecond!).  

Once you take a real time protocol and start conflating, you're basically just polling, so why have all the complexity? 

## Issues with polling

It's most natural for polling protocols to send snapshots of the entire data model.  Snapshots are expensive for large data models.  

## Clever use of ES6

ES6 has object watches.  This library will use these watches to do fast deltas of objects coming in from MongoDB. I'm not sure how well it will work, but it could be a more efficient way to send the polling results across the wire. 
