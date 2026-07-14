# 📖 Codebook - Schema dei Metadati / Metadata Schema

Questo documento descrive dettagliatamente la struttura del dataset, definendo le classi, il significato di ciascuna variabile, i valori ammessi, le regole di codifica e i riferimenti agli standard e alle linee guida europee.

<table style="width:100%; border-collapse: collapse; text-align: left;">
  <thead>
    <tr style="background-color: #f2f2f2;">
      <th style="padding: 10px; border: 1px solid #dddddd; width: 12%;">Class</th>
      <th style="padding: 10px; border: 1px solid #dddddd; width: 15%;">Variable Name</th>
      <th style="padding: 10px; border: 1px solid #dddddd; width: 20%;">Description</th>
      <th style="padding: 10px; border: 1px solid #dddddd; width: 15%;">Values</th>
      <th style="padding: 10px; border: 1px solid #dddddd; width: 23%;">Coding Rules</th>
      <th style="padding: 10px; border: 1px solid #dddddd; width: 15%;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">IDENTITÀ</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">festival_id</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">ID alfanumerico strutturato</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">schema: IT-PHO-000</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Generare un ID sequenziale univoco per ciascun festival mappato.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">-</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">festival_name</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Nome del festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">testo</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Utilizzare il nome più ricorrente e ufficiale; evitare sottotitoli se inconsistenti tra le fonti.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">-</td>
    </tr>
    <tr>
      <td rowspan="3" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">INFO</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">city</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Città in cui si svolge il festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">testo</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Utilizzare nomi standardizzati. Inserire esclusivamente la città principale. Nei rari casi di festival multi-sede, la scelta ricade sulla sede legale o sull'hub principale per garantire l'atomicità del dato.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">-</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">region</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Regione italiana in cui si svolge il festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">testo</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Utilizzare denominazioni ufficiali delle regioni italiane.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">-</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">country</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Paese del festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">testo</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Sempre "Italy"; colonna inserita per garantire scalabilità e confronti futuri a livello internazionale.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">-</td>
    </tr>
    <tr>
      <td rowspan="3" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">TEMPORALITÀ</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">festival_edition_start_year</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Anno della prima edizione del festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">anno / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Estrarre l'anno di fondazione o della prima edizione dal sito ufficiale o da fonti storiche affidabili.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;"><a href="https://issuu.com/yourope.org/docs/european_festival_report_2025" target="_blank">YOUROPE Festival Report 2025</a></td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">festival_status</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Stato di attività del festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">active / inactive / defunct / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">
        • <b>active:</b> edizione negli ultimi 18-24 mesi o date future già annunciate.<br>
        • <b>inactive:</b> nessuna edizione negli ultimi 2 anni ma canali social/web ancora online.<br>
        • <b>defunct:</b> dichiarazione ufficiale di chiusura.<br>
        • <b>unknown:</b> mancanza di dati verificabili.
      </td>
      <td style="padding: 10px; border: 1px solid #dddddd;">-</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">duration_days</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Durata del festival in giorni (Stimata)</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">numero / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Si contano sia il giorno d'inizio che di fine (data fine - data inizio + 1). Se le mostre restano aperte un mese dopo il weekend di apertura, si conta l'intero periodo delle mostre. Riferito all'edizione più recente.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;"><a href="https://issuu.com/yourope.org/docs/european_festival_report_2025" target="_blank">YOUROPE Festival Report 2025</a></td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">TEMPORALITÀ (cont.)</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">recurrence</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Ciclicità del festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">annual / biennial / mixed / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">
        • <b>annual:</b> si svolge ogni anno.<br>
        • <b>biennial:</b> regolare ogni due anni.<br>
        • <b>mixed:</b> ha cambiato cadenza nel tempo.<br>
        • <b>unknown:</b> informazioni insufficienti.
      </td>
      <td style="padding: 10px; border: 1px solid #dddddd;">-</td>
    </tr>
    <tr>
      <td rowspan="5" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">DIGITAL PRESENCE</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">website_official</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Sito web ufficiale del festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">URL / null</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Inserire solo l'indirizzo web ufficiale e specifico del festival.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;"><a href="https://doi.org/10.2759/561008" target="_blank">Creative Europe Report (2023)</a></td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">website_secondary</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Sito secondario o istituzionale</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">URL / null</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Inserire l'URL di pagine ospitanti (es. pagina del comune o associazione) solo se non esiste un sito web indipendente.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;"><a href="https://doi.org/10.2759/561008" target="_blank">Creative Europe Report (2023)</a></td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">website_active</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Sito ufficiale aggiornato</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se il sito presenta informazioni su edizioni recenti (ultimi 2 anni); 0 se assente, offline o non aggiornato.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;"><a href="https://doi.org/10.2759/561008" target="_blank">Creative Europe Report (2023)</a></td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">website_languages</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Lingue disponibili sul sito</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">EN / mono / multi</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">
        • <b>EN:</b> presente anche l'inglese oltre l'italiano.<br>
        • <b>mono:</b> solo lingua italiana.<br>
        • <b>multi:</b> presenti altre lingue oltre a italiano e inglese.
      </td>
      <td style="padding: 10px; border: 1px solid #dddddd;"><a href="https://doi.org/10.2759/561008" target="_blank">Creative Europe Report (2023)</a></td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">instagram</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Profilo Instagram ufficiale</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">URL / null</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Inserire l'URL diretto del profilo Instagram ufficiale attivo del festival.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;"><a href="https://doi.org/10.2759/561008" target="_blank">Creative Europe Report (2023)</a></td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">DIGITAL PRESENCE (cont.)</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">facebook</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Pagina Facebook ufficiale</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">URL / null</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Inserire l'URL diretto della pagina Facebook ufficiale attiva del festival.</td>
      <td style="padding: 10px; border: 1px solid #dddddd;"><a href="https://doi.org/10.2759/561008" target="_blank">Creative Europe Report (2023)</a></td>
    </tr>
    <tr>
      <td rowspan="3" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">STRUTTURA ORGANIZZATIVA</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">organizer_type</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Tipologia dell'organizzazione promotrice</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">public / private / non_profit / mixed / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">
        • <b>public:</b> ente della Pubblica Amministrazione.<br>
        • <b>non_profit:</b> Associazione Culturale, APS, fondazione non bancaria.<br>
        • <b>private:</b> entità societaria o commerciale.<br>
        • <b>mixed:</b> co-organizzazione strutturata paritaria.
      </td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Giorgi, L. (2010). Eurofestival Project.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">has_public_funding</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Presenza di finanziamenti pubblici</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1 / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se vi è evidenza di contributi economici pubblici diretti (band
