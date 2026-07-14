# 📖 Codebook - Schema dei Metadati / Metadata Schema

Questo schema dei metadati definisce l'architettura dei dati utilizzata per la strutturazione del dataset. Le variabili e le classi qui descritte sono state modellate a partire dai principali regolamenti, linee guida e documentazioni ufficiali dell'Unione Europea nell'ambito del patrimonio, delle statistiche e delle politiche culturali (tra cui *Eurostat, ESSnet-Culture* e *Creative Europe*).

Sebbene nel presente framework tali metriche siano applicate verticalmente alla mappatura e normalizzazione dei festival fotografici italiani (caso studio), l'intera architettura dell'informazione è stata progettata secondo criteri di modularità e flessibilità. Ciò rende il modello completamente scalabile e replicabile per la catalogazione di qualsiasi altra tipologia di festival o evento culturale sul web.

La tabella seguente descrive nel dettaglio il dizionario dei dati: definisce le classi logiche, i vincoli di tipo delle variabili, i valori ammessi, le regole rigorose di codifica (utilizzate anche per la validazione degli output dell'IA) e le relative fonti istituzionali di riferimento.

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
    <!-- IDENTITÀ -->
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
    <!-- INFO -->
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
    <!-- TEMPORALITÀ -->
    <tr>
      <td rowspan="3" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">TEMPORALITÀ</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">festival_edition_start_year</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Anno della prima edizione del festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">anno / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Estrarre l'anno di fondazione o della prima edizione dal sito ufficiale o da fonti storiche affidabili.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">YOUROPE & ILMC. (2026). <a href="https://issuu.com/yourope.org/docs/european_festival_report_2025" target="_blank"><i>European Festival Report 2025</i></a>. IQ Magazine.</td>
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
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">YOUROPE & ILMC. (2026). <a href="https://issuu.com/yourope.org/docs/european_festival_report_2025" target="_blank"><i>European Festival Report 2025</i></a>. IQ Magazine.</td>
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
    <!-- DIGITAL PRESENCE -->
    <tr>
      <td rowspan="5" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">DIGITAL PRESENCE</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">website_official</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Sito web ufficiale del festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">URL / null</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Inserire solo l'indirizzo web ufficiale e specifico del festival.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">European Commission. (2023). <a href="https://doi.org/10.2759/561008" target="_blank"><i>Creative Europe 2021-2022: Monitoring report</i></a>. Publications Office of the EU.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">website_secondary</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Sito secondario o istituzionale</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">URL / null</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Inserire l'URL di pagine ospitanti (es. pagina del comune o associazione) solo se non esiste un sito web indipendente.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">European Commission. (2023). <a href="https://doi.org/10.2759/561008" target="_blank"><i>Creative Europe 2021-2022: Monitoring report</i></a>. Publications Office of the EU.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">website_active</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Sito ufficiale aggiornato</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se il sito presenta informazioni su edizioni recenti (ultimi 2 anni); 0 se assente, offline o non aggiornato.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">European Commission. (2023). <a href="https://doi.org/10.2759/561008" target="_blank"><i>Creative Europe 2021-2022: Monitoring report</i></a>. Publications Office of the EU.</td>
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
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">European Commission. (2023). <a href="https://doi.org/10.2759/561008" target="_blank"><i>Creative Europe 2021-2022: Monitoring report</i></a>. Publications Office of the EU.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">instagram</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Profilo Instagram ufficiale</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">URL / null</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Inserire l'URL diretto del profilo Instagram ufficiale attivo del festival.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">European Commission. (2023). <a href="https://doi.org/10.2759/561008" target="_blank"><i>Creative Europe 2021-2022: Monitoring report</i></a>. Publications Office of the EU.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">DIGITAL PRESENCE (cont.)</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">facebook</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Pagina Facebook ufficiale</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">URL / null</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Inserire l'URL diretto della pagina Facebook ufficiale attiva del festival.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">European Commission. (2023). <a href="https://doi.org/10.2759/561008" target="_blank"><i>Creative Europe 2021-2022: Monitoring report</i></a>. Publications Office of the EU.</td>
    </tr>
    <!-- STRUTTURA ORGANIZZATIVA -->
    <tr>
      <td rowspan="3" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">STRUTTURA ORGANIZZATIVA</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">organizer_type</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Tipologia dell'organisation promotrice</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">public / private / non_profit / mixed / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">
        • <b>public:</b> ente della Pubblica Amministrazione.<br>
        • <b>non_profit:</b> Associazione Culturale, APS, fondazione non bancaria.<br>
        • <b>private:</b> entità societaria o commerciale.<br>
        • <b>mixed:</b> co-organizzazione strutturata paritaria.
      </td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Giorgi, L. (Ed.). (2010). <a href="https://www.academia.edu/21774168/European_Arts_Festivals_Cultural_Pragmatics_and_Discursive_The_S%C3%B3nar_Festival" target="_blank"><i>European Arts Festivals: Cultural Pragmatics and Discursive Identity Frames</i></a>. European Commission.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">has_public_funding</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Presenza di finanziamenti pubblici</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1 / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se vi è evidenza di contributi economici pubblici diretti (bandi, fondi FUS, sponsorizzazioni di enti locali); 0 se assenti. Usare "unknown" se compare solo un patrocinio gratuito senza certezza di fondi.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Giorgi, L. (Ed.). (2010). <a href="https://www.academia.edu/21774168/European_Arts_Festivals_Cultural_Pragmatics_and_Discursive_The_S%C3%B3nar_Festival" target="_blank"><i>European Arts Festivals: Cultural Pragmatics and Discursive Identity Frames</i></a>. European Commission.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">has_international_orientation</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Presenza di partner o reti internazionali</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1 / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se l'open call è esplicitamente bilingue e aperta a fotografi di ogni nazionalità, o se vi sono partner e scambi internazionali espliciti; 0 se la call e la comunicazione sono unicamente rivolte al territorio locale/nazionale.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Giorgi, L. (Ed.). (2010). <a href="https://www.academia.edu/21774168/European_Arts_Festivals_Cultural_Pragmatics_and_Discursive_The_S%C3%B3nar_Festival" target="_blank"><i>European Arts Festivals: Cultural Pragmatics and Discursive Identity Frames</i></a>. European Commission.</td>
    </tr>
    <!-- CONTENUTI CULTURALI -->
    <tr>
      <td rowspan="5" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">CONTENUTI CULTURALI</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">has_mixed_visual_arts</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Presenza di altre arti visive</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se il festival non espone solo fotografia, ma integra programmaticamente altre arti plastiche o visive (pittura, scultura, arte contemporanea, graphic design, illustrazione).</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Bína, V. et al. (2012). <a href="https://policycommons.net/artifacts/2053334/essnet-culture-final-technical-report/2806425/" target="_blank"><i>ESSnet-Culture: European Statistical System Network on Culture. Final Report</i></a>. Eurostat.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">has_books_press</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Presenza di attività editoriali</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se il festival ospita una sezione dedicata all'oggetto-libro, all'editoria fotografica o ai fanzine (bookshop specializzato, presentazioni di libri, premi dummy, ecc.).</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Bína, V. et al. (2012). <a href="https://policycommons.net/artifacts/2053334/essnet-culture-final-technical-report/2806425/" target="_blank"><i>ESSnet-Culture: European Statistical System Network on Culture. Final Report</i></a>. Eurostat.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">has_architecture</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Contenuti legati all'architettura</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se il festival affronta esplicitamente e programmaticamente il tema dell'architettura, dello spazio costruito, del design urbano o del paesaggio modificato.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Bína, V. et al. (2012). <a href="https://policycommons.net/artifacts/2053334/essnet-culture-final-technical-report/2806425/" target="_blank"><i>ESSnet-Culture: European Statistical System Network on Culture. Final Report</i></a>. Eurostat.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">has_performing_arts</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Presenza di attività performative</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se sono presenti performance dal vivo che coinvolgono la presenza fisica dell'artista (teatrali, danza, performance art, live music di accompagnamento).</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Bína, V. et al. (2012). <a href="https://policycommons.net/artifacts/2053334/essnet-culture-final-technical-report/2806425/" target="_blank"><i>ESSnet-Culture: European Statistical System Network on Culture. Final Report</i></a>. Eurostat.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">has_audiovisual</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Presenza di contenuti audiovisivi</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se il festival include installazioni multimediali, proiezioni video stabili, utilizzo di realtà aumentata (AR), realtà virtuale (VR) o contenuti video-artistici interattivi.</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Bína, V. et al. (2012). <a href="https://policycommons.net/artifacts/2053334/essnet-culture-final-technical-report/2806425/" target="_blank"><i>ESSnet-Culture: European Statistical System Network on Culture. Final Report</i></a>. Eurostat.</td>
    </tr>
    <!-- SPAZIO -->
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">SPAZIO</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">venue_type</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Tipologia principale degli spazi utilizzati</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">museum_gallery / cultural_space / historic_site / public_space / mixed / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Classificare in base alla funzione d'uso prevalente dello spazio espositivo (es. spazi urbani all'aperto = <i>public_space</i>; palazzi storici non musealizzati = <i>historic_site</i>).</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">Alberti, V. et al. (2024). <a href="https://doi.org/10.1007/978-981-99-3236-8_1" target="_blank"><i>Ontology Engineering to Model the European Cultural Heritage: The Case of Cultural Gems</i></a>. Springer.</td>
    </tr>
    <!-- POLICIES / CONTESTO -->
    <tr>
      <td rowspan="3" style="padding: 10px; border: 1px solid #dddddd; font-weight: bold; vertical-align: top; background-color: #fafafa;">POLICIES / CONTESTO</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">ticket_policy</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Modalità di accesso al festival</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">free / paid / mixed / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">
        • <b>free:</b> tutte le mostre e attività sono gratuite.<br>
        • <b>paid:</b> l'accesso al corpo centrale richiede l'acquisto di un pass/biglietto.<br>
        • <b>mixed:</b> combinazione significativa di mostre a pagamento e incontri gratuiti.
      </td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">European Commission. (2025). <a href="https://europa.eu/eurobarometer/surveys/detail/3364" target="_blank"><i>Europeans’ Attitudes towards Culture. Special Eurobarometer</i></a>. DG EAC.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">sustainability_claim</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Comunicazione esplicita d'impegno ecologico</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">0 / 1 / unknown</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">1 se vi è una pagina/dichiarazione sul sito dedicata alle politiche ecologiche (plastic-free, compensazione CO2, mobilità sostenibile); 0 se assente. La codifica "0" indica solo l'assenza di comunicazione ufficiale, non che il festival adotti comportamenti negativi (evitare bias).</td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">YOUROPE & ILMC. (2026). <a href="https://issuu.com/yourope.org/docs/european_festival_report_2025" target="_blank"><i>European Festival Report 2025</i></a>. IQ Magazine.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #dddddd; font-family: monospace;">digital_presence_score</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">Punteggio calcolato di presenza digitale</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">numero intero, 0-10</td>
      <td style="padding: 10px; border: 1px solid #dddddd;">
        
Canale Web (Max 4pt):
- Sito ufficiale presente: 2pt
- Sito ufficiale anche ATTIVO (website_active = 1): +2pt (Totale 4pt)
- Sito ufficiale NON attivo (website_active = 0): +0pt (Rimane a 2pt)
- Solo sito secondario (o nessun sito): 0pt

Social (Max 4pt):
- Instagram dedicato = 2pt
- Facebook dedicato = 2pt

Lingue (Max 2pt):
- Multilingue = 2pt
- Inglese (su sito attivo o secondario) = 1pt
- Solo italiano = 0pt
      </td>
      <td style="padding: 10px; border: 1px solid #dddddd; font-size: 0.85em;">European Commission. (2025). <a href="https://europa.eu/eurobarometer/surveys/detail/3364" target="_blank"><i>Europeans’ Attitudes towards Culture. Special Eurobarometer</i></a>. DG EAC.</td>
    </tr>
  </tbody>
</table>
