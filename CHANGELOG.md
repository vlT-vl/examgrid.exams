# Changelog

Le funzionalità principali del registro, in ordine cronologico inverso.

## 2026-10-02

- Rinominati gli esami base in `RH066X Fundamentals` e `Proxmox Fundamentals`,
  aggiornando identificativi, percorsi pubblici e permessi di accesso degli utenti
  per lasciare spazio a futuri esami avanzati.

## 2026-10-01

- Corrette 20 chiavi `correctAnswers` dell'esame Nutanix `NCA-7.5` sulla base del
  JSON revisionato `NCA-7.5_corretto.json`, senza modificare testo, opzioni,
  metadati o `answersnumber`.
- Aggiunti `LastUpdate` ai sorgenti degli esami e `lastUpdate` ai nove record del
  manifest pubblico, così la UI può mostrare la data prima della decifratura.
- Aggiunto `primaryLanguage` ai nove esami e al manifest (`it`/`en`); aggiornato
  il generatore locale perché propaghi automaticamente il campo.
- Aggiunto ai profili utente il permesso `canReviewQuestions`, allineato a
  `canRevealAnswers`.
- Aggiunti gli account `davide.locatelli` e `fabio.circiello`; riallineati gli
  accessi ristretti ai tre esami `EG-*`, mantenendo per `giacomo.marcelli` anche
  l'accesso a `2V0-41.24` e limitando `fabio.circiello` a
  `rh066x-fundamentals`.
- Importati gli esami infrastrutturali `S2E-ARUBA-DC` e `S2E-ONPREM-DC`,
  rispettivamente con 180 e 327 quesiti, e aggiunta la categoria `s2e`; CoreDNS
  è trattato esclusivamente nell'esame On-Premises.
- Riscritto il README pubblico per descrivere scopo, struttura, contratto dati e
  modello di accesso della repo.
- Aggiunti strumenti operativi locali, ignorati da Git: report utenti/accessi e
  console voucher autonoma. La console usa un catalogo incorporato sincronizzato
  automaticamente dal generatore, separa emissione e storico e supporta
  importazione/esportazione JSON e file picker nativo quando disponibile.

## 2026-09-30

- Aggiunti ai profili utente i permessi `canRandomizeQuestions` e
  `canChooseRange`, assegnati coerentemente con `canRevealAnswers`.
- Importato l'esame Nutanix `NCA-7.5`, con codice ufficiale preservato, 168
  quesiti e durata di 90 minuti.
- Importati gli esami VMware Cloud Foundation Architect `2V0-13.25` e VMware
  NSX 4.X Professional V2 `2V0-41.24`, entrambi con 115 quesiti e durata di 135
  minuti.
- Riviste con `NSX.xlsx` 18 chiavi di risposta di `2V0-41.24`, senza modificare
  testo e opzioni.
- Rinominate le categorie `linux-redhat` in `redhat` e `vmware-vsphere` in
  `vmware`.
- Aggiunti icona e colore vendor a categorie ed esami nel manifest pubblico.
- Aggiunto `avatarUrl` opzionale ai profili disponibili e rinominato il nome
  visualizzato dell'account `admin` in `Lorenzo Veronesi`.
- Esteso l'accesso a tutto il catalogo, con tutti i permessi, agli account
  `luca.spano`, `matteo.locascio`, `patrick.staccioli` e `christian.grandi`.

## 2026-09-28

- Prima pubblicazione del registro statico con sorgenti locali, envelope cifrati
  e firmati, manifest pubblico e lista utenti/accessi separata.
- Aggiunti gli esami oggi denominati `RH066X Fundamentals`, `vSphereBasics`,
  `Proxmox Fundamentals` e VMware Cloud
  Foundation Administrator `2V0-17.25`.
- Aggiunto `exams/index.json`, generato automaticamente dai sorgenti durante la
  cifratura.
- Introdotto il sistema voucher a tempo per lo sblocco del contenuto degli esami.
- Corretti quesiti e duplicati nei primi esami e configurati accessi realistici
  per account.
- Aggiunti logo dedicato con temi chiaro/scuro e licenza proprietaria
  closed-source.
