# VectoRide — Smarter Routes. Better Rides.

**Version:** 0.1 web/PWA prototype. **Test area:** Kearney, Nebraska.

## What works
- Mobile responsive map and start location selection (tap / drag marker)
- Ride distance, baseline speed, departure time, mode and surface UI
- Request three loop-shaped bicycle routing candidates from the publicly hosted Valhalla OSM test routing server; display actual returned road/trail geometry, distance and basic time comparisons
- Fetch the live NWS hourly forecast for the selected start coordinate
- PWA manifest and service worker for installation on Android over HTTPS

## Not implemented yet
- Route optimization by wind, predicted departure time, effort, training history
- Traffic avoidance filtering / road-safety certification. The high-traffic switch is **only a preference placeholder** and does not affect routing yet.
- Route-surface selection filtering, scoring of ride modes, route fitting to exact requested mileage
- Offline map and route navigation, user accounts, turn-by-turn directions, Strava integration

**Important:** Treat all generated routes as unverified suggestions, not navigation instructions. Independently verify cycling legality, conditions, shoulders and traffic. Routes can deviate from target distance. Valhalla public endpoint and NWS connectivity depend on browser CORS and service availability and are not production infrastructure.

## Run locally
Python: `python -m http.server 8000` inside the VectoRide directory; then open http://localhost:8000.
For mobile, deploy the files together to an HTTPS static host (e.g., GitHub Pages); then use Android Chrome → Add to Home screen / Install app. An Android phone needs HTTPS for PWA install and service worker. Remote map tiles and routing require internet.

## Next build milestone
Integrate a production-grade routing backend, enforce high-traffic avoidance, query forecasts along the route, calculate wind-adjusted speed / work, and evaluate departure windows.
