# MotionGrid Architect v1.2

Applicazione web interattiva che usa **webcam + MediaPipe Hands** per disegnare e manipolare una griglia di quadrati in tempo reale con i gesti della mano.

## Cosa fa il programma

- Mostra il feed della webcam come sfondo.
- Riconosce fino a **2 mani** contemporaneamente.
- Visualizza uno scheletro della mano con stile "cyber" migliorato con gradienti e glow animati.
- Disegna una griglia (mesh) luminosa sovrapposta.
- Permette di creare, spostare e cancellare quadrati della griglia usando gesti.
- I quadrati attivi hanno effetti visivi migliorati con glow pulsante e angoli evidenziati.
- Mostra indicatori circolari di caricamento quando un gesto richiede una pressione prolungata.

## Gesti da usare

I gesti sono riconosciuti in base alle dita rilevate da MediaPipe.

1. **Pinch (presa pollice + indice)**
- Azione: aggiunge subito un quadrato nella cella della griglia sotto il dito indice.

2. **Pinch mantenuto (~1 secondo)**
- Azione: attiva la modalita disegno continuo.
- Risultato: mentre tieni il pinch, vengono aggiunti quadrati lungo il movimento del dito.
- Feedback visivo: anello di caricamento azzurro.

3. **Pugno (fist)**
- Azione: sposta in blocco tutti i quadrati gia creati.
- Risultato: i quadrati si muovono a "scatti" di cella seguendo lo spostamento del palmo.

4. **Cancellazione (combo a 2 mani)**
- Gesto richiesto: una mano in **pugno** + l'altra in **pinch** mantenuti insieme per ~1.2 secondi.
- Dopo l'attivazione: passa con il dito pinch sui quadrati per eliminarli.
- Feedback visivo: anello rosso durante il caricamento e stato UI rosso in modalita cancellazione.

## Interfaccia

- **Nascondi/Mostra griglia**: alterna la visibilita della mesh luminosa.
- **Cancella quadrati**: mostra un promemoria sul gesto corretto di cancellazione (non elimina direttamente tutti i quadrati).

## Requisiti

- Browser moderno con supporto `getUserMedia`.
- Connessione Internet per caricare le librerie MediaPipe da CDN.