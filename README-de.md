# PlaidCloud Dokumentation

[![Build Status](https://api.travis-ci.org/PlaidCloud/website.svg?branch=master)](https://travis-ci.org/PlaidCloud/website)
[![GitHub release](https://img.shields.io/github/release/PlaidCloud/website.svg)](https://github.com/PlaidCloud/website/releases/latest)

Herzlich willkommen! Dieses Repository enthält alle Assets, die zur Erstellung der [PlaidCloud-Website und Dokumentation](https://plaidcloud.com/) erforderlich sind. Wir freuen uns sehr, dass Sie dazu beitragen wollen!

## Beiträge zur Dokumentation

Sie können auf die Schaltfläche **Fork** im oberen rechten Bereich des Bildschirms klicken, um eine Kopie dieses Repositorys in Ihrem GitHub-Konto zu erstellen. Diese Kopie wird als *Fork* bezeichnet. Nehmen Sie die gewünschten Änderungen an Ihrem Fork vor. Wenn Sie bereit sind, diese Änderungen an uns zu senden, gehen Sie zu Ihrem Fork und erstellen Sie eine neue Pull-Anforderung, um uns darüber zu informieren.

Sobald Ihre Pull-Anfrage erstellt wurde, übernimmt ein Rezensent von PlaidCloud die Verantwortung für klares, umsetzbares Feedback. Als Eigentümer des Pull-Request **liegt es in Ihrer Verantwortung Ihren Pull-Reqest entsprechend des Feedbacks, dass Sie vom PlaidCloud-Reviewer erhalten haben abzuändern.** Beachten Sie auch, dass Sie am Ende mehr als einen Rezensenten von PlaidCloud erhalten, der Ihnen Feedback gibt, oder dass Sie Rückmeldungen von einem Rezensenten von PlaidCloud erhalten, der sich von demjenigen unterscheidet, der ursprünglich für das Feedback zugewiesen wurde. In einigen Fällen kann es vorkommen, dass einer Ihrer Prüfer bei Bedarf eine technische Überprüfung von einem [PlaidCloud Tech-Reviewer](https://github.com/PlaidCloud/website/wiki/tech-reviewers) anfordert. Reviewer geben ihr Bestes, um zeitnah Feedback zu geben, die Antwortzeiten können jedoch je nach den Umständen variieren.

Weitere Informationen zum Beitrag zur PlaidCloud-Dokumentation finden Sie unter:

* [Mitwirkung beginnen](https://plaidcloud.com/docs/contribute/start/)
* [Ihre Dokumentationsänderungen bereitstellen](https://plaidcloud.com/docs/contribute/intermediate#view-your-changes-locally)
* [Seitenvorlagen verwenden](https://plaidcloud.com/docs/contribute/style/page-content-types/)
* [Dokumentationsstil-Handbuch](https://plaidcloud.com/docs/contribute/style/style-guide/)
* [Übersetzung der PlaidCloud-Dokumentation](https://plaidcloud.com/docs/contribute/localization/)

## `README.md`'s Localizing PlaidCloud Documentation

### Deutsch
Die Betreuer der deutschen Lokalisierung erreichen Sie unter:

* Benedikt Rollik ([@bene2k1](https://github.com/bene2k1))
* Max Körbächer ([@mkorbi](https://github.com/mkorbi))
* [Slack Kanal](https://PlaidCloud.slack.com/messages/PlaidCloud-docs-de)

## Site lokal mit Docker ausführen

Um die PlaidCloud-Website lokal laufen zu lassen, empfiehlt es sich, ein spezielles [Docker](https://docker.com) Image auszuführen, das den statischen Site-Generator [Hugo](https://gohugo.io) enthält.

> Unter Windows benötigen Sie einige weitere Tools, die Sie mit [Chocolatey](https://chocolatey.org) installieren können.
`choco install make`

> Wenn Sie die Website lieber lokal ohne Docker ausführen möchten, finden Sie weitere Informationen unter [Website lokal mit Hugo ausführen](#Die-Site-lokal-mit-Hugo-ausführen).

Das benötigte [Docsy Hugo theme](https://github.com/google/docsy#readme) muss als git submodule installiert werden:

```
#Füge das Docsy submodule hinzu
git submodule update --init --recursive --depth 1
```

Wenn Sie Docker [installiert](https://www.docker.com/get-started) haben, erstellen Sie das Docker-Image `PlaidCloud-hugo` lokal:

```bash
make container-image
```

Nachdem das Image erstellt wurde, können Sie die Site lokal ausführen:

```bash
make container-serve
```

Öffnen Sie Ihren Browser unter http://localhost:1313, um die Site anzuzeigen. Wenn Sie Änderungen an den Quelldateien vornehmen, aktualisiert Hugo die Site und erzwingt eine Browseraktualisierung.

## Die Site lokal mit Hugo ausführen

Hugo-Installationsanweisungen finden Sie in der [offiziellen Hugo-Dokumentation](https://gohugo.io/getting-started/installing/). Stellen Sie sicher, dass Sie die Hugo-Version installieren, die in der Umgebungsvariablen `HUGO_VERSION` in der Datei [`netlify.toml`](netlify.toml#L9) angegeben ist.

Das benötigte [Docsy Hugo theme](https://github.com/google/docsy#readme) muss als git submodule installiert werden:

```
#Füge das Docsy submodule hinzu
git submodule update --init --recursive --depth 1
```

So führen Sie die Site lokal aus, wenn Sie Hugo installiert haben:

```bash
# Installieren der JavaScript Abhängigkeiten
npm ci
make serve
```

Dadurch wird der lokale Hugo-Server an Port 1313 gestartet. Öffnen Sie Ihren Browser unter http://localhost:1313, um die Site anzuzeigen. Wenn Sie Änderungen an den Quelldateien vornehmen, aktualisiert Hugo die Site und erzwingt eine Browseraktualisierung.

## Community, Diskussion, Beteiligung und Unterstützung

Erfahren Sie auf der [Community-Seite](https://plaidcloud.com/community/) wie Sie mit der PlaidCloud-Community interagieren können.

Sie können die Betreuer dieses Projekts unter folgender Adresse erreichen:

- [Slack](https://PlaidCloud.slack.com/messages/sig-docs)
- [Mailing List](https://groups.google.com/forum/#!forum/PlaidCloud-sig-docs)

### Verhaltensregeln

Die Teilnahme an der PlaidCloud-Community unterliegt dem [PlaidCloud-Verhaltenskodex](code-of-conduct.md).

## Vielen Dank!

PlaidCloud lebt vom Community Engagement und wir freuen uns sehr über Ihre Beiträge zu unserer Website und unserer Dokumentation!
