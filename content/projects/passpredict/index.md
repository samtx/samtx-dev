---
title: "Satellite Pass Predict Python Library"
weight: 1
repo_url: https://github.com/samtx/passpredict
draft: false
---

I've been developing a Python/CPP library to accompany a website that will show upcoming overpasses for any satellite over a user-defined location on earth. I found that existing libraries that provide this function aren't highly configurable for the different levels of accuracy that are needed.

Orbit propagation and overpass prediction is based on the [Orbit Predictor](https://github.com/satellogic/orbit-predictor) python library. It uses the SGP4 propagator [python-sgp4](https://github.com/brandon-rhodes/python-sgp4), written by Brandon Rhodes, with WGS84 Earth constants. Coordinate frame transformations use the IAU FK5/1976 coordinate frames. Cython is used to speed up some functions.

