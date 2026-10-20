# Ph1lly Jam 🎧

**Sito live: https://ph1llyon.github.io/ph1lly-jam/**

Web app gratuita e mobile-first per scegliere insieme la musica durante le uscite con gli amici.
Il proprietario usa Apple Music su iPhone; gli amici (anche su Android) partecipano dal browser,
senza account Apple Music e senza abbonamenti.

## Come funziona
1. Cerca un brano per titolo o artista nel catalogo pubblico Apple (iTunes Search API, nessuna chiave richiesta).
2. Aggiungilo alla lista: copertina, titolo, artista e album.
3. Riordina o rimuovi i brani.
4. Per ascoltare: apri il brano in Apple Music dal link ufficiale e aggiungilo alla coda nell'app Musica.

## Stanza live (v2)
- Dalla sezione **Stanza live** crei una stanza e condividi il **link di invito**: chi lo apre entra automaticamente, senza account.
- La lista si sincronizza **in tempo reale** tra i telefoni collegati: la connessione è diretta da browser a browser (WebRTC, libreria Trystero), senza server e senza database.
- La sincronizzazione funziona mentre la pagina è aperta su almeno un altro telefono della stanza: non c'è un server che conservi la lista quando tutti chiudono.
- Senza stanza, resta il sistema della v1: lista codificata nel link, da condividere a mano dopo ogni modifica.

## Limiti
- Il sito **non** modifica direttamente la coda dell'app Musica su iOS: le API pubbliche di Apple non lo consentono a una web app. L'apertura del brano in Apple Music è manuale.
- Nessun dato viene raccolto da server: la lista vive nei telefoni collegati e nel link condiviso.

## Tecnologie
- Singolo file `index.html` (HTML, CSS e JavaScript vanilla), nessun build, nessun backend.
- Ricerca: endpoint pubblico iTunes Search di Apple (`entity=song`, storefront IT), con incrocio della discografia dell'artista per i brani che la ricerca libera non indicizza.
- Sync live: WebRTC via Trystero (rete pubblica di segnalazione gratuita, dati diretti tra browser).
- Hosting: GitHub Pages da questo repository, branch `main`, cartella root.

## Idee per il futuro
Un player web integrato richiederebbe MusicKit con account Apple Developer a pagamento (token sviluppatore): scartato per mantenere il progetto a costo zero.

Progetto indipendente, non affiliato ad Apple.
