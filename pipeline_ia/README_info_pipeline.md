# Pipeline IA

Questa repository contiene la *proof of concept* della pipeline sviluppata per sperimentare la strutturazione semi-automatica di informazioni culturali non strutturate attraverso strumenti di intelligenza artificiale.

La pipeline è stata implementata in **Python**, all'interno di **Google Colab**, e utilizza **Flan-T5 Large**, modello linguistico open source basato sull'architettura T5 e ottimizzato mediante *instruction tuning*.

![Uploading Figura R.png…]()


## Obiettivo

La sperimentazione non mira a sostituire la costruzione manuale del dataset né a valutare le prestazioni assolute del modello linguistico. L'obiettivo è verificare se il *framework* metodologico, il modello dati e il *codebook* definiti nella ricerca possano essere trasferiti a una procedura di estrazione e strutturazione semi-automatica.

Il modello linguistico opera quindi all'interno di uno **schema-guided approach**: le informazioni vengono estratte dal testo e ricondotte alle variabili e alle categorie precedentemente definite nel *codebook*.

## Pipeline

Il processo sperimentale comprende:

1. **Acquisizione controllata delle fonti** — gli URL pertinenti vengono individuati sulla base delle variabili previste dal *codebook*.
2. **Pre-processing** — le pagine web vengono trasformate in testo attraverso operazioni di pulizia e normalizzazione.
3. **Sliding window** — i testi più lunghi vengono suddivisi in porzioni compatibili con i limiti di elaborazione del modello.
4. **Information Extraction** — Flan-T5 Large riceve un *prompt* strutturato contenente il contesto della ricerca, le variabili da estrarre e i valori ammessi per le variabili categoriali.
5. **Normalizzazione e strutturazione** — gli output del modello vengono convertiti in *record* coerenti con il modello dati.
6. **Data enrichment geografico** — le informazioni relative alla località vengono collegate a vocabolari e classificazioni territoriali, tra cui ISTAT e NUTS 2024.
7. **Human-in-the-Loop** — gli output vengono confrontati con il dataset costruito manualmente e sottoposti a verifica e correzione umana.

## Risultato della sperimentazione

La *proof of concept* ha mostrato che l'IA può supportare l'estrazione e la strutturazione di informazioni culturali, soprattutto per attributi esplicitamente presenti nelle fonti. Le maggiori criticità emergono invece quando le variabili richiedono interpretazione contestuale, classificazione semantica o informazioni distribuite tra più fonti.

La pipeline va quindi interpretata come **strumento di supporto alla strutturazione del dato**, non come sistema autonomo di catalogazione. La qualità dell'output dipende dall'interazione tra modello linguistico, schema dati, *prompt*, procedure di normalizzazione e supervisione umana.

Il notebook principale della sperimentazione è:

[proof_of_concept_pipeline.ipynb](https://github.com/annagiacometti/cultural-data-framework-photography-festivals/blob/main/pipeline_ia/proof_of_concept_pipeline.ipynb)
