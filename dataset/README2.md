<table>
<thead>
<tr>
<th>Class</th>
<th>Variable name</th>
<th>Description</th>
<th>Values</th>
<th>Coding rules</th>
<th>Source</th>
</tr>
</thead>

<tbody>

<tr>
<td rowspan="2">IDENTITY</td>
<td>festival_id</td>
<td>Identificativo alfanumerico del festival</td>
<td>Schema: IT-PHO-000001</td>
<td>ID univoco assegnato al record del festival</td>
<td>-</td>
</tr>

<tr>
<td>festival_name</td>
<td>Nome del festival</td>
<td>Testo</td>
<td>Utilizzare il nome più ricorrente e ufficiale; evitare sottotitoli se inconsistenti tra le fonti</td>
<td>-</td>
</tr>


<tr>
<td rowspan="5">LOCATION</td>
<td>city</td>
<td>Città in cui si svolge il festival</td>
<td>Denominazioni ufficiali ISTAT</td>
<td>Inserire esclusivamente la città principale. Nei rari casi di festival multi-sede, scegliere la sede legale o l'hub principale. Indicare nelle note eventuali altre sedi o carattere itinerante.</td>
<td>-</td>
</tr>

<tr>
<td>city_geonames_id</td>
<td>Codice identificativo della città secondo GeoNames</td>
<td>Codice numerico</td>
<td>-</td>
<td>GeoNames</td>
</tr>

<tr>
<td>region</td>
<td>Regione italiana in cui si svolge il festival</td>
<td>Denominazioni ufficiali ISTAT</td>
<td>-</td>
<td>-</td>
</tr>

<tr>
<td>region_nuts</td>
<td>Regione italiana rappresentata come codice NUTS</td>
<td>Codice NUTS2 (Eurostat)</td>
<td>-</td>
<td>Eurostat NUTS classification</td>
</tr>

<tr>
<td>country_iso</td>
<td>Paese in cui si svolge il festival</td>
<td>ISO 3166-1 alpha-2</td>
<td>Codice paese per garantire scalabilità futura</td>
<td>ISO</td>
</tr>


<tr>
<td rowspan="4">TIME</td>
<td>festival_edition_start_year</td>
<td>Anno della prima edizione del festival</td>
<td>Anno / unknown</td>
<td>Estrarre da sito ufficiale o fonti affidabili</td>
<td>YOUROPE – The European Festival Association &amp; ILMC (2026). European Festival Report 2025.</td>
</tr>

<tr>
<td>festival_status</td>
<td>Stato di attività del festival al momento della raccolta dati</td>
<td>active / inactive / defunct / unknown</td>
<td>
<b>active:</b> edizione negli ultimi 18-24 mesi oppure date/open call future annunciate.<br>
<b>inactive:</b> nessuna edizione negli ultimi 2 anni, ma canali online ancora presenti.<br>
<b>defunct:</b> chiusura dichiarata ufficialmente.<br>
<b>unknown:</b> dati insufficienti o contrastanti.
</td>
<td>-</td>
</tr>

<tr>
<td>duration_days</td>
<td>Durata del festival in giorni</td>
<td>Numero / unknown</td>
<td>
Conteggio inclusivo del giorno iniziale e finale.<br>
Se le mostre rimangono aperte oltre l'evento inaugurale viene considerato l'intero periodo.<br>
Viene utilizzata l'edizione più recente.
</td>
<td>YOUROPE – The European Festival Association &amp; ILMC (2026). European Festival Report 2025.</td>
</tr>

<tr>
<td>recurrence</td>
<td>Ciclicità del festival</td>
<td>annual / biennial / mixed / unknown</td>
<td>
annual: ogni anno.<br>
biennial: ogni due anni.<br>
mixed: variazione della frequenza nel tempo.<br>
unknown: informazioni insufficienti.
</td>
<td>-</td>
</tr>


<tr>
<td rowspan="6">DIGITAL PRESENCE</td>
<td>website_official</td>
<td>Sito web ufficiale del festival</td>
<td>URL / null</td>
<td>Inserire esclusivamente il sito ufficiale</td>
<td>European Commission (2023). Creative Europe 2021-2022: Monitoring report.</td>
</tr>

