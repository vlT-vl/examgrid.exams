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
  `vmware-vsphere` e nell'indice del catalogo.

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
