# Angular-Workshop

Theorie Slides und Übungen

## NodeJS installieren

Direkte Installation [siehe hier](https://nodejs.org/en/download). Über Package Manager (empfohlen) [siehe hier](https://nodejs.org/de/download/package-manager).

## Exkurs: Git

[Git](https://git-scm.com/) dient als Versionierungstool des Code-Repositories. Plattformen wie [GitHub](https://github.com/) und [GitLab](https://about.gitlab.com/) für remote Repositories, um gemeinsam an einem Projekt arbeiten zu können.

## Wichtigste Git Befehle

Nachfolgend die wichtigsten Befehle für die Interaktion mit git und darüber ebenfalls mit remote Repositories

- remote Repository abbild lokal herunterladen: `git clone <repository>`
- Änderungen auf dem remote Repository ins eigene lokale Abbild laden: `git pull`
- Änderungen im Repository versionieren (speichern):
  - hinzufügen zur Versionierung `git add .`
  - mit einer Änderungsnachricht versehen `git commit -m "add new feature"`
- Änderungen auf das remote Repository laden und anderen Entwicklern damit zugängig machen: `git push <remote> <branch-name>`
