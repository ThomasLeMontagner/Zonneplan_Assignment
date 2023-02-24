# Zonneplan_Assignment
## Achtergrondinformatie

Zonneplan Energie heeft als ambitie om het komende jaar te groeien naar 30.000 tot 75.000 energieklanten. We bieden klanten een energiecontract met uurprijzen. Dit betekent dat de prijs voor elektriciteit ieder uur wijzigt. Klanten zien iedere dag om 13.00 uur de prijzen in de Zonneplan App voor de komende 35 uur. Zij kunnen hun verbruik aanpassen aan de prijzen. Als energieleverancier ben je verplicht om elektriciteit voor je klanten zo goed mogelijk te voorspellen en vervolgens in te kopen.

Voor ieder kwartier moet de afname (of teruglevering) van het elektriciteitsnet worden ingekocht.  Dit moet vóór 10:00 D-1 voor leveringdag D. Wanneer het gerealiseerde verbruik afwijkt van ons voorspelde verbruik hebben we ‘’onbalans’’. Bij onbalans (ver)kopen we het verschil tussen de voorspelde en gerealiseerde volumes tegen de prijs die op dat moment geldt (de onbalansmarkt). De prijs op de [onbalansmarkt](https://services.tenergy.nl/public.aspx/actualimbalanceprices) is afhankelijk van de onbalans op het gehele elektriciteitsnet en kan zowel positief als negatief uitpakken. Gemiddeld gezien is het echter ongunstig om onbalans te hebben. Hierdoor is het belangrijk om de positie van je energieportfolio zo goed mogelijk te voorspellen. 

De verbruiksvoorspelling wordt op dit moment gedaan aan de hand van historische en voorspelde data. Dit is historische verbruiksdata uit de slimme meter, historische en voorspelde zon opwek data uit de omvormer, historische prijzen en historische en voorspelde weerdata.

## Opdracht

Maak een verbruiksvoorspelling aan de hand van de meegeleverde dataset. De opdracht is om het verwachte verbruik (of teruglevering) in kWh per kwartier te forecasten voor de periode 1 t/m 7 januari voor de som van alle actieve contracten in het energieportfolio. 

[datafiles_assignment_data_scientist.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0eea6785-e96b-4a87-a636-26c08c6aaa07/datafiles_assignment_data_scientist.zip)

<aside>
❗ Het voorspelde volume per kwartier heeft altijd maar 1 stand. (Afname minus teruglevering)

Teruglevering van elektriciteit zijn negatieve waarden, afname is positief. 

Alleen het verbruik afgenomen of ingevoed op het elektriciteitsnet is relevant. Er kan verbruik plaatsvinden binnen een huishouden wat niet geregistreerd wordt op de slimme meter. Dit gebeurt wanneer er zonne-opwek is wat direct in huis wordt verbruikt.  

Niet alle klanten hebben zonnepanelen, en niet iedereen met zonnepanelen heeft deze gekocht bij Zonneplan. 

Alle relevante informatie over de data staat in het ZIP bestand.

</aside>

## Wat verwachten we van je?

- Oplossing: Een voorspelling voor de periode 1 t/m 7 januari met een stand per kwartier.
- Aanpak: Duidelijke uitleg hoe je tot deze voorspelling bent gekomen.
- Vervolgstappen: Hoe ga je deze voorspelling nog beter maken als je hier de komende maanden mee bezig gaat?
- Reflectie: Waar liep je tegenaan? Wat ging goed? Wat kon beter?

Deze opdracht mag worden uitgewerkt in een document of als een presentatie.

# Data
actual_values.json:

    Contract_id: personal identification number of household
    Timestamp: quarter times in local timezone
    Pv_actual_kwh: realized generated with solar panels in kWh
    P1_actual_kwh: realized kWh on smart meter
    Pv_forecast_kwh: forecast generated with solar panels in kWh

forecast_values.json:

    Contract_id: personal identification number of household
    Timestamp: quarter times in local timezone
    Pv_forecast_kwh: advance expected generation with solar panels in kWh

contracten_database_table.csv:

    Contract_id: personal identification number of household
    Start_date: first day of customer's contract
    End_date: last day of customer's contract

weahter_actual.json and weather_forecast.json:

    Location_id: location of weather station
    Ghi: Global Horizontal Irradiation
    Dni: Direct Normal Irradiation
    Dhi: Diffuse Horizontal Irradiation
    Ebh: Direct (Beam) Horizontal Irradiance
    Zenith: The angle between a line perpendicular to the earth's surface and the sun (90 deg = sunrise and sunset; 0 * deg = sun directly overhead)
    Azimuth: The angle between a line pointing due north to the sun's current position in the sky. Negative to the East. Positive to the West. 0 at due North
    Cloud_opacity: The measurement of how opaque the clouds are to solar radiation in the given location.
    Air_temp: temperature in degrees celsius Timestamp: quarter times in local timezone

price_epex.json:

    Price_epex: market price at which we buy and sell
    Timestamp: quarter times in local timezone
