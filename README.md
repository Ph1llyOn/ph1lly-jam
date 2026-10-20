# Ph1lly Jam 🎧

**Sito live: https://ph1llyon.github.io/ph1lly-jam/**

Web app gratuita e mobile-first per scegliere insieme la musica durante le uscite con gli amici.
Il proprietario usa Apple Music su iPhone; gli amici (anche su Android) partecipano dal browser,
senza account Apple Music e senza abbonamenti.

## Come funziona
1. Cerca un brano per titolo o artista nel catalogo pubblico Apple (iTunes Search API, nessuna chiave richiesta).
2. Aggiungilo alla lista: copertina, titolo, artista e album.
3. Riordina o rimuovi i brani, poi premi **Condividi lista** e manda il link agli altri.
4. Chi riceve il link vede la lista e può aggiungere brani e condividere il link aggiornato.
5. Per ascoltare: apri il brano in Apple Music dal link ufficiale e aggiungilo alla coda nell'app Musica.

## Limiti della versione attuale (beta)
- La lista è codificata nell'URL condiviso, non salvata su un server: ogni modifica richiede di condividere di nuovo il link aggiornato. **Non c'è sincronizzazione in tempo reale.**
- Il sito **non** modifica direttamente la coda dell'app Musica su iOS: le API pubbliche di Apple non lo consentono a una web app. L'apertura del brano in Apple Music è manuale.
- Nessun dato viene raccolto o salvato: la lista vive solo nel link.

## Tecnologie
- Singolo file `index.html` (HTML, CSS e JavaScript vanilla), nessun build, nessun backend.
- Ricerca: endpoint pubblico iTunes Search di Apple (`entity=song`, storefront IT).
- Hosting: GitHub Pages da questo repository, branch `main`, cartella root.

## Versione 2 — idee per una vera coda in tempo reale
Per sincronizzare la lista tra i telefoni in tempo reale servirebbe un backend sempre attivo
con un canale live (es. WebSocket su un piccolo server auto-ospitato) o un database realtime.
Il controllo diretto della coda nativa di Apple Music resterebbe comunque fuori portata per una
web app: la riproduzione dovrebbe passare da un player web MusicKit (richiede account Apple
Developer a pagamento per il token) oppure restare manuale come in questa versione.

Progetto indipendente, non affiliato ad Apple.
