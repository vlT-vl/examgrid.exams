# Changelog

Le funzionalità principali del registro, in ordine cronologico inverso.

## 2026-09-30

- Aggiunti ai profili utente i permessi `canRandomizeQuestions` e
  `canChooseRange`, assegnati coerentemente con `canRevealAnswers`.
- Importato l'esame Nutanix `NCA-7.5`, con il codice ufficiale preservato,
  aggiunto alla categoria `nutanix` e all'indice del catalogo.
- Categoria `linux-redhat` rinominata in `redhat` (solo l'identificativo, il
  contenuto degli esami non cambia).
- Icona e colore di ogni categoria ora seguono il logo del vendor reale
  (Red Hat, Nutanix, Proxmox, VMware) invece di un'icona generica: nuovo
  campo opzionale `color` accanto a `icon`, sia a livello di categoria sia
  di singolo esame nell'indice del catalogo.
- Importato l'esame VMware Cloud Foundation Architect `2V0-13.25`, con codice
  ufficiale preservato, 115 domande e durata di 135 minuti, nella categoria
  `vmware` e nell'indice del catalogo.
- Categoria `vmware-vsphere` rinominata in `vmware` (solo l'identificativo,
  il contenuto degli esami non cambia).
- Aggiunta la foto profilo per 7 dei 8 account (link diretto, nessun file caricato nel
  registro); chi non ne ha una resta con l'icona generica come prima.
- Account `admin` rinominato con il nome nominale del titolare invece della generica "Admin".
- Importato l'esame VMware NSX 4.X Professional V2 `2V0-41.24`, con codice
  ufficiale preservato, 115 quesiti e durata di 135 minuti, nella categoria
  `vmware`; le chiavi restano quelle del PDF in attesa della revisione XLS.
- Riviste con `NSX.xlsx` le chiavi di risposta di `2V0-41.24`: aggiornati 18
  quesiti, lasciati invariati gli altri e mantenuti i refusi testuali delle
  opzioni non pertinenti alla sola revisione delle chiavi.
- Accesso esteso a tutto il catalogo (con tutti i permessi) per gli account
  `luca.spano`, `matteo.locascio`, `patrick.staccioli` e `christian.grandi`.

## 2026-10-01

- Corrette 20 chiavi `correctAnswers` dell'esame Nutanix `NCA-7.5` sulla base del
  JSON revisionato `NCA-7.5_corretto.json`, senza modificare testo, opzioni,
  metadati o `answersnumber` delle domande.
- Aggiunto il campo statico `LastUpdate` ai sette JSON degli esami, con la data
  concordata dell'ultimo aggiornamento del dump.
- Aggiunto ai profili utente il permesso `canReviewQuestions`, allineato a
  `canRevealAnswers`, per consentire al portale di gestire la review finale.
- Aggiunto l'account `davide.locatelli`, con foto profilo, accesso ai soli esami
  `EG-*` e tutte le permission del portale.
- Aggiunti sotto `tools/` (ignorati da Git) il report privato utenti/accessi e la
  console voucher statica compatibile con il protocollo di emissione locale.
- Il report privato utenti/accessi è stato spostato nella root del progetto e
  aggiunto al `.gitignore`; la console resta sotto `tools/`.
- Gli utenti con accesso ristretto sono stati uniformati ai tre esami `EG-*`;
  `giacomo.marcelli` ha inoltre ricevuto `2V0-41.24`.
- Rimossa la cartella vuota `tools/backup/`; gli script la ricreano automaticamente
  solo quando devono salvare una chiave durante una rotazione.
- La console voucher locale ora evita il caricamento `file://` soggetto a CORS tramite
  `voucher-console.command`, espone sempre lo stato Web Crypto, pagina lo storico e consente
  di eliminare le voci riscrivendo il JSON locale quando disponibile; la favicon usa il solo
  simbolo quadrato `res/examgrid.svg`, senza wordmark.
- La console voucher è stata resa autonoma: nessun server o comando da avviare, configurazione
  JSON incorporata in testa alla pagina, storico in `localStorage` ed esportazione manuale JSON.
- Ripristinati il logo SVG ufficiale `examgrid-exams` e la favicon con la sola icona `examgrid`;
  lo storico supporta importazione JSON, aggiornamento automatico e download del file aggiornato.
- L'esportazione dello storico apre il selettore nativo di percorso/nome tramite
  `showSaveFilePicker` quando il browser lo supporta, con fallback al download standard.
- Pubblicato `lastUpdate` anche nell'indice `exams/index.json` per tutti gli esami, così la UI
  può mostrare la data senza sbloccare o decifrare il file delle domande.

## 2026-09-28

- Prima pubblicazione del registro: struttura a macrocategorie sotto
  `exams/`, esami e lista utenti/accessi pubblicati in forma cifrata.
- Aggiunti i primi due esami: `linux-redhat` e `vmware-vsphere`.
- Aggiunto un terzo esame, `proxmox`, accanto ai due iniziali.
- Aggiunto `exams/index.json`: l'indice del catalogo con titolo,
  categoria, durata e numero di domande di ogni esame.
- Corrette alcune imprecisioni nelle domande e risposte degli esami
  esistenti.
- Ampliata la lista utenti con nuovi account e i relativi permessi di
  accesso agli esami.
- Aggiunto il logo dedicato del registro in cima al README, con
  supporto al tema chiaro/scuro di GitHub.
- Licenza aggiornata a closed-source.
- Introdotto un sistema di voucher a tempo per la decifratura del contenuto degli esami, pubblicati in forma cifrata separatamente dalla lista utenti.
- Permessi di accesso agli esami resi realistici per ogni utenza (non più accesso indiscriminato a tutto il catalogo).
