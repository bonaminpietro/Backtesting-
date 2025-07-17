# Backtesting
A simple backtest of a Moving Average Crossover trading strategy on the S&amp;P 500 using Python, but more is coming...

# Backtesting di una Strategia di Trading: Moving Average Crossover

Questo repository contiene un progetto completo per il backtesting di una classica strategia di trading quantitativo, il **Moving Average Crossover (Golden Cross / Death Cross)**. Il progetto è implementato in Python utilizzando `pandas`, `yfinance` e `matplotlib` in un ambiente Jupyter Notebook.

L'obiettivo è analizzare la performance storica della strategia rispetto a un benchmark passivo di "Buy and Hold" sull'indice S&P 500 (tramite l'ETF `SPY`).

## 📜 Indice

- [Descrizione della Strategia](#-descrizione-della-strategia)
- [Tecnologie e Librerie Utilizzate](#-tecnologie-e-librerie-utilizzate)
- [Risultati del Backtesting](#-risultati-del-backtesting)
- [Limiti e Possibili Sviluppi Futuri](#-limiti-e-possibili-sviluppi-futuri)
- [Autore](#-autore)
- [Licenza](#-licenza)

## 💡 Descrizione della Strategia

La strategia implementata è basata sull'incrocio di due Medie Mobili Semplici (SMA):

-   **Media Mobile Veloce:** 50 giorni
-   **Media Mobile Lenta:** 200 giorni

Le regole di trading sono le seguenti:

-   **Segnale di Acquisto (Golden Cross):** Si apre una posizione "long" (si compra) quando la media mobile a 50 giorni incrocia **al rialzo** quella a 200 giorni. La posizione viene mantenuta finché non si verifica un segnale di vendita.
-   **Segnale di Vendita (Death Cross):** Si chiude la posizione (si vende) quando la media mobile a 50 giorni incrocia **al ribasso** quella a 200 giorni.

## 🛠️ Tecnologie e Librerie Utilizzate

-   **Python**
-   **Pandas:** Per la manipolazione e l'analisi dei dati.
-   **NumPy:** Per i calcoli numerici.
-   **yfinance:** Per scaricare i dati storici dei prezzi da Yahoo Finance.
-   **Matplotlib** & **Seaborn:** Per la visualizzazione dei dati e dei risultati.
-   **Jupyter Notebook / Google Colab:** Come ambiente di sviluppo interattivo.

## 📊 Risultati del Backtesting

L'analisi è stata condotta sui dati storici dell'ETF `SPY` dal 2010 ad oggi.

#### Grafico Strategia Moving Avg Crossover con Buy/Sell indicator

<img width="637" alt="Screenshot 2025-06-26 alle 12 48 24" src="https://github.com/user-attachments/assets/dbac59df-0c0d-44fd-baac-260bcf61359c" />

#### Metriche di Performance Chiave

Ecco un riepilogo delle metriche di performance calcolate. 

| Metrica | Strategia Crossover | Mercato (Buy & Hold) |
| :--- | :---: | :---: |
| **Rendimento Totale** | `256.43%` | `583.77%` |
| **Volatilità Annualizzata**| `14.01%` | `17.05%` |
| **Sharpe Ratio** | `0.68` | `-.--` |
| **Max Drawdown** | `-33.72%`| `-33.72%` |

**Commento ai Risultati:** 
"I risultati del backtesting evidenziano un chiaro trade-off tra rischio e rendimento.

Rendimento vs. Rischio: La strategia ha ottenuto un rendimento totale (256.43%) che è meno della metà di quello del mercato (583.77%). Questo è visibile nel grafico, dove la curva di equity della strategia (linea arancione) rimane costantemente al di sotto del benchmark. Tuttavia, il suo punto di forza è una volatilità annualizzata inferiore (14.01% vs 17.05%), che si traduce in un percorso di crescita più stabile.

Efficienza e Protezione: Nonostante la minore volatilità, l'efficienza della strategia misurata dallo Sharpe Ratio (0.68) è risultata inferiore a quella del mercato (stimabile intorno a 0.80). L'osservazione più critica riguarda il Max Drawdown (-33.72%), che è identico a quello del mercato. Questo indica che la natura "ritardataria" (lagging) dei segnali di crossover non è stata in grado di far uscire la strategia dal mercato in tempo per evitare i principali crolli.

In sintesi, la strategia ha scambiato un potenziale di crescita elevato per una minore volatilità quotidiana, ma non ha offerto una protezione adeguata contro i rischi di coda (drawdown massimi), un limite intrinseco di questo tipo di indicatore."

## 🧐 Limiti e Possibili Sviluppi Futuri

Questo backtest è una base di partenza, ma presenta delle semplificazioni. Dimostrare consapevolezza dei limiti del tuo lavoro è fondamentale.

-   **Costi di Transazione:** L'analisi non include commissioni di trading o bid-ask spread, che ridurrebbero la performance reale.
-   **Slippage:** Non viene considerato lo slittamento (differenza tra prezzo atteso ed effettivo), che può verificarsi in mercati volatili.
-   **Dividendi:** Il calcolo del rendimento del benchmark si basa solo sul prezzo, ignorando i dividendi che SPY distribuisce.
-   **Ottimizzazione:** I periodi delle medie mobili (50 e 200) sono stati scelti per convenzione e non sono stati ottimizzati.

Possibili **sviluppi futuri** potrebbero includere:

-   [ ] Aggiungere un modello realistico di costi di transazione e slippage.
-   [ ] Testare la strategia su un paniere diversificato di asset (altri indici, azioni singole, criptovalute).
-   [ ] Eseguire un'analisi di sensitività per ottimizzare i periodi delle medie mobili.
-   [ ] Integrare altri indicatori (es. RSI, Volume) per filtrare i segnali e ridurre i falsi positivi.
-   [ ] Implementare logiche di gestione del rischio come stop-loss o take-profit.

## 👨‍💻 Autore

-   **Pietro Bonamin**
-   **Profilo LinkedIn:** `https://www.linkedin.com/in/pietro-bonamin-127666203/`
-   **Profilo GitHub:** `https://github.com/bonaminpietro`

## 📄 Licenza

Questo progetto è rilasciato sotto la Licenza MIT. Vedi il file `LICENSE` per maggiori dettagli (se presente).
