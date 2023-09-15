# Intro

## introduction

- cheat sheet link: html, css
- jede component ein Teil einer view
- component gegliedert in
  - template: html
    - syntax {{}}
  - style sheet: css
  - eigentliche behaviour in component.ts
  - file für testing: component spec.ts
- input zu templates (inline oder extern) wird automatisch aktualisiert
- angular material vorstellen

## routing

- routing module
- wild card default navigation \*\*
- url parameter
- router-outlet
- verschiedene arten von navbar
  - routerLink vs. click -> router.navigate

## data binding und directives

- 3 verschiedene arten + beispiele
- ngStyle, ngClass
- *ngIf, *ngFor

## parent/child communication

- input()
- output()
- ngOnInit(), ngAfterViewInit(), ngOnDestroy(), ngOnChanges()

## services & backend communication

- cheat sheet:
- services
  - für alles nicht ui bezogene (helpermethods, reused methods)
  - eine anwendung http requests
- httpClient + observables
  - observables bieten subscriptions

## forms

- static form Erstellung
- kurze Info zu dynamic forms

## guards/auth

- was sind guards? wie nutzen?
- authentication
- authorization
