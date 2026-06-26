
Analisi Transazioni Finanziarie e Rilevamento Frodi

Descrizione

Terzo progetto del mio percorso in data analytics. Ho scelto un dataset di transazioni finanziarie perché si collega al mio percorso di laurea in banca e finanzia, permettendomi di applicare competenze tecniche a un ambito che già conosco dal punto di vista teorico.


Dataset

Il dataset è composto da diversi file:


transactions_data.csv: le transazioni (data, importo, metodo di pagamento, merchant, ecc.) — file di grandi dimensioni (1.2GB, milioni di righe)
cards_data.csv: dati sulle carte di credito/debito utilizzate
users_data.csv: dati sugli utenti/clienti
mcc_codes (JSON): codici categoria merchant
train_fraud_labels (JSON): etichette che indicano se ogni transazione è fraudolenta (Yes/No)


Fonte: Financial Transactions Dataset: Analytics - Kaggle

Domande di business affrontate


Quali sono i metodi di pagamento più usati nelle transazioni?
Analisi della colonna use_chip per capire la distribuzione tra Swipe, Chip e Online Transaction.

**Qual è l'importo medio delle transazioni?**
Risultato: l'importo medio è di circa $42.98. È stato necessario pulire la colonna amount (rimozione del simbolo $ e conversione da testo a numero) prima del calcolo.

**Quali sono le 5 categorie di merchant (mcc) con più transazioni?**
Analisi di frequenza sulla colonna mcc per identificare i tipi di esercenti più comuni.

**L'importo medio delle transazioni fraudolente è diverso da quello delle transazioni normali?**
Risultato: le transazioni fraudolente hanno un importo medio di $110,23, quasi 3 volte superiore rispetto alle transazioni normali ($42,85). Questo suggerisce che gli importi più alti potrebbero essere un segnale utile per il rilevamento di frodi.

 **Le transazioni Online hanno una percentuale di frode più alta rispetto a Swipe o Chip?**
   Risultato: le transazioni Online hanno una percentuale di frode di circa **0,84%**, molto più alta rispetto a Swipe (**0,03%**) e Chip (circa **0,1%**). Questo, nonostante Swipe sia il metodo con più transazioni totali in assoluto. Suggerisce che le transazioni online meritano controlli antifrode più stringenti.


Tecniche Python/pandas utilizzate


pd.read_csv() per caricare dataset di grandi dimensioni
value_counts() per analizzare la distribuzione di valori categorici
Pulizia dati: .str.replace() e .astype() per convertire colonne testuali in numeriche
Lettura e gestione di file JSON con la libreria json
Trasformazione di un dizionario Python in DataFrame con pd.DataFrame()
merge() per unire le etichette di frode alle transazioni, con gestione di tipi di dato incompatibili (int vs str)
groupby() con mean() per confrontare gruppi diversi (frode vs non frode)


Strumenti


Python (pandas)
Visual Studio Code + Jupyter
Git/GitHub per il versionamento del codice
