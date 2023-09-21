# 04 - Parent-Child Verhalten

In dieser Übung werden wir das Parent-Child Verhalten mithilfe eines `*ngFor` Loops und den Input und Output Directives erkunden.

## 4.1 Child Input

1. Erstelle eine weitere Komponente "card"
2. Importiere die Blog Posts aus dem "data" Ordner ins `.ts` File der "overview" Komponente und initialisiere den entsprechenden Array.
3. Nutze einen for-Loop, im HTML File der "overview" Komponente auf dem HTML Tag der neu erstellten "card" Komponente, welcher durch den Blog Post Array iteriert.
4. Füge der "card" Componente eine Input Variable hinzu und übergib damit as jeweilige Object aus dem Blog Post Array.
5. Importiere das `MatCardModule` im `.ts` File der "card" Komponente und erstelle den HTML Tag `<mat-card>` im HTML File.
6. Die`mat-card` enthält einen `mat-card-header`, in welchem Titel und Autor\*in und `mat-card-content`, in welchem das Bild (aus dem Input der "overview" Komponente als Parent) dargestellt werden soll.
7. Triggere den Router bei Klick auf die `mat-card` zur Weiterleitung auf die "detail" Komponente bzw. auf die URL `/detail/:id`, mit der entsprechenden id des Posts.

## 4.2 Child Output

1. Erstelle in der "card" Komponente einen Boolean, welcher ein Output Event emitiert. Setze diesen per Default auf `false`.
2. Erstelle eine Methode welche bei Klick auf das `mat-card` Element den Boolean auf `true` setzt und damit das Output Event emitiert.
3. Empfange das Output Event in der "overview" Komponente, um hier den Boolean im Array der Blog Posts unter dem Attribut "read" zu speichern.

## 4.3 Lifecycle Hooks

1. Nutze die `ngOnInit()` Methode in der "detail" Komponente, um die über die URL als Parameter übergebene `id` als Variable zu initialisieren.
2.

## Zusatzaufgabe

1. Nutze das neue "read" Attribut, um mithilfe eines `mat-toggle` und eines `*ngIf` gelesene Posts ausblenden zu können (Toggle an = alle Posts, Toggle aus = nur ungelesene Posts). Zeige je nach Toggle Position per Interpolation "all" bzw. "unread" an.
2. Nutze das "read" Attribut in der "card" Komponente, um der `mat-card` per `ngClass` die CSS Klassen `read` bzw. `unread` zuzuweisen.
   ?????? nur wenn css-klassen bereitgestellt
