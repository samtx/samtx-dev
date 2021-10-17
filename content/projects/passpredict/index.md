---
title: "Satellite Pass Predictor"
resources:
- src: iss.jpg
  title: International Space Station
weight: 1
github_url: https://github.com/samtx/passpredict
live_site_url: https://passpredict.com
---
# Website and Library to Predict Satellite Overpasses

![The ISS above the Earth](iss.jpg)

I've been developing a Python/CPP library to accompany a website that will show upcoming overpasses for any satellite over a user-defined location on earth. I found that existing websites that provide this function aren't user friendly, don't work well on mobile devices, and have poor performance. My goal was to develop site that is easy enough for a novice to use, but detailed enough to provide benefit for expert use as well.

The website is live at [passpredict.com](https://passpredict.com).  It is built with a Python backend using Starlette and FastAPI. The frontend is server-rendered with Jinja templates. It uses Postgresql and Redis for data storage and caching. Caddy server is the reverse proxy for the Starlette application and serves the static files. All of the applications are hosted on a Digital Ocean virtual private server.

Orbit and satellite data is gathered from [Celestrak](https://celestrak.com) three times a day. Orbit propagation and overpass prediction is computed with the [Orbit Predictor](https://github.com/satellogic/orbit-predictor) python library. It uses the SGP4 propagator [python-sgp4](https://github.com/brandon-rhodes/python-sgp4), written by Brandon Rhodes, with WGS84 Earth constants. Coordinate frame transformations use the IAU FK5/1976 coordinate frames. Cython is used to speed up some functions.

