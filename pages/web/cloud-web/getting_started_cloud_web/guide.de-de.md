---
title: Erste Schritte mit Cloud Web Hosting
slug: erste-schritte-mit-cloud-web
excerpt: In dieser Anleitung erfahren Sie, wie Sie richtig mit Ihrem Cloud Web Hosting starten
section: Erste Schritte
---

**Stand 25.06.2018**

## Einleitung

Unser Cloud Web Hosting Angebot kombiniert 20 Jahre Webhosting-Erfahrung mit der Power unserer Public Cloud. Wie bei unseren klassischen Webhostings werden Ihre Internetseiten auch bei Cloud Web auf einem rund um die Uhr verwalteten Dienst gehostet. Darüber hinaus haben Sie Zugriff auf zusätzliche Funktionen und profitieren von der höheren Performance unserer SSD-Festplatten.

**Hier erfahren Sie, wie Sie richtig mit Ihrem Cloud Web Hosting starten.**

## Voraussetzungen

- Sie verfügen über ein [Cloud Web Hosting](https://www.ovh.de/hosting/cloud-web.xml) Angebot.
- Sie haben die Bestätigungs-E-Mail zur Installation Ihres Cloud Web Hostings erhalten.
- Sie besitzen eine [Domain](https://www.ovh.de/domains/), über die Ihre Website erreichbar sein wird.
- Sie sind in Ihrem [Kundencenter](https://www.ovh.com/auth/?action=gotomanager) eingeloggt.

## Beschreibung

### Schritt 1: Ihr Projekt definieren

Cloud Web Hosting bietet mehr Konfigurationsmöglichkeiten als ein klassisches Webhosting, damit Sie Ihr Angebot möglichst genau an Ihr Projekt anpassen können. Um dieses erfolgreich umzusetzen, ist es wichtig, dass Sie Ihr Ziel klar vor Augen haben. Das sind unsere Empfehlungen:

- **Legen Sie fest, was Sie einrichten möchten**: Möchten Sie einen Blog oder einen Onlineshop erstellen? Ihre Leidenschaft mit anderen teilen oder die Internetpräsenz Ihres Unternehmens stärken? Bestimmen Sie die Einzelheiten Ihres Projekts, bevor Sie beginnen.

- **Ermitteln Sie die technischen Voraussetzungen für die Installation**: Möglicherweise müssen für Ihr Projekt bestimmte technische Voraussetzungen erfüllt sein. Überprüfen Sie diese am besten im Voraus.

- **Stellen Sie sicher, dass Ihr Projekt mit Cloud Web Hosting technisch kompatibel ist**: Benötigen Sie eine bestimmte Runtime Engine oder SQL-Sprache? Falls Sie das noch nicht getan haben, überprüfen Sie, dass alles, was Sie brauchen, bei Ihrem [Cloud Web](https://www.ovh.de/hosting/cloud-web.xml) Hosting verfügbar ist.

Nachdem Sie sich die verschiedenen Optionen angesehen und Ihr Projekt genau definiert haben, können Sie mit der Umsetzung beginnen.

### Schritt 2: Runtime Engine auswählen

Bei Cloud Web stehen Ihnen für Ihr Projekt verschiedene Entwicklungssprachen zur Verfügung. Falls Sie eine andere Sprache als das standardmäßig ausgewählte PHP verwenden möchten, wählen Sie die entsprechende „Runtime Engine“ aus.

Aktuell sind folgende Programmiersprachen verfügbar: PHP und Node.js.

Um zu den Runtime Engines Ihres Cloud Web Hostings zu gelangen, loggen Sie sich in Ihrem [OVH Kundencenter](https://www.ovh.com/auth/?action=gotomanager){.external} ein, klicken Sie links im Menü auf `Hosting-Pakete`{.action} und wählen Sie das betreffende Cloud Web Hosting aus. Gehen Sie dann auf den Tab `Runtime Engines`{.action}.

Bei der Installation Ihres Hostings wird automatisch eine Engine erstellt und als `Standardauswahl` in der zugehörigen Tabelle angezeigt. Um eine bereits eingerichtete Runtime Engine zu bearbeiten, klicken Sie auf die drei Punkte rechts daneben und anschließend auf `Bearbeiten`{.action}. 

Je nach [Cloud Web](https://www.ovh.de/hosting/cloud-web.xml) Angebot können Sie auch zusätzliche Runtime Engines hinzufügen. Klicken Sie hierzu auf den Button `Aktionen`{.action} und anschließend auf `Runtime Engine hinzufügen`{.action}. Bitte beachten Sie, das die maximale Anzahl an Runtime Engines von dem von Ihnen bestellten Cloud Web Angebot abhängig ist.

Überprüfen Sie daher, bevor Sie fortfahren, dass Sie über die für Ihr Projekt notwendigen Runtime Engines verfügen.

![Cloud Web](images/cloud-web-first-steps-step1.png){.thumbnail}

### Schritt 3: Umgebungsvariablen erstellen (optional)

Wenn Sie Ihr Projekt mehrfach in verschiedenen Umgebungen einrichten möchten (zum Beispiel: Entwicklung, Test oder Produktion), brauchen Sie Variablen, damit Ihr Code entsprechend reagiert. Hierfür können Sie mit Cloud Web verschiedene Umgebungsvariablen definieren, die über den Code Ihrer Website oder Webanwendung verfügbar sind.

Dadurch ist es zum Beispiel möglich, keine .env-Datei im PHP-Framework Laravel festzulegen, wie es in der zugehörigen Dokumentation beschrieben ist: <https://laravel.com/docs/5.6/configuration>.

Um eine Umgebungsvariable hinzuzufügen, gehen Sie zum betreffenden Cloud Web Hosting und klicken Sie anschließend auf `Umgebungsvariablen`{.action}. Es wird eine Tabelle mit den für Ihr Angebot erstellten Umgebungsvariablen angezeigt. Um eine neue Variable hinzuzufügen, klicken Sie auf den Button `Aktionen`{.action} und anschließend auf `Umgebungsvariable hinzufügen`{.action}. Folgen Sie nun den Anweisungen für die Variable, die Sie erstellen möchten.

![Cloud Web](images/cloud-web-first-steps-step2.png){.thumbnail}

Wenn Sie kein Entwicklungsframework mit Umgebungsvariablen verwenden oder überprüfen möchten, ob Ihre Umgebungsvariablen funktionieren, können Sie hierfür ein Skript erstellen. Im Folgenden finden Sie zwei Beispiele, um Ihnen bei diesem Vorgang zu helfen. Sie ersetzen allerdings nicht die Hilfe eines Webmasters.

- **Für PHP**:

```php
<?php echo "ENV: " . $_ENV['DB_DATABASE']; ?>
```

- **Für Node.js**:

```sh
var http = require('http');

http.createServer(function(request, response) {  
    response.writeHeader(200, {"Content-Type": "text/html"});  

    response.write( process.env. 'DB_DATABASE');

    response.end();  
}).listen(80);
```

Vergessen Sie nicht, die allgemeinen Angaben in diesen Skripten („DB_DATABASE“) durch die entsprechende Umgebungsvariable zu ersetzen.

### Schritt 4: Zusätzliche Domains und Multisite konfigurieren (optional)

Nun da die technische Umgebung Ihres Cloud Web Hostings fertig ist, können Sie zusätzliche Domains konfigurieren und als Multisite einrichten. So können Sie Ihren Bereich aufteilen und beispielsweise mehrere Websites darauf hosten. Wenn Sie dies für Ihr Projekt einrichten möchten, gehen Sie erneut zum entsprechenden Cloud Web Hosting und klicken Sie anschließend auf den Tab `Multisite`{.action}.

Die angezeigte Tabelle listet alle Domains auf, die Ihrem Hosting zugewiesen sind. Einige wurden bei der Installation Ihres Hostings automatisch hinzugefügt. Um weitere hinzuzufügen, klicken Sie auf den Button `Eine Domain oder Subdomain hinzufügen`{.action} und folgen Sie den Anweisungen. Die Vorgehensweise kann variieren, je nachdem, ob Ihre Domain bei OVH gehostet ist oder nicht. 

Füllen Sie die folgenden Informationen sorgfältig aus:

- **Wurzelverzeichnis**: Verzeichnis, in dem die angegebene Domain auf einem Speicherplatz Ihres Cloud Web Hostings gehostet sein muss. 

- **Runtime Engine**: Zuvor eingerichtete Runtime Engine, die für die Multisite verwendet wird, die Sie gerade erstellen.

> [!warning]
>
> Wenn Sie eine externe Domain hinzugefügt haben, muss zusätzlich ein TXT-Feld mit dem Namen **ovhcontrol** in der DNS-Konfiguration der Domain erstellt werden. Über dieses Feld kann OVH überprüfen, dass die Domain tatsächlich hinzugefügt werden darf. Wurde kein TXT-Feld erstellt, wird der Vorgang abgebrochen.
>

Wiederholen Sie diesen Schritt, falls Sie mehrere Domains zu Ihrem Cloud Web Hosting hinzufügen möchten. Weitere Informationen zum Hinzufügen einer Domain als Multisite finden Sie in unserer Anleitung: [„Hosting multiple websites on your Web Hosting plan“](https://docs.ovh.com/gb/en/hosting/multisites-configuring-multiple-websites/){.external} (in Kürze auf Deutsch).

![Cloud Web](images/cloud-web-first-steps-step3.png){.thumbnail}

### Schritt 5: Projekt auf Cloud Web Hosting einrichten

Es gibt zwei mögliche Vorgehensweisen, um Ihr Projekt einzurichten. Wenn Sie mehrere Projekte einrichten möchten, wiederholen Sie die gewählte Vorgehensweise sooft wie nötig.

#### 1. OVH 1-Klick-Module verwenden

Mit dieser Lösung können Sie auf einer gebrauchsfertigen Websitestruktur aufbauen und diese nach Belieben anpassen (Themes, Texte usw.). OVH stellt Ihnen 4 verschiedene 1-Klick-Module zur Verfügung. Nähere Informationen finden Sie auf der Webseite [„Erstellen Sie Ihre Website mit 1-Klick-Modulen“](https://www.ovh.de/hosting/website/){.external}.

Wenn Sie sich für die Verwendung eines unserer 1-Klick-Module entscheiden, klicken Sie bei dem entsprechenden Cloud Web Hosting auf den Tab `1 Klick Module`{.action} und anschließend auf `Ein Modul hinzufügen`{.action}. Nun können Sie auswählen, ob Sie eine „einfache“ (nicht personalisierbare) Installation oder die Installation „im Experten-Modus“ (mit anpassbaren Optionen) durchführen möchten.

Wenn Sie mehr über die 1-Klick-Module von OVH wissen möchten, werfen Sie einen Blick in unsere Dokumentation: ["Installation Ihrer Website mit 1-Klick-Modulen"](https://docs.ovh.com/de/hosting/webhosting_installation_von_webhosting-modulen/){.external}.

> [!primary]
>
> Wenn Sie 1-Klick-Module nutzen möchten, muss unbedingt die PHP-Runtime-Engine verwendet werden.
>

![Cloud Web](images/cloud-web-first-steps-step4.png){.thumbnail}

#### 2. Projekt manuell einrichten

Die manuelle Einrichtung Ihres Projekts ist um einiges technischer und erfordert zusätzliche Kenntnisse Ihrerseits − egal ob Sie eine neue Website erstellen oder eine bereits existierende migrieren möchten. Deshalb empfehlen wir Ihnen, falls Sie Hilfe brauchen, einen spezialisierten Dienstleister und/oder den Herausgeber der Software zu kontaktieren. 

Wenn Sie sich für die manuelle Installation entschieden haben, benötigen Sie alle Dateien der Website oder Anwendung, die Sie einrichten möchten. Falls Sie zuvor eine Datenbank auf Ihrem Cloud Web Hosting angelegt haben, brauchen Sie außerdem die zugehörigen Angaben und Login-Daten. Wenn Sie eine Website migrieren, erstellen Sie zunächst ein komplettes Backup aller zugehörigen Daten.

Da nicht alle Projekte gleich sind, gibt es auch keine universelle Vorgehensweise. Unsere Anleitungen [„Webhosting: Meine Seite online stellen“](https://docs.ovh.com/de/hosting/webhosting_meine_seite_online_stellen/){.external} und [„Migration Ihrer Website und E-Mails zu OVH“](https://docs.ovh.com/de/hosting/migration-ihrer-website-zu-ovh/){.external} enthalten jedoch einige hilfreiche Informationen zum weiteren Vorgehen.

### Schritt 6: E-Mail-Adressen anlegen

Nun, da Ihr Projekt auf Ihrem Cloud Web Hosting eingerichtet ist, können Sie Ihre E-Mail-Adressen anlegen. Wenn Sie keine E-Mail-Adressen erstellen möchten, gehen Sie direkt zum nachfolgenden Schritt.

Um eine oder mehrere E-Mail-Adressen anzulegen, klicken Sie in Ihrem [OVH Kundencenter](https://www.ovh.com/auth/?action=gotomanager){.external} im linken Menü auf `E-Mails`{.action} und wählen Sie anschließen die Domain aus, die mit Ihrem Cloud Web Angebot verbunden ist.

Um eine neue Adresse einzurichten, klicken Sie auf den Button `Eine E-Mail-Adresse erstellen`{.action} und folgen Sie den Anweisungen. Falls Sie Hilfe benötigen, finden Sie hier die zugehörige Dokumentation: [„Creating an email address with your MX Plan package“](https://docs.ovh.com/gb/en/emails/hosted_email_how_to_set_up_an_email_address/){.external} (in Kürze auf Deutsch).

![Cloud Web](images/cloud-web-first-steps-step5.png){.thumbnail}

### Schritt 7: Konfiguration Ihrer Domain bearbeiten

Wenn Sie bei diesem Schritt angelangt sind, ist Ihr Projekt auf Ihrem Cloud Web Hosting installiert und Ihre E-Mail-Adressen sind eingerichtet. Sollten die E-Mail-Adressen noch nicht funktionieren, ist Ihre Domain möglicherweise nicht richtig konfiguriert. Ist das der Fall, oder sind Sie sich nicht sicher, ob Änderungen vorgenommen wurden, befolgen Sie den aktuellen Schritt.

Wenn Sie dabei sind, Ihre Dienste zu OVH zu migrieren, beachten Sie bitte, dass diese möglicherweise nicht verfügbar sind, falls die Änderungen der DNS-Zone nicht im richtigen Moment durchgeführt wurden. Folgen Sie den entsprechenden Schritten unserer Anleitung [Migration Ihrer Website und E-Mails zu OVH](https://docs.ovh.com/de/hosting/migration-ihrer-website-zu-ovh/){.external} und bearbeiten Sie die DNS-Server Ihrer Domain erst am Ende des Prozesses.

#### 1. OVH DNS-Einträge verstehen 

Es gibt mehrere zu OVH gehörige DNS-Einträge. Wir interessieren uns an dieser Stelle für zwei Einträge, mit denen die Erreichbarkeit Ihrer Website und der Empfang von Nachrichten auf Ihren OVH E-Mail-Adressen sichergestellt werden. Folgen Sie den nachstehenden Schritten, um die entsprechenden Einträge zu finden:

|DNS-Eintrag|Zugehöriger Dienst|Wo finde ich den Eintrag?|
|---|---|---|
|A|Für die Website|Begeben Sie sich in Ihrem [OVH Kundencenter](https://www.ovh.com/auth/?action=gotomanager){.external} im Bereich `Hosting-Pakete`{.action} zum betreffenden Cloud Web Hosting. Suchen Sie dann im Tab `Allgemeine Informationen`{.action} die IP-Adresse, die neben „IPv4“ steht.|
|MX|Für E-Mails|Begeben Sie sich in Ihrem [OVH Kundencenter](https://www.ovh.com/auth/?action=gotomanager){.external} im Bereich `E-Mails`{.action} zur betreffenden Domain. Dann suchen Sie in dem Tab `Allgemeine Informationen`{.action} die Angaben, die neben dem Punkt „MX Einträge“ stehen.|

#### 2. DNS-Einträge überprüfen oder bearbeiten

Nun, da Sie die DNS-Einträge für Ihr Cloud Web Hosting und Ihr OVH E-Mail-Angebot kennen, können Sie deren Konfigurationen überprüfen und gegebenenfalls ändern. Beides geschieht bei dem Anbieter, der die DNS-Konfiguration (die DNS-Zone) Ihrer Domain verwaltet.

> [!warning]
>
> - Wenn Ihre Domain nicht die DNS-Konfiguration von OVH verwendet, muss die Änderung über das Interface des Anbieters vorgenommen werden, bei dem die Konfiguration verwaltet wird.
> 
> - Wenn Ihre Domain bei OVH registriert ist, können Sie überprüfen, ob sie unsere DNS-Konfiguration verwendet. Gehen Sie hierzu in Ihrem [OVH Kundencenter](https://www.ovh.com/auth/?action=gotomanager){.external} zur betreffenden Domain und klicken Sie anschließend auf den Tab `DNS Server`{.action}.
>

Lesen Sie in der folgenden Tabelle, wo Sie die entsprechenden Änderungen vornehmen:

|Verwendete DNS-Konfiguration|Wo nehme ich die Änderungen vor?|
|---|---|
|OVH|Begeben Sie sich in Ihrem [OVH Kundencenter](https://www.ovh.com/auth/?action=gotomanager){.external} im Bereich `Domains`{.action} zur betreffenden Domain. In dem Tab `DNS Zone`{.action} überprüfen Sie dann die Informationen und ändern diese gegebenenfalls ab. Wenn Sie weitere Hilfe benötigen, lesen Sie unsere Anleitung [„Editing an OVH DNS zone“](https://docs.ovh.com/gb/en/domains/web_hosting_how_to_edit_my_dns_zone/){.external} (in Kürze auf Deutsch)|
|Andere|Verwenden Sie das Interface des Anbieters, der die DNS-Konfiguration Ihrer Domain verwaltet. Bei Problemen wenden Sie sich bitte an Ihren Anbieter.|

Die Änderung der DNS-Konfiguration Ihrer Domain erfordert eine Propagationszeit von bis zu 24 Stunden, bis sie voll wirksam ist. Falls Sie mehrere Domains als Multisite mit Ihrem Cloud Web Hosting verbunden haben, müssen die notwendigen Änderungen für jede Domain einzeln durchgeführt werden. 

### Schritt 8: Website personalisieren

Dieser Schritt ist optional, wenn Sie eine Website migriert haben, die bereits angepasst wurde. Wenn Sie jedoch zum Beispiel gerade mithilfe unserer Module eine neue Website installiert haben, können Sie diese durch Anpassung des Themes und die Veröffentlichung erster Inhalte personalisieren.

Wenn Sie Hilfe bei der Nutzung spezieller Funktionen Ihrer Website benötigen, gehen Sie bitte auf die offizielle Website des jeweiligen Herausgebers. Dort finden Sie ergänzende Dokumentation zu Ihrer Unterstützung.

### Schritt 9: E-Mail-Adressen verwenden

Sie können nun auch Ihre E-Mail-Adressen verwenden. Dafür stellt OVH Ihnen eine Webanwendung (Webmail) zur Verfügung: RoundCube. Diese App ist über die Adresse <https://www.ovh.de/mail/> erreichbar, auf der Sie die Login-Daten für Ihre von OVH angelegte E-Mail-Adresse eingeben.

Wenn Sie mehr Informationen über die Verwendung von RoundCube benötigen, werfen Sie bitte einen Blick in unsere Anleitung: [Verwendung von RoundCube](https://docs.ovh.com/de/emails/webmail_verwendung_von_roundcube/){.external} Wenn Sie Ihre E-Mail-Adresse auf einem E-Mail-Client oder einem Gerät (beispielsweise einem Smartphone oder einem Tablet) einrichten möchten, werfen Sie bitte einen Blick in die jeweilige Anleitung unter <https://docs.ovh.com/de/emails/>.

## Weiterführende Informationen

[Migration Ihrer Website und E-Mails zu OVH](https://docs.ovh.com/de/hosting/migration-ihrer-website-zu-ovh/){.external}

[Meine Seite online stellen](https://docs.ovh.com/de/hosting/webhosting_meine_seite_online_stellen/){.external}

[Installation Ihrer Website mit 1-Klick-Modulen](https://docs.ovh.com/de/hosting/webhosting_installation_von_webhosting-modulen/){.external}

[„Hosting multiple websites on your Web Hosting plan“](https://docs.ovh.com/gb/en/hosting/multisites-configuring-multiple-websites/){.external} (in Kürze auf Deutsch)

[Creating an email address with your MX Plan package](https://docs.ovh.com/gb/en/emails/hosted_email_how_to_set_up_an_email_address/){.external} (in Kürze auf Deutsch)

[Verwendung von RoundCube](https://docs.ovh.com/de/emails/webmail_verwendung_von_roundcube/){.external}

Für den Austausch mit unserer User Community gehen Sie auf <https://community.ovh.com/en/>.
