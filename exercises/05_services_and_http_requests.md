# 05 - Services und HTTP-Requests

## 5.1 Service hinzufügen

Erstelle einen Service für deine App und verwende ihn in deiner Overview Komponente (definiere bspw. eine `getData()` Funktion die statische Dummy Daten an den Komponenten übergibt)

## 5.2 HTTP-Request ausführen

Benutze den [HTTP-Client](https://angular.io/api/common/http/HttpClient#usage-notes) von Angular um einen ersten GET Request auszuführen. Sende diesen an das vorbereitete Backend mit der url `https://angular-workshop.dev.digisus-lab.ch/`

## 5.3 Verwendung von Daten in Komponenten

Versuche nun die vom Request erhaltenen Daten in der Komponente zu verwenden anstelle des statisch definierten Arrays. Der loop sollte sich nun also auf die live Daten des Backends beziehen und nicht mehr auf im Angular Projekt statisch definierte Daten

### Zusatzaufgabe

Versuche einen Patch Request zu senden, um einen existierenden Blog Post abzuändern
