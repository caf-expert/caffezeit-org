---
date: '2025-07-04T12:30:00+02:00'
draft: false
title: 'GitHub Pages mit Hugo: Der komplette Guide'
description: 'Eine Schritt-für-Schritt Anleitung zum Erstellen einer Website mit Hugo und GitHub Pages'
tags: ['github-pages', 'hugo', 'tutorial', 'deployment', 'github-actions']
categories: ['Tutorials', 'GitHub']
cover:
    image: "images/posts/github-pages-hugo.svg"
    alt: "GitHub Pages mit Hugo Tutorial"
    caption: "GitHub Pages + Hugo = Perfekte Kombination für Websites"
    relative: false
    hidden: false
---

# GitHub Pages mit Hugo: Der komplette Guide

GitHub Pages ist eine fantastische Möglichkeit, statische Websites kostenlos zu hosten. In Kombination mit Hugo können Sie schnell professionelle Websites erstellen.

## 🎯 Was Sie benötigen

- Ein GitHub-Account
- Hugo auf Ihrem lokalen Computer
- Grundkenntnisse in Git
- Ein Texteditor Ihrer Wahl

## 🚀 Schritt-für-Schritt Anleitung

### 1. Hugo-Projekt erstellen

```bash
# Neues Hugo-Projekt erstellen
hugo new site meine-website
cd meine-website

# Git Repository initialisieren
git init
```

### 2. Theme hinzufügen

```bash
# Theme als Submodule hinzufügen
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod

# Theme in Konfiguration setzen
echo 'theme = "PaperMod"' >> hugo.toml
```

### 3. GitHub Actions Workflow

Erstellen Sie `.github/workflows/deploy.yml`:

```yaml
name: Deploy Hugo site to GitHub Pages

on:
  push:
    branches: ["main"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive

      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          extended: true

      - name: Build
        run: hugo --minify

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

### 4. GitHub Repository konfigurieren

1. Erstellen Sie ein neues Repository auf GitHub
2. Pushen Sie Ihren Code:

```bash
git remote add origin https://github.com/USERNAME/REPO-NAME.git
git branch -M main
git add .
git commit -m "Initial commit"
git push -u origin main
```

3. Aktivieren Sie GitHub Pages:
   - Gehen Sie zu Settings → Pages
   - Wählen Sie "GitHub Actions" als Source

## ⚙️ Hugo-Konfiguration optimieren

### Basis-Konfiguration

```toml
baseURL = 'https://username.github.io/repository-name/'
languageCode = 'de-de'
title = 'Meine Website'
theme = 'PaperMod'

enableRobotsTXT = true
enableEmoji = true

[params]
  ShowReadingTime = true
  ShowShareButtons = true
  ShowPostNavLinks = true
  ShowBreadCrumbs = true
  ShowCodeCopyButtons = true

[menu]
  [[menu.main]]
    name = "Home"
    url = "/"
    weight = 10
  [[menu.main]]
    name = "Posts"
    url = "/posts/"
    weight = 20
```

## 🎨 Anpassungen und Styling

### Custom CSS hinzufügen

1. Erstellen Sie `assets/css/custom.css`
2. Fügen Sie `layouts/partials/extend_head.html` hinzu:

```html
<link rel="stylesheet" href="{{ "css/custom.css" | relURL }}">
```

### Eigene Layouts

Überschreiben Sie Theme-Templates, indem Sie sie nach `layouts/` kopieren.

## 📝 Content erstellen

### Neue Posts

```bash
hugo new content posts/mein-post.md
```

### Front Matter Beispiel

```yaml
---
title: "Mein Blogpost"
date: 2025-07-04T12:00:00+02:00
draft: false
tags: ["hugo", "blog"]
categories: ["Tutorial"]
description: "Beschreibung des Posts"
---
```

## 🔧 Erweiterte Features

### Kommentare hinzufügen

Integrieren Sie Kommentarsysteme wie:
- Disqus
- Utterances (GitHub Issues)
- Giscus (GitHub Discussions)

### Analytics

```toml
[params]
  googleAnalytics = "GA-TRACKING-ID"
```

### SEO Optimierung

```toml
[params]
  description = "Website-Beschreibung"
  keywords = ["keyword1", "keyword2"]
  author = "Ihr Name"
```

## 🚨 Häufige Probleme

### Submodules nicht geladen

```bash
git submodule update --init --recursive
```

### Base URL falsch

Stellen Sie sicher, dass die `baseURL` in `hugo.toml` korrekt ist.

### GitHub Actions Fehler

Überprüfen Sie die Permissions in den Repository-Einstellungen.

## 📚 Weiterführende Ressourcen

- [Hugo Dokumentation](https://gohugo.io/documentation/)
- [PaperMod Theme Docs](https://github.com/adityatelange/hugo-PaperMod)
- [GitHub Pages Docs](https://docs.github.com/en/pages)

## 🎉 Fazit

Mit Hugo und GitHub Pages haben Sie eine mächtige Kombination für das Erstellen und Hosten von Websites. Der Workflow ist automatisiert, kostenfrei und skalierbar.

Viel Erfolg mit Ihrer neuen Website!ate = '2025-07-04T12:59:07+02:00'
draft = true
title = 'Github Pages Guide'
+++
