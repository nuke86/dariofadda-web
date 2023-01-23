---
title: "Ubuntu phone"
date: 2020-07-27T14:30+08:00
description: "Da Ubuntu Phone ad Android (e viceversa)."
tags: ["linux", "ubuntu", "smartphone"]
type: post
weight: 25
showTableOfContents: true
---

## Da Ubuntu Phone ad Android (e viceversa)

In questa pagina trovate istruzioni e materiale utile per finalizzare questo passaggio sfruttando le potenzialità offerte dai dispositivi BQ e quindi installare Android su Aquaris Ubuntu E X.x di BQ. Nello specifico tutte le prove sono state fatte con un **Aquaris E4.5 Ubuntu Edition**.

Vista l'ancora limitata usabilità a livello consumer, di questo sistema operativo di casa Canonical, ho deciso di rendere pubblico il supporto di questo dispositivo per il sistema Android.

I prodotti BQ infatti, concepiti per le distribuzioni di Ubuntu Touch, a livello hardware sono delle macchinette perfette per ospitare anche un sistema Android. Avendo inoltre un hardware con caratteristiche tuttaltro che limitate posso affermare che Android "gira" estremamente **bene**.

## Materiale

*   [2.0.1\_20150623-1900\_bq-FW.zip](http://www.dariofadda.it/views/files/2.0.1_20150623-1900_bq-FW.zip) Firmware ufficiale per Android **Lollipop 5.0**
*   [Drivers&Tool.rar](http://www.dariofadda.it/views/files/Drivers&Tool.rar) Flash tools con driver per Windows (solo Vista e 7)
*   [Tool\_Ubuntu.zip](http://www.dariofadda.it/views/files/Tool_Ubuntu.zip) Flash utility per Ubuntu o sistemi Debian

L'operazione è realizzabile sia su Windows che su sistemi GNU/Linux. Il supporto più semplice e immediato per installare Android sul nostro E4.5 è utilizzare un PC GNU/Linux, per l'immediato supporto hardware offerto. Non si drovranno infatti installare nessun tipo di driver o periferica.

La procedura è semplice: una volta scaricati il Firmware (1) e il Tool\_Ubuntu (3), scompattiamo entrambi gli archivi nelle rispettive sottocartelle. A questo punto entrando nel Tool Ubuntu semplicemente facciamo partire l'eseguibile **flash\_tool.sh** come utente root. Apparirà la medesima interfaccia QT come nella versione Windows.

## Inizializziamo il programma

Nella schermata principale noteremo due fonti, entrambe modificabili, nella prima ci si riferisce al Download Agent e non la si deve modificare. Nella seconda invece si parla di Scatter-loading File, questo è il firmware che vogliamo installare, quindi dal menu di fianco scegliamo quello che abbiamo precedentemente estratto (sarà un file **.txt**).

## Parte pratica

Il mio consiglio è di collegare con USB il nostro Ubuntu Phone rigorosamente spento. Una volta collegato (assicurandoci di avere il flash\_tool aperto), premere il pulsante di accensione del telefono a lungo, guardando il monitor, non appena appare il messaggio di collegamento del dispositivo con il flash\_tool, premere nel programma il pulsante _Download_ per far iniziare il processo.

Al termine dell'installazione il programma crea un messaggio di SUCCESSO, dopo il quale possiamo scollegare lo smartphone e accenderlo per verificare l'installazione di Android perfettamente completata.

