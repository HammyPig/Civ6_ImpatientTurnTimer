# ImpatientTurnTimer

Increases the likelihood that your multiplayer game will finish in a single session.

This sets the game's dynamic turn timer equal to 10 + 5*<max_cities> seconds, where <max_cities> is the highest number of cities owned by any single civilization.

This was determined by getting 3 hours and dividing it by 250 turns (the max turns of an online speed game), resulting in roughly 43 seconds per turn. We specify we want a minimum turn time of 15 seconds, which will then scale linearly to 70 seconds (to create an average near our target). For the sake of simplicity, we assume the maximum number of cities will scale linearly throughout the game. Our starting city gives us 15 seconds, meaning the remaining 55 seconds must come from our additional cities. Given a player builds 12 cities over the course of a game, this scales to 5 seconds per city.

In comparison, the current dynamic turn timer is far more generous, set at 30 + 10*<max_cities> + 5*<max_units> seconds.
