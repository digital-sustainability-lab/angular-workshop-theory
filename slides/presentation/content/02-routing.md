# 02 Angular Routing

--

## Routing Module

- zuständig für das Verhalten der Routes
  - Mapping der Pfade auf die Komponenten (und Guards)
  - Redirects
  - Wildcard und URL Parameter

--

## Router Outlet

- stellt die im Routing Module zugewiesene Komponente des aktiven Route Pfades dar

--

## Arten der Navigation...

- über RouterLink in HTML Files

```html
<a
  routerLink="/navigate/here"
  routerLinkActive="['active','other-css-class']"
></a>
```

- über Angular Router in Methoden in `.ts` Files der Komponenten

```html
<button (click)="navigateWithCustomBehavior(id)">navigate by id</button>
```

```typescript
navigateWithCustomBehavior(id: number) {
    // custom logic...
    this.router.navigate([`navigate/by/${id}`])
}
```

- absolute und relative Pfade

--

## Your turn :) --> Übung 2
