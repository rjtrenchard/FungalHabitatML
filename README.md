# FungalHabitatML

#### Author: 
R.J. Trenchard

#### Date:
Nov 18 2024

#### Version:
1.0

#### Description:
A mushroom edibility predictor

#### Setup:
Have Jupyter installed with Python 3.13.0. A virtual environment is recommended.

#### Instructions:
It only needs to be run, and requires an internet connection.
The final slide will start an API server at port 3000.

#### Paths:
`/` - base path, gives an overview of places you can go
`/rf` - returns basic stats on the random forest model
`/dt` - returns basic stats on the decision tree model
`/logistic` - returns basic stats on the logistic regression model

Sending the model paths a POST request with a JSON body will attempt to perform a prediction on edibility
The format for this JSON is:

    {
        'cap-diameter': 'metric value, cm', 
        'cap-shape': 'bell=b, conical=c, convex=x, flat=f',
        'cap-surface': 'fibrous=i, grooves=g, scaly=y, smooth=s,shiny=h, leathery=l, silky=k, sticky=t,wrinkled=w, fleshy=e', 
        'cap-color': 'brown=n, buff=b, gray=g, green=r, pink=p, purple=u, red=e, white=w, yellow=y, blue=l, orange=o, black=k', 
        'does-bruise-or-bleed': 't/f', 
        'gill-attachment': 'adnate=a, adnexed=x, decurrent=d, free=e, sinuate=s, pores=p, none=f',
        'gill-spacing': 'close=c, distant=d, none=f', 
        'gill-color': 'see cap-color + none=f',
        'stem-surface': 'see cap-surface + none=f',
        'stem-height': 'metric, cm', 
        'stem-width': 'metric, cm', 
        'stem-root': 'bulbous=b, swollen=s, club=c, cup=u, equal=e, rhizomorphs=z, rooted=r',
        'stem-color': 'see cap-color + none=f',
        'veil-type': 'partial=p, universal=u',
        "veil-color": "see cap-color + none=f",
        'has-ring': 't/f',
        'ring-type': 'cobwebby=c, evanescent=e, flaring=r, grooved=g, large=l, pendant=p, sheathing=s, zone=z, scaly=y, movable=m, none=f',
        'spore-print-color': 'see cap color',
        'habitat': 'grasses=g, leaves=l, meadows=m, paths=p, heaths=h, urban=u, waste=w, woods=d', 
        'season': 'spring=s, summer=u, autumn=a, winter=w'
    }

# Disclaimer:
Not to be used as a true decisionmaker when defining the edibility of mushrooms.
Most mushrooms are fine, inedible, or otherwise unusuable for food; however, deadly ones are really deadly.
Use at your own risk.
