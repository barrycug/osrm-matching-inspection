# Matching inspection

These scripts can be used to inspect matchings generated by the [map matching](https://github.com/Project-OSRM/osrm-backend/tree/feature/matching) plugin for OSRM.

## Installation

Run:
    npm install

## Starting the frontend

Assuming your GPX traces are contained in a folder ```data``` in the current repository root:

Locally run:
	node server.js

This will start a http server that listens on ```http://127.0.0.1:8337```.

If you open this in your browser you will see something similar to this:

![](http://i.imgur.com/XvMjiVC.png)

Which shows an interactive trellis diagram of the matching. Select a state pair to view the transition probabilities
and Viterbi values.

You can use the left and right arrow key to cycle through the GPX traces.

## Classifying

Opening ```http://127.0.0.1:8337/classify.html``` will display a minimal interface for easy classification.
Pressing 0 will classify as ```unknown```, 1 as ```valid``` and ```2``` as invalid.
The labels will be saved in ```labels.json``` which can be used by ```test_classification.js``` to verify the classifier
implemented inside the OSRM plugin or by ```save_classified_traces.py``` in [the matching tools](https://github.com/mapbox/osrm-match-gpx-tools)
to derive better classification values.