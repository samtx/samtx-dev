---
title: "Tafelberg Vacation Rental Site API"
date: 2021-07-05
weight: 2
repo_url: https://github.com/samtx/tafelberg-api
live_site_url: https://tafelberg-api.samtx.dev
tags: [python, starlette, web scraping]
---

A small, family-owned company had three different short-term property rentals listed on a local vacation rental web platform.
The family wanted a custom website to promote their vacation properties, *Tafelberg*, located in Rockport, Texas.
They wanted to keep reservation and booking system with their existing vendor, but wanted to be able to customize the reservation calendar display for their properties.

I built this backend service to scrape the vendor's reservation web site for each property.
The scraper collects reservation availability and pricing for the next 12 months.

The backend service exposes a REST API to deliver current property reservation information.
Another endpoint returns the formatted booking URL which directs a user from the custom marketing site to the official vendor site to make the booking.

The backend is written in Python using FastAPI for web serving. 
Web scraping is performed using httpx and BeautifulSoup.
The results are stored in an in-memory cache with a short time-to-live. 
The cache ensures that the vendor's reservation system isn't pinged too often while returning near up-to-date reservation data.
