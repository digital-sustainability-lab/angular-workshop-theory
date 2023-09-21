# 06 - Forms

In dieser Übung werden wir ein Formular implementieren um das Erstellen neuer Blog Posts zu ermöglichen.

## 6.1 Statisches Formular erstellen

1. Erstelle eine neue Komponente "create-post"
2. Erstelle `template-driven` ein Formular mit 4 Input Feldern (Author, Title, Description, Image URL) inklusive `submit` button, welcher die `onSubmit(form)` Methode mit dem Formular als Input aufrufen soll
3. Setze Author, Title & Description required

## 6.2 Daten mit POST Request speichern

1. Importiere den `HttpClient` in der "create-post" Komponente und erstelle (wenn noch nicht vorhanden) eine `onSubmit(form: NgForm)` Methode
2. Prüfe darin, ob das Formular gültig ist und speichere in diesem Fall die Formularwerte per HTTP POST Request auf die URL ???????????.

## Zusatzaufgabe

Schreibe das `template-driven` in ein `reactive` Formular um.