<tr>
<td>website_secondary</td>
<td>Sito secondario o istituzionale contenente informazioni sul festival</td>
<td>URL / null</td>
<td>Inserire solo quando non esiste un sito ufficiale</td>
<td>European Commission (2023). Creative Europe 2021-2022: Monitoring report.</td>
</tr>

<tr>
<td>website_active</td>
<td>Presenza di un sito ufficiale aggiornato</td>
<td>0 / 1</td>
<td>
1: sito aggiornato con edizioni recenti.<br>
0: sito non aggiornato o assente.
</td>
<td>European Commission (2023). Creative Europe 2021-2022: Monitoring report.</td>
</tr>

<tr>
<td>website_languages</td>
<td>Lingue disponibili sul sito ufficiale o secondario</td>
<td>IT_EN / IT_ONLY / MULTI</td>
<td>
IT_EN: italiano + inglese.<br>
IT_ONLY: solo italiano.<br>
MULTI: italiano, inglese e altre lingue.
</td>
<td>European Commission (2023). Creative Europe 2021-2022: Monitoring report.</td>
</tr>

<tr>
<td>instagram</td>
<td>Profilo Instagram ufficiale del festival</td>
<td>URL / null</td>
<td>Inserire esclusivamente profilo ufficiale</td>
<td>European Commission (2023). Creative Europe 2021-2022: Monitoring report.</td>
</tr>

<tr>
<td>facebook</td>
<td>Pagina Facebook ufficiale del festival</td>
<td>URL / null</td>
<td>Inserire esclusivamente pagina ufficiale</td>
<td>European Commission (2023). Creative Europe 2021-2022: Monitoring report.</td>
</tr>

</tbody>
</table>

<tbody>

<tr>
<td rowspan="1">DIGITAL PRESENCE</td>
<td>digital_presence_score</td>
<td>Punteggio sintetico della presenza digitale del festival</td>
<td>Numero intero 0-10</td>
<td>
<b>Canale Web (max 4 punti):</b><br>
- Sito ufficiale presente: +2<br>
- Sito ufficiale attivo (website_active = 1): +2<br>
- Sito ufficiale non attivo (website_active = 0): +0<br>
- Solo sito secondario o nessun sito: 0<br><br>

<b>Social (max 4 punti):</b><br>
- Instagram dedicato: +2<br>
- Facebook dedicato: +2<br><br>

<b>Lingue (max 2 punti):</b><br>
- MULTI: +2<br>
- IT_EN: +1<br>
- IT_ONLY: 0
</td>
<td>
European Commission (2025). Directorate-General for Education, Youth, Sport and Culture. Europeans’ Attitudes towards Culture. Special Eurobarometer.
</td>
</tr>


<tr>
<td rowspan="4">ORGANIZATION</td>
<td>organizer_type</td>
<td>Tipologia dell’organizzazione che promuove il festival. Natura giuridica dell'organizzatore.</td>
<td>public / private / non_profit / unknown / mixed</td>
<td>
public: organizzatore appartenente alla Pubblica Amministrazione.<br>
non_profit: associazione culturale, fondazione culturale non bancaria, organizzazione di volontariato o promozione sociale.<br>
private: entità commerciale.<br>
mixed: presenza di più categorie organizzative.
</td>
<td>
Giorgi, L. (Ed.). (2010). European Arts Festivals: Cultural Pragmatics and Discursive Identity Frames (EURO-FESTIVAL).
</td>
</tr>


<tr>
<td>has_documented_public_funding</td>
<td>Presenza di finanziamenti pubblici documentati online</td>
<td>0 / 1</td>
<td>
1: presenza di evidenza documentata di contributi economici pubblici.<br>
0: assenza di evidenza o presenza esclusiva di patrocinio.
</td>
<td>
Giorgi, L. (Ed.). (2010). European Arts Festivals: Cultural Pragmatics and Discursive Identity Frames.
</td>
</tr>


