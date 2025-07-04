# Meine Hugo GitHub Page

Dies ist eine mit [Hugo](https://gohugo.io/) erstellte Website, die automatisch auf GitHub Pages bereitgestellt wird.

## 🚀 Features

- **Hugo Static Site Generator**: Schnell und modern
- **PaperMod Theme**: Sauberes und responsives Design
- **Automatische Bereitstellung**: GitHub Actions für CI/CD
- **Deutschsprachig**: Konfiguriert für deutsche Inhalte

## 📁 Projektstruktur

```
test-hugo/
├── .github/workflows/    # GitHub Actions für automatische Bereitstellung
├── archetypes/          # Content-Vorlagen
├── content/             # Website-Inhalte
│   └── posts/          # Blog-Posts
├── layouts/             # HTML-Templates
├── static/              # Statische Dateien
├── themes/              # Hugo-Themes
│   └── PaperMod/       # Verwendetes Theme
└── hugo.toml           # Hugo-Konfiguration
```

## 🛠️ Lokale Entwicklung

### Voraussetzungen

- [Hugo Extended](https://gohugo.io/installation/) (Version 0.147.9 oder höher)
- [Git](https://git-scm.com/)

### Setup

1. Repository klonen:
   ```bash
   git clone <repository-url>
   cd test-hugo
   ```

2. Submodules initialisieren:
   ```bash
   git submodule update --init --recursive
   ```

3. Lokalen Server starten:
   ```bash
   hugo server -D
   ```

4. Website im Browser öffnen: http://localhost:1313

## ✏️ Neue Inhalte erstellen

### Neuen Blog-Post erstellen

```bash
hugo new content posts/mein-neuer-post.md
```

### Draft-Status entfernen

Bearbeiten Sie den erstellten Markdown-File und setzen Sie `draft = false` im Front Matter.

## 🚀 Bereitstellung

Die Website wird automatisch auf GitHub Pages bereitgestellt, wenn Änderungen auf den `main` Branch gepusht werden.

### Manuelle Bereitstellung

Sie können den Deployment-Workflow auch manuell über die GitHub Actions Tab in Ihrem Repository auslösen.

## 📝 Konfiguration

Die Hauptkonfiguration befindet sich in `hugo.toml`. Hier können Sie:

- Website-Titel und -Beschreibung ändern
- Theme-Einstellungen anpassen
- Menü-Struktur konfigurieren
- Social Media Links hinzufügen

## 🎨 Theme anpassen

Das PaperMod Theme bietet viele Anpassungsmöglichkeiten. Weitere Informationen finden Sie in der [PaperMod Dokumentation](https://github.com/adityatelange/hugo-PaperMod).

## 📚 Weitere Ressourcen

- [Hugo Dokumentation](https://gohugo.io/documentation/)
- [PaperMod Theme](https://github.com/adityatelange/hugo-PaperMod)
- [GitHub Pages Dokumentation](https://docs.github.com/en/pages)

## 📄 Lizenz

Dieses Projekt steht unter der MIT-Lizenz.
