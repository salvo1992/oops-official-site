# OOPS! — Sito ufficiale e pagine legali

Sito **statico senza framework e senza JavaScript**, pronto per un hosting statico (incluso Vercel).

## File inclusi
- `index.html`: homepage OOPS! con logo dello sviluppatore The Viking of the Web
- `privacy(.html)`, `terms`, `cookies`, `delete-account`, `support`: pagine legali e contatti in italiano
- `*-en.html`: corrispettivi in inglese
- `assets/oops-original-art.webp`: copertina OOPS! scelta per il sito; originale PNG incluso in `assets/oops-original-art.png`
- `assets/oops-game-icon-512.png`: **icona PNG 512×512 più semplice per Google Play**, da verificare sul dispositivo
- `assets/oops-game-icon-1024.png`: icona PNG 1024×1024
- `assets/oops-game-icon.svg`: sorgente vettoriale dell'icona del gioco (creata per questo sito)
- `assets/oops-wordmark.svg` e `.png`: logo orizzontale OOPS!
- `assets/the-viking-of-the-web-logo.png`: logo dello sviluppatore ricavato dal PNG allegato
- `vercel.json`: URL senza estensione (`/privacy` ecc.) e header di sicurezza

## Attenzione — controlli legali obbligatori prima della pubblicazione
1. La pagina Privacy Policy italiana e inglese indica **Salvatore Di Maria** come titolare del trattamento, perché è stato confermato essere la persona fisica che gestisce il gioco. Le altre pagine mantengono **The Viking of the Web** come marchio pubblico. Verificare con un professionista se ulteriori dati o informazioni di contatto sono dovuti in base all’attività svolta.
2. Ho lavorato sui testi forniti dall'utente, NON sul codice Android / Cloudflare backend: **verificare** account, rimozione account, durata dei log, Cloudflare, AdMob, UMP, Google Play Billing, uso del consenso e delle chiavi localStorage. Le informazioni non verificate non vanno pubblicate come certe.
3. Sito statico senza JS, tracking e cookie impostati dal sito. L'hosting può trattare log tecnici autonomamente.
4. La rimozione account deve essere possibile realmente nell'app e tramite richiesta web. La pagina web da sola NON implementa l'eliminazione, ma fornisce email operativa.
5. L'app non è stata modificata. I collegamenti alle pagine legali vanno aggiunti/verificati anche nell'app.
6. Non è stato creato `app-ads.txt`: per evitare un ID fittizio, genera il file con la riga ufficiale restituita da AdMob. Non rinominare il file `.NOT_READY`.

## Pubblicazione su Vercel
**NOTA COMMERCIALE:** Vercel Hobby è riservato all'uso personale non commerciale; se il sito promuove un gioco monetizzato, verifica/usa un piano idoneo (p.es. Pro) oppure un hosting statico con condizioni che consentano progetti commerciali. Fonte: https://vercel.com/docs/plans/hobby

1. Carica la cartella in un repository Git (file `index.html` e `vercel.json` nella root).
2. In Vercel vai su Add New → Project → Import repository Git. Framework: **Other**; build command: nessuno; output: root (`.`).
3. In Project → Settings → Domains aggiungi `oopschaos.com` e `www.oopschaos.com`.
4. In Namecheap → Domain List → Manage → Advanced DNS, sostituisci soltanto i record di parcheggio o redirect incompatibili con i record mostrati specificamente da Vercel. NON cancellare MX, TXT/SPF, DKIM/DMARC usati per la posta.
5. Attendi la verifica DNS/SSL. Verifica che funzionino `https://oopschaos.com/privacy`, `/terms`, `/cookies`, `/delete-account`.
6. Google Play Console → Norme sulla privacy: inserisci `https://oopschaos.com/privacy` soltanto quando la policy è completa e realmente pubblicata.
7. Aggiungi `https://oopschaos.com/delete-account` nell'apposita sezione Google Play se è prevista creazione account.

## DNS
Prendi i **valori esatti dal pannello Vercel**: non usare CNAME o indirizzi IP inventati. La guida ufficiale è https://vercel.com/docs/domains/set-up-custom-domain

## Prova locale
Dalla directory: `python -m http.server 8000`, quindi apri `http://localhost:8000/`. Le pagine con URL pulite `/privacy` richiedono Vercel; in locale puoi aprire `http://localhost:8000/privacy.html`.

## Sicurezza
Nessuna chiave, password o token è richiesta per questo sito. Non caricare mai keystore o backup di firma su hosting pubblico.

## File scaricabili in aggiunta
La copertina originale e le versioni separate dell’icona e dei loghi sono state salvate anche fuori dallo ZIP con nomi semplici.
L’immagine promozionale è stata generata durante il progetto OOPS! in questa conversazione; non proviene da uno stock recuperato dal web. Non si garantisce una esclusività assoluta contro somiglianze con opere terze.

## Aggiornamento del 30 ottobre 2026
La Privacy Policy (IT/EN) è stata corretta per identificare il titolare. Questo archivio va ridistribuito su Vercel **sullo stesso progetto** già collegato al dominio: non è necessario cambiare DNS o ricreare l’app su Play Console. Prima di considerare completata la conformità, verificare il comportamento reale di app, SDK, backend, conservazione e cancellazione account.
