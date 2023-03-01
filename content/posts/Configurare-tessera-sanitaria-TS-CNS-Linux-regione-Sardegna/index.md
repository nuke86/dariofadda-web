---
title: "Configurare la tessera sanitaria (TS-CNS) su Linux per regione Sardegna"
date: 2023-03-01T22:30:00+02:00
description: "Installare i driver per l'accesso alla PA con Carta Nazionale Servizi e Addon Firefox"
tags: ["linux", "sardegna", "driver", "PA"]
type: post
weight: 25
showTableOfContents: true
---

Le istruzioni presenti sul sito Web della regione Sardegna [Sardegna Salute](https://tscns.regione.sardegna.it/it/articoli/come-si-usa) risalgono in alcuni casi al 2012 e altri al 2017, ad ogni modo sono abbastanza datate e con sistemi Linux aggiornati o recenti, è impossibile farle funzionare. Gli Addon per Firefox che vengono forniti non sono più supportati dal browser Mozilla. In questo post offro qualche consiglio e le soluzioni aggiornate per far funzionare la tessera sanitaria TS-CNS su sistemi Linux, senza problemi di compatibilità con le soluzioni offerte da regione Sardegna.

## Installazione driver TS-CNS e Firefox per Linux

Per quanto riguarda l'installazione dei driver, possiamo attenerci a quanto riportato sul sito ufficiale, quindi sceglere la versione del driver, in base al chip della nostra tessera:

* per carte con codice identificativo AC 2013, AC 2014, AC 2018, ACx 2021, ACe 2021, OT 2015, OT 2016 e ID 2019 (in alto a sinistra vicino al logo):
	* LINUX - [file DEB](https://swdownload1.agenziaentrate.gov.it/pub/sanita/libbit4xpki-idemia-amd64.1.4.10-622.deb)
	* LINUX 32bit - UBUNTU - [file DEB](https://swdownload1.agenziaentrate.gov.it/pub/sanita/libbit4xpki-idemia-i386.1.4.10-647.deb)
	* LINUX 32bit - RED HAT - [file RPM](https://swdownload1.agenziaentrate.gov.it/pub/sanita/libbit4xpki-1.4.10-647-idemia.i386.rpm)

* per carte con identificativo ST 2021 e ST2022:
	* LINUX 64bit - [file ZIP](https://swdownload1.agenziaentrate.gov.it/pub/sanita/SafeDive2022-4.9.1_x64.zip)
	* LINUX 32bit - [file ZIP](https://swdownload1.agenziaentrate.gov.it/pub/sanita/SafeDive2022-4.9.1_x32.zip)
	
Procedere dunque con l'installazione del pacchetto selezionato e tenere presente che se ci dovessero essere problemi con le dipendenze di DPKG, eseguire l'installazione di:

`sudo apt install libccid pcscd`

e poi

`sudo apt --fix-broken install`

A questo punto potete installare il pacchetto scaricato in precedenza con:

`sudo dpkg -i libbit4xpki-idemia-amd64.1.4.10-622.deb`

## Configurazione di Firefox

Come detto dunque se scaricate l'Addon Firefox che regione Sardegna offre, non riuscirete ad installarlo a meno che non abbiate un PC senza aggiornamenti dal 2017. Per superare questo problema e abilitare Firefox, affinché legga il lettore carte con la tessera inserita, dovete aggiungere un dispositivo di sicurezza.

Dalle **Impostazioni** di Firefox cliccare su **Privacy e Sicurezza->Certificati->Dispositivi di sicurezza**. A questo punto compare una finestra di **Gestione Dispositivi**, premere sul pulsante **Carica**.
Nella finestra che appare a video, inserire il Nome modulo che si sta per caricare (per es. “TS-CNS”).
Nel campo Nome file modulo inserire il Path del Driver di gestione specifico per il tipo di TS-CNS.

Per trovare il path specifico in base al modello di tessera, utilizziamo il comando `locate`.

* Per modelli ACx 2021, ACe 2021, AC 2013, AC 2014 AC 2018 digitare `locate libbit4xpki.so`;
* Per modelli ID 2019, OT 2015, OT 2016 digitare `locate libbit4opki.so`;
* Per modelli ST 2021 digitare `locate libstpkcs11.so`.

Ora che avete il path completo del modulo, dovete appunto inserirlo nella finestra di Gestione Dispositivi e confermare con **OK**.

Firefox da questo momento indirizzerà tutte le richieste indirizzate al lettore, su quel modulo indicato.

Il sistema è pronto, non dovete fare altro che recarvi nella pagina di pubblica amministrazione alla quale dovete accedere (CUP Web, Fascicolo sanitario ecc) e seguendo la procedura di login, utilizzando CNS, ora il sistema sarà in grado di chiedervi il PIN per sbloccare il token e autorizzarvi ad entrare.

Il gioco è fatto. Sistema Linux configurato per accesso con TS-CNS anche senza gli strumenti obsoleti offerti da regione Sardegna e senza Addon (ormai inutilizzabile).


















