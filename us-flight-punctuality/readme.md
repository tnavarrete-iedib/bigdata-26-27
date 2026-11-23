
# Puntualitat dels vols als Estats Units per número de vol
[**https://huggingface.co/datasets/tripstow/us-flight-punctuality**](https://huggingface.co/datasets/tripstow/us-flight-punctuality)

Dades mensuals de puntualitat de tots els vols domèstics programats per les principals companyies aèries dels Estats Units. Cada fila correspon a una companyia aèria, un número de vol i una ruta durant un mes, per als darrers 12 mesos publicats per l'Oficina d'Estadístiques del Transport dels Estats Units (BTS). Les dades són actualitzades mensualment per [**TripStow**](https://tripstow.com/).

Es poden consultar versions més fàcils de llegir a [**tripstow.com/flights**](https://tripstow.com/flights), amb una pàgina per a cada vol, ruta, aeroport i companyia aèria. També hi ha informes mensuals a [**tripstow.com/blog**](https://tripstow.com/blog), dades estadístiques a [**tripstow.com/press**](https://tripstow.com/press) i una classificació mensual dels aeroports a [**tripstow.com/press/airports**](https://tripstow.com/press/airports).

## Camps

| **Camp** | **Significat** |
| :--- | :--- |
| `month` | Primer dia del mes (AAAA-MM-DD). |
| `carrier` | Companyia aèria (codi IATA, segons les dades comunicades al BTS). |
| `flight_number` | Número de vol. |
| `origin`, `dest` | Aeroports d'origen i destinació (codis IATA). |
| `flights` | Nombre de vols programats durant el mes. |
| `cancelled`, `diverted` | Nombre de vols cancel·lats o desviats. |
| `on_time` | Nombre de vols que arriben amb un retard inferior a 15 minuts respecte de l'horari previst (segons la definició del Departament de Transport dels EUA). |
| `late_30` | Nombre de vols que arriben amb més de 30 minuts de retard. |
| `arr_delay_mean`, `arr_delay_median` | Mitjana i mediana, respectivament, del retard d'arribada en minuts dels vols efectuats (els valors negatius indiquen que han arribat abans de l'hora prevista). |

La proporció de vols puntuals es calcula com a `on_time / (flights - cancelled - diverted)`, tal com es fa als informes oficials.

## Font i llicència

**Font:** Departament de Transport dels Estats Units, Oficina d'Estadístiques del Transport (BTS), dades de puntualitat de les companyies aèries (*Airline On-Time Performance*).

Les obres del Govern dels Estats Units són de domini públic. Aquesta recopilació de dades es distribueix sota la llicència CC0. S'agraeix citar TripStow ([**https://tripstow.com**](https://tripstow.com)), però no és obligatori.
