# 02 - Routing

In diesem Exercise gehen wir auf verschiedene Arten des Routings in Angular ein.

Als Beispielprojekt werden wir eine Blog-Seite erstellen, auf welcher eine Übesricht über die erstellen Blog Posts und eine Ansicht mit Detailinfos zu einzelnen Blog Posts. Zudem werden wir eine Navigation erstellen, um das Routing zu üben.

???? Screenshots

## 2.1 Neue Routes erstellen

1. Erstelle eine neue Route `/overview` über welche die in der vorherigen Übung erstellte Komponente erreicht werden kann
2. Erstelle eine `wildcard` Route, welche alle weiteren URL Pfade auf die zuvor erstellte Route weiterleitet

## 2.2 Router-Outlet und Routerlink nutzen

1. Erstelle 2 neue Komponenten
   - eine mit Namen "navbar", welche eine Navigation bar werden soll
   - eine mit Namen "detail", welche als Detail Ansicht der Blog Posts
2. Integriere folgendes im App Template (HTML) file
   - die Navbar Komponente
   - einen `<main>` Tag
   - den `<router-outlet>` Tag
3. Importiere das Menu von Angular Material (`mat-menu`) und erstelle in der "Navbar" Komponente ein Menu mit 2 Einträgen
   - der erste Eintrag "Übersicht" soll bei klick über einen `RouterLink` auf die bereits existierende "overview" Komponente navigieren
   - der zweite Eintrag "Neuer Post"????? dient vorerst als Placeholder und wird in einer späteren Übung verwendet

## 2.3 Routing in der Komponente mit URL Parameter

1. Importiere den Router im `.ts` File der "overview" Komponente
2. Erstelle eine Methode welche eine number ID entgegennimmt und auf über die URL `/detail/:id` mit der entsprechenden ID auf die "Detail" Komponente navigiert

### Zusatzaufgabe

Nutze `RouterLinkActive`, um den aktiven RouterLink einzufärben/hervorzuheben
