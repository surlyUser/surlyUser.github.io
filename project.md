---
layout: default
title: "Project"
date: 2026-03-06
---
[Home](./index.html) \| [Project](./project.html) \| [About](./about.html)

# Project

## GitHub Pages

Für das Fach WMC soll mit Hilfe von GitHub Pages eine Website erstellt werden.
Normalerweise verwendet man für eine einfache Website CSS, HTML und JavaScript, wobei
komplexere Seiten auch noch Datenbanken, jQuery, React, CMS und viele weitere Tools verwenden.
Bei einem GET-request wird dann aus allen den fIles und Daten dynamisch eine Seite erstellt und im Browser des Users dargestellt. Das dauert eine gewisse Zeit und ist anfällig für Hacker-Angriffe.

GitHub Pages arbeitet nach dem SSG-Prinzip (Static Site Generator), das heißt es wird mit Hilfe eines Generators eine statische Seite erstellt. Diese wird dann schon im Vorfeld erstellt
und somit auf Anfrage eines Clients die fertige Seite gesendet.
Das ist schneller und sicherer als die zuvor erwähnte dynamische Variante.
Mittlerweile können damit auch komplexere, dynamische Seiten kreiert werden - Stichwort JAMstack.


### Basic Tools For Github Pages

Für einfachere Seiten bzw. Themes verwendet man hauptsächlich:

- Jekyll als SSG (Standard bei Github; andere möglich)
- md-Files für die Inhalte
- eigene HTML- und CSS-Files um individuelle Anpassungen zu machen (Override Theme)
- Liquid für die Templates


## Different Ways To Create A Site

### How To

Es gibt mehrere Möglichkeiten, eine solche Seite zu erstellen:

- Alles selbst erstellen, from scratch sozusagen
- Ein Theme importieren und mit eigenen Files ergänzen
- Ein Theme "Forken" und dieses als Basis für die Webseite nehmen

### Themes

Folgende Seiten stellen *Themens* zur Verfügung:

- jekyllthemes.io: Gute Filter für Blogs, Portfolios oder Dokumentationen
- jekyllthemes.org: Eine der ältesten und größten Sammlungen
- jamstackthemes.dev: Moderne Übersicht über statische Webseiten-Designs

Zusätzlich bietet GitHub auch [Standard-Themes](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll) an.

### Getting Started

Hier findet man eine [Quickstart-Anleitung](https://docs.github.com/en/pages/quickstart).


## Examples

### Integrating A Theme Into Your Website

Nachdem man entsprechend den Anweisungen der *Quickstart-Anleitung* eine Seite erstellt hat,
muss man, um ein Theme zu importieren, dieses in das File **_config.yml** eintragen.
Zusätzlich sind weitere Infos wie *title, description, plugins...* notwendig - das variert
je nach Theme; am Besten die Anleitung des entsprechenden Themes beachten.

```yml
# Basic info
title: Title
description: My first SSG site

# Theme
# remote_theme: daattali/beautiful-jekyll
remote_theme: pages-themes/modernist@v0.2.0

# Plugins
plugins:
  - jekyll-remote-theme
```

Wichtig ist sind auch die sogenannten **YAML Front Matter**.
Diese müssen ganz am Beginn der md-Files stehen und bilden den Verweis zu einem anderen Element, wie z.B. das
html-File, in das der Inhalt des md-Files dann intgriert wird.

```md
---
layout: default
title: "About"
date: 2026-03-06
---

# H1

## H2
```

### More Advanced Themes

Die meisten Themes bauen auf die eben erwähnten Basic-Setting auf, wobei *fancier* Themes oft zusätzliche Strukturen und Settings erfordern.

Das Theme *Beautiful Jekyll* ist ein Beispiel für etwas mehr Aufwand bezüglich der Erstellung und Anpassung einer Website.
Wer sich das Repositry ansieht, wird feststellen, dass es hier viel mehr Files und Folder gibt, die ein feineres bzw. gezielteres Design ermöglichen
out-of-the-box ermöglichen.

Die Basics bleiben gleich, jedoch ist die Verschachtelung der Dateien untereinander schon komplexer.

Ein Beispiel dafür:

```html
---
layout: page
---

<!-- content: Platzhalter für den Inhalt der referenzierenden Datei -->
{{ content }}

{% assign posts = paginator.posts | default: site.posts %}

<!-- role="list" needed so that `list-style: none` in Safari doesn't remove the list semantics -->
<ul class="posts-list list-unstyled" role="list">
  {% for post in posts %}
  <li class="post-preview">
    <article>

      {%- capture thumbnail -%}
        {% if post.thumbnail-img %}
          {{ post.thumbnail-img }}
....usw.....
```

Typische File-Struktur: 

![Folder example]({{ site.baseurl }}/assets/img/folder_example.JPG)
