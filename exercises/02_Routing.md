# 02 - Routing

In diesem Exercise gehen wir auf verschiedene Arten des Routings in Angular ein.

## 1. Neue Routes erstellen

1. Erstelle eine neue Route `/overview` über welche die im vorherigen Exercise erstellte Component erreicht werden kann
2. Erstelle eine "wildcard" Route, welche alle weiteren URL Pfade auf die zuvor erstellte Route weiterleitet

## 2. Router-Outlet und Routerlink nutzen

1. Erstelle 2 neue Components
   - die Erste soll eine navigation bar werden
   - die Zweite dient als Detail Ansicht der Blog Posts
2. Integriere folgendes im App Template (HTML) file
   - die Navbar Component
   - einen main Tag
   - den "router-outlet" Tag
3. Importiere das Menu von Angular Material (mat-menu) und erstelle in der "Navbar" Component ein Menu mit 2 Einträgen
   - der eine Eintrag soll bei klick über einen "RouterLink" auf die "Overview" Component navigieren
   - der zweite Eintrag navigiert einem auf .......

## 3. Bonus: Routing über Component

1. Importiere den Router im Component File der "Overview" Component
2. Erstelle eine Methode welche eine number ID entgegennimmt und auf über die URL `/detail/:id` mit der entsprechenden ID auf die "Detail" Component navigiert
