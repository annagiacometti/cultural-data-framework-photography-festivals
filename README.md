# Cultural Data Structuring Framework & AI Pipeline
### *Caso Studio: Dataset dei Festival Fotografici Italiani / Case Study: Italian Photography Festivals Dataset*

---

## IT

### Panoramica del Progetto
Questo repository raccoglie i risultati pratici, metodologici e di codice legati a un progetto di tesi in **Digital Humanities** (Università degli Studi di Palermo) dedicato alla **raccolta, strutturazione e normalizzazione dei dati culturali eterogenei disponibili sul web**.

L'obiettivo principale è trasformare informazioni culturali frammentate e non strutturate (siti web, social media, documentazione sparsa) in **dataset aperti, confrontabili, riutilizzabili e conformi agli standard di metadati europei** (*Eurostat, ESSnet-Culture, Creative Europe, Eurobarometer*).

> **Note:** Il progetto e la relativa ricerca di tesi sono attualmente **in fase di completamento ed evoluzione**. I dati e il codice vengono aggiornati e validati in tempo reale.

---

### Struttura della Directory e Output del Progetto

Il progetto si articola in tre output fondamentali:

1. **`codebook.md` (Framework di Metadati su Base Europea):**
   * Schema metodologico e dizionario dei dati sviluppato a partire dalle direttive europee per i beni culturali.
   * Definisce le classi logiche, le regole di codifica, le tipologie di variabili e i vincoli di validazione dei dati.
2. **`dataset/` (Dataset dei Festival Fotografici Italiani):**
   * Mappatura censuaria e storicizzata applicata ai festival fotografici italiani attivi, inattivi o conclusi (*defunct*).
   * Focus primario: festival con la fotografia come tema centrale e prevalente della programmazione.
   * Accessibile in tempo reale via Google Sheets o mediante esportazione diretta dinamica `.csv` e `.xlsx`.
3. **`pipeline_ia/` (Prototipo AI per l'Estrazione Dati):**
   * Notebook in Python (Jupyter / Google Colab) per l'automatizzazione intelligente dell'estrazione e normalizzazione di dati culturali non strutturati dal web.
   * Sperimentazione di modelli LLM/NLP (es. *Flan T5-Large*) con approcci *Zero-Shot* e *Few-Shot + Sliding Window*, integrati in un workflow *Human-in-the-Loop*.

---

## EN

### Project Overview
This repository hosts the practical, methodological, and computational outputs of a **Digital Humanities** thesis project (University of Palermo) focused on the **collection, structuring, and standardization of heterogeneous online cultural data**.

The core goal is to transform fragmented and unstructured cultural information scattered across the web (websites, social media, documentation) into **open, comparable, and reusable datasets aligned with European metadata standards** (*Eurostat, ESSnet-Culture, Creative Europe, Eurobarometer*).

> **Note:** The thesis research and dataset population are currently **ongoing and evolving in real-time**. Data and scripts are continuously updated and validated.

---

### Repository Structure & Key Outputs

The project delivers three main integrated components:

1. **`Codebook.md` (EU-Aligned Metadata Framework):**
   * A methodological schema and data dictionary modeled after European cultural policy frameworks.
   * Defines logical classes, coding guidelines, variable types, and validation constraints.
2. **`dataset/` (Italian Photography Festivals Dataset):**
   * A census-based, historical mapping of active, inactive, and defunct Italian photography festivals.
   * Strictly targets events where photography serves as the primary theme of programming.
   * Accessible live via Google Sheets or via direct dynamic `.csv` / `.xlsx` exports.
3. **`pipeline_ia/` (AI Pipeline for Data Extraction):**
   * Executable Python Notebooks (Jupyter / Google Colab) demonstrating AI-assisted automated extraction and normalization of unstructured web content.
   * Features experiments with LLMs (e.g., *Flan T5-Large*) using *Zero-Shot* and *Few-Shot + Sliding Window* strategies within a *Human-in-the-Loop* validation design.

---

## Link Rapidi e Accesso ai Dati / Quick Links

* 📖 **[Leggi il Codebook / Read the Codebook]([dataset/Codebook.md](https://github.com/annagiacometti/cultural-data-framework-photography-festivals/blob/5a93e982f385b03bdb97fe0b97575840543889e3/dataset/Codebook.md))**
* 🌐 **[Esplora il Dataset Live su Google Sheets / Live Interactive Sheet](https://docs.google.com/spreadsheets/d/1Mqnbuf3mBJQ5Z3N5Tah1VuAr0akWJmj9OtJMr6WqqB4/edit?gid=822136368#gid=822136368)**
* 📥 **[Scarica il Dataset Live (.CSV) / Direct CSV Export](https://docs.google.com/spreadsheets/d/1Mqnbuf3mBJQ5Z3N5Tah1VuAr0akWJmj9OtJMr6WqqB4/export?format=csv&gid=822136368)**
* 📥 **[Scarica il Dataset Live (.XLSX) / Direct Excel Export](https://docs.google.com/spreadsheets/d/1Mqnbuf3mBJQ5Z3N5Tah1VuAr0akWJmj9OtJMr6WqqB4/export?format=xlsx&gid=822136368)**
* 🛠️ **[Apri il Notebook IA su Google Colab / Open AI Pipeline](./pipeline_ia/)**

---

## Autrice / Author
**Anna Giacometti**  
Laureanda in Digital Humanities – Università degli Studi di Palermo[cite: 1]  
🔗 Repository GitHub: [photography-festivals-dataset](https://github.com/annagiacometti/photography-festivals-dataset.git)
