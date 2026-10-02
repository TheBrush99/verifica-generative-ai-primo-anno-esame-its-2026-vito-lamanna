# Consegna finale della verifica

Il pacchetto contiene un notebook completato ed eseguito per ciascuna parte, con gli output salvati. Per leggere i risultati è sufficiente aprire i notebook; non occorre ripetere l'esecuzione.

- PARTE 1: `Esercizi_parte1.ipynb`.
- PARTE 2: `Esercizi_parte2.ipynb`, i tre testi originali in `texts/` e i risultati in `risultati_parte2/`.
- PARTE 3: `esercizi_parte3.ipynb` e il report `confronto_modelli.txt` richiesto dal task 3.
- `requirements.txt`: dipendenze Python delle tre parti.

## Ripetere le esecuzioni

Ambiente verificato: Python 3.12.10. Sul PC già preparato si può usare il venv della cartella principale. Su un altro PC con Python 3.12, creare un ambiente e installare le dipendenze:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m nltk.downloader punkt punkt_tab
.\.venv\Scripts\python.exe -m ipykernel install --user --name genai-esame --display-name "GenAI - Esame (Python 3.12)"
.\.venv\Scripts\python.exe -m jupyter notebook
```

Aprire ciascun notebook nella propria cartella PARTE 1/2/3, selezionare **GenAI - Esame (Python 3.12)** e scegliere **Riavvia kernel ed esegui tutte le celle**. PARTE 2 legge i testi attraverso il percorso relativo `texts/`, quindi i file devono restare accanto al notebook.

Per PARTE 3 serve anche il programma Ollama, avviato su `localhost:11434`, con questi modelli:

```text
ollama pull llama3.2
ollama pull llama3.2:3b-instruct-q2_K
ollama pull qwen2.5
```

Il pacchetto Python `ollama` non installa il programma o i pesi dei modelli. Sul PC già preparato il servizio e i tre modelli sono disponibili. Gli altri modelli Python vengono scaricati automaticamente alla prima esecuzione se non sono presenti nella cache; occorre quindi una connessione internet. I pesi e il venv non sono inclusi nel pacchetto.

PARTE 2 segue la simulazione didattica Base/SFT/RLHF delle lezioni, con tre copie degli stessi pesi di DistilGPT2. La rubrica qualitativa riporta una revisione delle risposte osservate, senza presentarla come uno studio con annotatori umani indipendenti. I benchmark dell'agente in PARTE 3 sono i dati fittizi forniti dalla traccia; il confronto RAG usa invece i modelli reali. Le risposte generate possono cambiare tra esecuzioni.

Nelle tre tracce non sono specificati formato di caricamento, archivio ZIP o obbligo di allegare un requirements. Questo pacchetto raccoglie i notebook e i file necessari per leggere e ripetere gli esercizi; eventuali istruzioni separate della piattaforma o del docente prevalgono sul formato del pacchetto.
