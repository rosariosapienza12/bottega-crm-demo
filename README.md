# Bottega CRM

Gestionale web per una bottega artigiana: dalla prima richiesta del cliente alla consegna del pezzo e all'incasso.

**Demo:** apri `index.html` o la pagina GitHub Pages del repository. I dati sono fittizi (una falegnameria immaginaria) e le modifiche restano solo nel tuo browser.

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

## Regole di calcolo principali

- **Margine reale** = prezzo − (costo materiali + ore lavorate × tariffa oraria)
- **Prezzo del preventivo** = (materiali + ore × tariffa) × (1 + spese %) × (1 + margine %) × (1 + IVA %)
- **Previsione ponderata** = Σ valore della richiesta × probabilità della fase

## Tecnologie

HTML, CSS e JavaScript senza framework, in un unico file. Grafico in SVG disegnato a mano, tema chiaro e scuro con variabili CSS, layout responsive con Grid e Flexbox. I dati passano da un adattatore con due archivi intercambiabili: database cloud oppure `localStorage` del browser.

## Come è stato realizzato

Ho definito il progetto, il dominio e i requisiti, e ho guidato le revisioni. Il codice è stato scritto con Claude Code, un assistente di programmazione basato sull'intelligenza artificiale.
