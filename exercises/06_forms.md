# 06 - Forms

In dieser Übung werden wir ein Formular implementieren, um das Erstellen neuer Blog Posts zu ermöglichen.

## 6.1 Statisches Formular erstellen

1. Erstelle eine neue Komponente "create-post" und rufe diese über den entsprechenden Menü Eintrag in der Navbar über eine neue Route `create-post` auf.
2. Erstelle in der neuen Komponente `template-driven` ein Formular mit 4 Input Feldern (Author, Title, Description, Image URL) inklusive `submit` button, welcher die `onSubmit(form)` Methode mit dem Formular als Input aufrufen soll.
3. Importiere `MatFormFieldModule` und `MatInputModule` im App Module
4. Packe die `inputs` im HTML File der neuen Komponente in den `<mat-form-field>` Tag und weise diesem die CSS Klasse `example-full-width`, sowie dem `<form>` Tag die Klasse `form` zu. Deklariere die `inputs` als matInput. Nutze zudem folgendes CSS Snippet:

```css
.form {
  padding: 5rem 10rem;
}
.example-full-width {
  width: 100%;
}
```

6. Setze Author, Title & Description required.

## 6.2 Daten mit POST Request speichern

1. Importiere den `BackendService` in der "create-post" Komponente und erstelle (wenn noch nicht vorhanden) eine `onSubmit(form: NgForm)` Methode.
2. Erstelle im `BackendService` eine Methode `storeData(newPost)`, welche einen neuen Post entgegennimmt und diesen per POST Request auf die URL `https://angular-workshop.dev.digisus-lab.ch/` sendet.
3. Prüfe in der `onSubmit` Methode der "create-post" Komponente, ob das Formular gültig ist und führe rufe in diesem Fall die neu erstellte Methode auf.
4. Wenn nicht bereits getan, passe folgende Komponenten an, damit diese ebenfalls mit den Daten des Backends arbeiten:
  - Datensatz in der "detail" Komponente
  - OutputTrigger der Card, welcher diese als "read" setzt (Info: da wir in diesem Workshop aufgrund der Komplexität keine Authentication eingebaut haben wird ein Post für alle auf "read" gesetzt sobald die ersten Teilnehmer*innen dies triggern. Auch für Bearbeitungen und Erstellen neuer Einträge wäre im realen Leben natürlich eine solche erforderlich, um Berechtigungen überprüfen zu können)


### Zusatzaufgabe

1. Schreibe das `template-driven` in ein `reactive` Formular um.
2. Verwende die "create-post" Komponente, um damit zusätzlich bestehende Blogs bearbeiten über den PATCH Request updaten zu können. Füge in der "detail" Komponente einen entsprechenden Angular [Material Icon Button](https://material.angular.io/components/button/overview) ein, über welchen zum Bearbeitungsformular des entsprechenden Posts gewechselt werden kann.
