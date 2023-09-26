# 04 - Parent-Child Verhalten

In dieser Übung werden wir das Parent-Child Verhalten mithilfe eines `*ngFor` Loops und den Input und Output Directives erkunden. Dabei werden wir die in Übung 3 erstellte `mat-card` von der "overview" Komponente in eine separate Komponente auslagern.

## 4.1 Child Input

1. Erstelle eine weitere Komponente "card"
2. Ergänze den Datensatz im `.ts` File der "overview" Komponente wie folgt:

```typescript
// Beispieldaten
[
  {
    id: 1,
    title: "Fancy first blog post",
    description: "Hello world! Here I am!",
    author: "Amazing, Laura",
    imageUrl: "https://cdn2.thecatapi.com/images/34h.jpg",
    color: "blue",
    class: "special",
    show: true,
  },
  {
    id: 2,
    title: "Fancy second blog post",
    description: "Hello world! Here I am!",
    author: "Excited, John",
    imageUrl: "https://cdn2.thecatapi.com/images/9pj.jpg",
    color: "black",
    class: "special",
    show: true,
  },
  {
    id: 3,
    title: "Fancy third blog post",
    description: "Hello world! Here I am!",
    author: "Mesmerising, Billy",
    imageUrl: "https://cdn2.thecatapi.com/images/bhp.jpg",
    color: "green",
    class: "normal",
    show: false,
  },
  {
    id: 4,
    title: "Fancy fourth blog post",
    description: "Hello world! Here I am!",
    author: "Surprising, Lisa",
    imageUrl: "https://cdn2.thecatapi.com/images/eaj.jpg",
    color: "green",
    class: "normal",
    show: true,
  },
];
```

3. Nutze den for-Loop, im HTML File der "overview" Komponente, um für jeden Eintrag des Arrays eine Einheit der neu erstellten "card" Komponente darzustellen (Iteration über Card).
4. Füge im HTML File der "overview" Komponente dem HTML Tag der "card" Komponente eine Input Variable hinzu, übergib damit das jeweilige Object aus dem Blog Post Array und deklariere den Input in der "card" Komponente.
5. Migriere die `mat-card` aus von der "overview" in die "card" Komponente (migriere auch alle mit der card verknüpften inhalte aus dem `CSS` und dem `.ts` File).
6. Passe die `mat-card` an: diese enthält neu einen `mat-card-header`, in welchem Titel als `<h4>` und Autor\*in als `<p>` sowie `mat-card-content`, in welchem das Bild dargestellt werden soll. Nutze dazu die Daten aus dem Input.
7. Vergib dem `mat-card-header` die Klasse `header` und nutze folgendes CSS Snippet:

```css
.header {
  display: flex;
  flex-direction: column;
}
img {
  width: 100%;
  height: auto;
}
```

8. Ändere zudem das `height` Attribut der `mat-card` im CSS File an auf den Wert `fit-content`, um die Card Höhe dem Bild anzupassen.
9. Triggere den Router bei Klick auf die `mat-card` zur Weiterleitung auf die "detail" Komponente bzw. auf die URL `/detail/:id`, mit der entsprechenden id des Posts. Migriere hierfür die `navigateToDetail(id)` Methode aus der "overview" in die "card" Komponente und nutze diese für die Navigation.

## 4.2 Child Output

1. Erstelle in der "card" Komponente einen Boolean, welcher ein Output Event emitiert. Setze diesen per Default auf `false`.
2. Nutze die Methode `navigateToDetail(id)`, um bei Klick auf das `mat-card` Element den Boolean auf `true` zu setzen, damit das Output Event emitiert.
3. Empfange das Output Event in der "overview" Komponente, um hier den Boolean-Wert im entsprechenden Blog Post unter dem Attribut "read" zu speichern.

## 4.3 Lifecycle Hooks

1. Nutze die `ngOnInit()` Methode in der "detail" Komponente, um die über die URL als Parameter übergebene `id` als Variable zu initialisieren. Nutze die `ActivatedRoute` um die `id` aus der URL zu extrahieren. Da URL Parameter grundsätzlich als `string` übergeben werden und auch `null` sein können, sofern nicht vorhanden, muss der entsprechende Parameter mit [`Number(string)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number?retiredLocale=de) zu einer number geparsed werden.
2. Kopiere den Array mit den Blog Posts in die "detail" Komponente und erstelle eine Methode `getDetail(id)` in welcher über die `id` der zugehörige Post geholt und zurückgegeben wird. Hierzu kann die `javascript` `Array.find()` Methode verwendet werden. Für mehr Infos siehe [hier](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find?retiredLocale=de)
3. Rufe die eben erstellte Methode bei Komponenten-Initialisierung auf, um den ausgewählten Post einer Variable `currentPost` zuzuweisen.
4. Stelle die Post Informationen (Title, Description, Author, Image) im HTML File dar.

## Zusatzaufgabe

1. Erstelle eine `sortRead()` Methode in der "overview" Komponente, welche das Array so sortiert, dass zuerst alle Posts zurückgegeben werden, welche noch nicht "read" sind. Weitere Infos siehe [Doku](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort?retiredLocale=de)
2. Loope beim HTML File durch den Rückgabewert dieser Methode, anstelle des unsortierten Arrays.
3. Nutze das "read" Attribut, um mithilfe eines `mat-toggle` gelesene Posts ausblenden zu können (Toggle an = alle Posts, Toggle aus = nur ungelesene Posts). Zeige je nach Toggle Position per Interpolation "all" bzw. "unread" an. Sofern das `mat-toggle` aus Übung 1 noch vorhanden ist, kannst du dieses entsprechend anpassen.
4. Nutze das "read" Attribut in der "card" Komponente, um der `mat-card` per `ngClass` die CSS Klassen `read` bzw. `unread` zuzuweisen. Passe das CSS-Styling nach belieben über die beiden Klassen an.