<tr>
<td>has_international_call</td>
<td>Presenza di open call internazionale</td>
<td>0 / 1</td>
<td>
1: open call aperta a fotografi di ogni nazionalità.<br>
0: open call limitata a cittadini italiani o assente.
</td>
<td>
Giorgi, L. (Ed.). (2010). European Arts Festivals: Cultural Pragmatics and Discursive Identity Frames.
</td>
</tr>


<tr>
<td>has_international_partners</td>
<td>Presenza di partner internazionali dichiarati</td>
<td>0 / 1</td>
<td>
1: presenza dichiarata di partner, istituzioni, organizzazioni o sponsor internazionali.<br>
0: assenza di partner internazionali dichiarati.
</td>
<td>
Giorgi, L. (Ed.). (2010). European Arts Festivals: Cultural Pragmatics and Discursive Identity Frames.
</td>
</tr>



<tr>
<td rowspan="6">CULTURAL DOMAINS</td>
<td>has_photography</td>
<td>Presenza della fotografia come dominio culturale nel programma del festival</td>
<td>0 / 1</td>
<td>
1: presenza esplicita di mostre fotografiche, esposizioni, installazioni fotografiche, workshop, portfolio review, incontri con fotografi o altre attività dove la fotografia è elemento centrale.<br><br>

0: fotografia utilizzata solo come elemento documentativo/promozionale senza programmazione fotografica.
</td>
<td>
Bína et al. (2012). ESSnet-Culture: European Statistical System Network on Culture. Final Report.
</td>
</tr>


<tr>
<td>has_other_visual_arts</td>
<td>Presenza di arti visive diverse dalla fotografia</td>
<td>0 / 1</td>
<td>
1: presenza di pittura, scultura, installazione, arte contemporanea, graphic design, illustrazione, incisione o altre arti visive.<br><br>

0: esclusiva presenza di fotografia o elementi scenografici senza componente artistica autonoma.
</td>
<td>
Bína et al. (2012). ESSnet-Culture: European Statistical System Network on Culture. Final Report.
</td>
</tr>


<tr>
<td>has_books_press</td>
<td>Presenza di attività editoriali nel programma del festival</td>
<td>0 / 1</td>
<td>
1: presenza di photobook, presentazioni editoriali, book fair, incontri con editori, pubblicazioni come parte del programma o premi dedicati ai libri fotografici.<br><br>

0: presenza esclusiva di cataloghi, merchandising o bookshop senza attività editoriali.
</td>
<td>
Bína et al. (2012). ESSnet-Culture: European Statistical System Network on Culture. Final Report.
</td>
</tr>


<tr>
<td>has_architecture_design</td>
<td>Presenza del dominio Architecture & Design</td>
<td>0 / 1</td>
<td>
1: presenza di mostre, workshop, conferenze o sezioni dedicate ad architettura, urbanistica, paesaggio costruito o design.<br><br>

0: utilizzo di edifici o luoghi architettonici solo come sede del festival.
</td>
<td>
Bína et al. (2012). ESSnet-Culture: European Statistical System Network on Culture. Final Report.
</td>
</tr>


<tr>
<td>has_performing_arts</td>
<td>Presenza di arti performative nel programma</td>
<td>0 / 1</td>
<td>
1: presenza di teatro, danza, performance artistiche, musica dal vivo o live show come parte del programma culturale.<br><br>

0: musica o intrattenimento solo come elemento accessorio.
</td>
<td>
Bína et al. (2012). ESSnet-Culture: European Statistical System Network on Culture. Final Report.
</td>
</tr>


<tr>
<td>has_audiovisual_multimedia</td>
<td>Presenza di attività audiovisive e multimediali</td>
<td>0 / 1</td>
<td>
1: presenza di cinema, documentari, videoarte, videoinstallazioni, opere multimediali, VR, AR, podcast o installazioni sonore.<br><br>

0: utilizzo esclusivo di strumenti audiovisivi come supporto tecnico.
</td>
<td>
Bína et al. (2012). ESSnet-Culture: European Statistical System Network on Culture. Final Report.
</td>
</tr>

</tbody>
</table>
