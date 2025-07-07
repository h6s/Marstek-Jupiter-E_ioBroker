# Marstek Jupiter E(C) per ESPHome über Modbus in ioBroker einbinden


Ich habe eine Konfiguration (marstek-jupiter-e.yaml - Datei) für ESPHome in Verbindung mit einem Marstek Jupiter E erstellt.
Da diese Konfiguration vielleicht dem Einen oder Anderen etwas Tiparbeit ersparen kann möchte ich sie hier veröffentlichen.

#  
# Folgende Voraussetzungen müssen erfüllt sein:

1. Für den Marstek Jupiter ist ein Anschlusskabel für den RS485 Anschluss (Modbus) erforderlich (war bei mir im Lieferumfang erhalten)
2. Es wird ein Pegelwandler vom Modbus auf TTL (3 Volt) benötigt. Solche Breakout-Boards gibt es bei verschiedenen Händlern ab einem Euro...
3. Für die Einbindung in ESPHome wird noch ein ESP32 benötigt. Ein ESP8266 würde sicherlich auch ausreichen - ich nehme aber lieber einen 32 (in meinem Fall MINI32 V1.0.0) da ich hier bessere Erfahrungen mit dem W-Lan gemacht habe.
4. Darüber hinaus wird natürlich noch ein 5 Volt Netzteil für den ESP benötigt ;-)

Die für die serielle Kommunikation notwendigen Pins - in meinem Fall GPIO21 und GPIO22 - können beim ESP32 mehr oder weniger frei gewählt werden. Ist also vom Layout des Aufbaus abhängig zu machen.

Ich habe die Abfrage-Intervalle der einzelnen Parameter in drei Gruppen aufgeteilt. Einige werden im 5 Sekunden Takt ausgelesen andere wiederum nur minütlich oder nur alle 5 Minuten. Da kann jeder selber festlegen welche Geschwindigkeiten wichtig sind... Wenn zu viele Parameter bei einer Abfrage ausgelesen werden gibt es allerdings eine Warnmeldung im ESPHome-Log, dass die Abfrage zu lange dauert.

Ansonsten wünsche ich viel Spaß mit der Implementierung und bin für Verbesserungen dankbar...
