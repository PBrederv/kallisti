---
title: Hoe deze site werkt
date: 2025-02-18 15:59
draft: false
tags:
  - zaadje
  - technisch
---
Ok, deze site werkt nu. In het kader van leren in het openbaar, wil ik delen hoe het precies draait - en hoe ik ervoor gezorgd heb dat het zo draait. Misschien dat dat in de toekomst ooit nog verandert, misschien dat ik dan de boel weer overhoop ga halen. Het is niet de bedoeling, maar ik ken mezelf. Dan wil ik het toch weer nét iets anders, omdat het dan gewoon in mijn hoofd er nét iets anders weer uit ziet.[^1]

## Hele grote stappen, lekker snel thuis
Ik schrijf mijn notities in [Obsidian](https://obsidian.md/). Dat is een vrij minimalistische app om in te schrijven - weinig op het scherm, dus weinig afleiding. Met Obsidian maak ik zogenaamde [Markdown-bestanden](https://www.markdownguide.org/) aan. Vervolgens vertaalt [Quartz](https://quartz.jzhao.xyz/) Markdown in HTML en maakt er zo een website van. Dat is hele grote stappen lekker snel thuis.

Internet heb ik hiervoor niet nodig. Ik hoef in dit stadium nergens in te loggen. Het staat gewoon op een schijf.[^2] Markdown zijn gewoon bestanden. Quartz genereert een statische site: een verzameling HTML- en CSS-bestanden die ook gewoon op mijn computer staan

> [!note]- Markdown is eigenlijk best wel handig
> Waarom heb ik Markdown trouwens niet eerder ontdekt? Het typt lekker snel. Ik hoef niet met de muis naar een ander deel van het scherm om daar op iets te klikken en een kop van een stuk tekst te maken. Dat is ook de bedoeling van Markdown. Het voelt sneller dan Word of Wordpress. Obsidian heeft wel wat variaties op de standaard-Markdown, waardoor ik dit soort *callouts* kan doen. 
> Ook sla je Markdown-bestanden gewoon ergens op. Wat ik dan weer fijner vind dan een database, zoals bij Wordpress

## Online zetten
Eigenlijk vereist het natuurlijk meer dan dat. Obsidian is makkelijk zat. Quartz heeft, helaas wat meer voeten in de aarde: NodeJS, en allerlei dingen die je moet aanpassen in scripts om het uiterlijk aan te passen. Dat probeer ik tot een minimum te beperken. Het is een lopend proces; als ik iets bedenk, dan vogel ik het uit en pas ik het aan.

Omdat ik niet in een CMS werk, maar offline op een computer of telefoon, moet ik de heleboel online zien te krijgen. Anders is het niet openbaar en geen website. Dát had even iets meer voeten in de aarde. De Quartz-handleiding vertelt je heel handig hoe je alles ergens op een server kan krijgen. Er zijn een paar leuke manieren om dat bijna volledig automatisch te laten doen. Alleen vertellen ze je alleen hoe dat moet voor bepaalde diensten en ik gebruik liever de webhosting die ik toch al heb.

Niet dat het veel werk is om deze website daar te krijgen. Ik genereer de site, log via FTP in op mijn host en sleep het mapje erheen. Het is niet heel erg veel werk - maar wel meer dan die mazzelaars die via de ondersteunde hostingdiensten gebruiken. Gelukkig vond ik na enig geklooi een oplossing.

Het hoeft niet, maar Quartz zegt wel dat je de basis voor de site op [GitHub](https://github.com/) op kan slaan. Niet de pagina's die Quartz genereert, maar wel de Markdownbestanden en alle scripts die nodig zijn om de site te maken. Vanuit daar kunnen die "bepaalde hostingdiensten"[^3] zelf Quartz gebruiken om de website te maken en hopla, staat die online. Voor één van die diensten - Github Pages - moet je wel zelf een zogenaamde actie opzetten, die de site voor je bouwt en het daarna verplaatst.

Wat als ik dat kon gebruiken om de pagina naar op Github te bouwen en dan naar mijn host te verplaatsen? Dat bleek te kunnen. Door de actie van de makers van Quartz zelf te combineren met een actie die via FTP alles over kan zetten naar een host, kreeg ik het aan de gang. Hier staat [die actie](https://github.com/PBrederv/kallisti/blob/v4/.github/workflows/main.yml), als je dit toevallig leest en hetzelfde wil doen.

Zet daarnaast een Obsidian plug-in die mijn notities automatisch *pusht* naar mijn Github en hoppa: met een druk op de knop update ik deze site. Heel handig. Tot alles breekt en ik niet weet waarom, want ik snap nog niet echt *hoe* het werkt. Ik weet ook niet of ik dat wel [[Alles is content, maar niets heeft inhoud##user-content-fnref-2|wil weten]].

> [!note]- Obsidian, Github en open source
> Een van mijn lichte ergernissen is dat noch Obsidian noch Github open source zijn. Obsidian is wel weer gratis en niet van een groot techbedrijf, maar Github is van Microsoft - en dat vind ik niet superfijn. Er zijn echter open-source alternatieven en ik zoek dus wel uit of ik over kan stappen, zonder het makkelijk updaten van Quartz te verliezen. *Wordt vervolgd...*

[^1]: Dat heb ik dus met wat er op [paulbrederveld.nl](https://paulbrederveld.nl) staat. Ik had weer een nieuw idee en nu wil ik weer helemaal opnieuw beginnen. ¯\_(ツ)_/¯

[^2]: Nou ja, eigenlijk via een cloud, zodat ik zowel thuis als mobiel aan iets kan werken en het zo over al mijn *devices* gesynchroniseerd wordt.

[^3]: Github Pages, Cloudflare en nog een paar anderen
