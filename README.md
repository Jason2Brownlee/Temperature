# Vermont Temperature Forecast

A simple one-page website to summarize the temperature forecast for the weather station (Scoresby, Victoria) closest to my house (Vermont, Victoria).

Visit: https://jasonbrownlee.me/Temperature/

## How to Change

You can update the "site" for your preferred weather station. Here's how:

1. Get the `geohash` for your suburb name.
	a. Visit: https://api.weather.bom.gov.au/v1/locations?search=vermont
	b. Change the search string from `vermont` to `<your suburb>`, use `+` for space if needed.
	c. On the loaded page, find and copy the value of `geohash`, e.g. `r1r28pf`
	d. Remove the last character from the `geohash`, e.g. `r1r28p`
2. Update docs/index.html for your the `geohash` for your suburb name.
	a. Change the observation API URL to use your `geohash` in the `fetchCurrentTemperature()` function: `'https://api.weather.bom.gov.au/v1/locations/r1r28p/observations'`
	b. Change the forecast API URL to use your `geohash` in the `fetchWeatherData()` function: 'https://api.weather.bom.gov.au/v1/locations/r1r28p/forecasts/hourly';
	c. Save and load the index.html in your browser.
3. Host your modified `index.html` somewhere, like [GitHub pages](https://pages.github.com/).

## References

* [Latest Weather Observations for Scoresby](http://www.bom.gov.au/fwo/IDV60901/IDV60901.95867.html) ([json](http://www.bom.gov.au/fwo/IDV60901/IDV60901.95867.json))
* [Scoresby Forecast](http://www.bom.gov.au/vic/forecasts/scoresby.shtml)
* [Melbourne Olympic Park Air Temperature](http://www.baywx.com.au/melbtemp2.html)
* [Australian Weather Data (using bom.gov.au)](https://github.com/tonyallan/weather-au/tree/master)

### APIs

* https://github.com/tonyallan/weather-au/blob/master/weather_au/api.py
* https://api.weather.bom.gov.au/v1/locations?search=vermont
* https://api.weather.bom.gov.au/v1/locations/r1r28p/forecasts/hourly
* https://api.weather.bom.gov.au/v1/locations/r1r28p/observations