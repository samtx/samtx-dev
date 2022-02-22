---
title: "Satellite Pass Predictor Website"
# resources:
# - src: iss.jpg
#   title: International Space Station
weight: 2
repo_url: https://github.com/samtx/passpredict-app
live_site_url: https://passpredict.com
draft: false
---

I've been developing a Python/CPP library to accompany a website that will show upcoming overpasses for any satellite over a user-defined location on earth. I found that existing websites that provide this function aren't user friendly, don't work well on mobile devices, and have poor performance. My goal was to develop site that is easy enough for a novice to use, but detailed enough to provide benefit for expert use as well.

The website is live at [passpredict.com](https://passpredict.com).  It is built with a Python backend using Starlette and FastAPI. The frontend is server-rendered with Jinja templates. It uses Postgresql and Redis for data storage and caching. A Caddy server is the reverse proxy for the Starlette application and serves the static files. All of the applications are hosted on a Digital Ocean virtual private server.

Orbit and satellite data is gathered from [Celestrak](https://celestrak.com) three times a day. Overpass prediction is computed with my [passpredict](https://github.com/samtx/passpredict) python library.

