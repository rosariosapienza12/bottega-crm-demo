# Bottega CRM

Gestionale web per una bottega artigiana: dalla prima richiesta del cliente alla consegna del pezzo e all'incasso.

**▶ Prova la demo: [rosariosapienza12.github.io/bottega-crm-demo](https://rosariosapienza12.github.io/bottega-crm-demo/)**

I dati sono fittizi (una falegnameria immaginaria) e le modifiche restano solo nel tuo browser. Il pulsante "Ripristina dati demo" riporta tutto allo stato iniziale. Funziona da computer e da telefono, con tema chiaro e scuro.

## Funzioni

| Area | Cosa fa |
|---|---|
| Panoramica | Indicatori chiave, grafico incassi e spese degli ultimi 6 mesi, consegne in arrivo, clienti da ricontattare, materiali da riordinare |
| Richieste | Pipeline a colonne con trascinamento; una richiesta confermata diventa una commessa con un clic |
| Preventivatore | Prezzo consigliato da materiali, ore di banco, spese e margine, con il prezzo minimo sotto cui si lavora in perdita |
| Laboratorio | Commesse per fase, registro ore, avvisi di ritardo e sforamento, acconto e saldo, margine reale per commessa |
| Magazzino | Giacenze, scorta minima, avviso di riordino, valore del magazzino |
| Clienti | Gusti, misure, ricorrenze, storico di richieste, commesse e pagamenti |
| Cassa | Incassi e spese per mese, categoria e stato |
| Backup | Scarica tutti i dati in un file e li ripristina, con doppia conferma e una copia dei dati precedenti |

## Regole di calcolo principali

- **Margine reale** = prezzo − (costo materiali + ore lavorate × tariffa oraria)
- **Prezzo del preventivo** = (materiali + ore × tariffa) × (1 + spese %) × (1 + margine %) × (1 + IVA %)
- **Previsione ponderata** = Σ valore della richiesta × probabilità della fase

## Tecnologie

HTML, CSS e JavaScript senza framework, in un unico file. Grafico in SVG disegnato a mano, tema chiaro e scuro con variabili CSS, layout responsive con Grid e Flexbox. I dati passano da un adattatore con due archivi intercambiabili: database cloud oppure `localStorage` del browser.

## Test e sicurezza

- Prove funzionali su tutte le aree: validazione dei moduli, calcoli del preventivo verificati a mano, passaggio richiesta → commessa → incasso, conferma prima di ogni eliminazione.
- Ogni testo inserito dall'utente viene neutralizzato prima di essere mostrato (protezione da XSS); date e fasi vengono validate, e un dato malformato non blocca la pagina.
- Backup e ripristino: il file viene accettato solo se è un backup di Bottega CRM con schede di testo, numeri e valori sì/no; un file manomesso o di altro tipo viene rifiutato per intero, senza toccare i dati.
- Content-Security-Policy restrittiva: la pagina non può caricare script esterni né inviare dati ad altri siti.
- Impaginazione verificata da 320 px (telefoni piccoli) fino a desktop, senza sovrapposizioni né scorrimento laterale.
