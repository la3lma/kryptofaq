 EFNs logo

KRYPTOGRAFI, KRIMINALITET OG PERSONVERN

Copyright Bjørn Remseth og Thomas Gramstad
Dette dokumentet er tilgjengelig under GNU Free Documentation License.

    HVA ER KRYPTERING?
    'SVAK' KRYPTOGRAFI
    'STERK' KRYPTOGRAFI
    STERK KRYPTOGRAFI: EN LIVSNØDVENDIGHET?
    HVA BETYR KRYPTERING FOR DEG?
    TILFELLER DER DET ER ØNSKELIG Å KUNNE SKAFFE SEG TILGANG TIL HEMMELIGE KODENØKLER
    TILFELLER DER DET ER NYTTIG Å HA HEMMELIGE KODENØKLER SOM ALDRI BLIR GJORT KJENT
    NØKKELDEPONERING
    HVORFOR ER DET I PRAKSIS UMULIG Å FORHINDRE BRUK AV STERK KRYPTERING?
    HVORDAN KAN KRYPTERING FORHINDRE DATAKRIMINALITET?
    KRYPTERINGSMETODER SOM KAN AVLYTTES
    NHDS RAPPORT OM UTVIKLING AV NASJONAL KRYPTOPOLITIKK (6. APRIL 2001)
    REFERANSER

HVA ER KRYPTERING?

Tradisjonelt har man med "kryptering" ment koding av informasjon på en slik måte at den kun kan dekodes (dekrypteres) og leses av personer som kjenner en spesiell "nøkkel". Ordet "kryptografi" er avledet av gresk og betyr "skjult skrift".

Kryptering brukes også for autentisering av informasjon. "Digitale signaturer" benyttes for at mottakeren av en melding skal kunne forsikre seg om identiteten til avsenderen og at meldingen ikke er endret av uvedkommende. Slik virker digitale signaturer omtrent som håndskrevne signaturer på papirdokumenter, men med den forskjellen at man ikke behøver å være skrift-ekspert for å vurdere om en signatur er ekte, alt som kreves er at man har en datamaskin som kan kjøre en ganske lite program.

'SVAK' KRYPTOGRAFI

Krypto-algoritmer har forskjellig styrke, fra helt trivielle til umulig å knekke. En 'svak' algoritme er ikke i stand til å motstå et seriøst angrep.

Helt tilbake i oldtiden finner man eksempler på svake kryptosystemer, et av de mest kjente tillegges Julius Cæsar. Da Cæsar ønsket å sende viktige meldinger til sine offiserer ute i felten krypterte han dem (altså kodet dem) ved å flytte alle bokstavene i alfabetet tre plasser til høyre. På denne måten ville meldingen "Angrip ved daggry" bli "Dqjuls yhg gdjjuøf", idet en "A" blir til en "D", en "B" blir til en "E" osv. Når offiserene - som kjente til Cæsars system - fikk den krypterte meldingen, dekrypterte de den ved å flytte bokstaven tre plasser til venstre.

Dersom man ønsker å bruke et slikt system bestemmer man seg for hvor mange plasser man skal flytte bokstavene, f.eks. 3, og vi sier da at 3 er nøkkelen.

Idag gir Cæsars system ingen sikkerhet, fordi det er lett å knekke (dvs. selv om fienden ikke vet hvor mange plasser bokstavene er flyttet kan de meget raskt finne det ut ved hjelp av regnekraften til datamaskiner). Dette er derfor et eksempel på en svak kode.

På den annen side, selv helt trivielle koder har en misjon: Du kan ikke i ettertid si at du 'tilfeldigvis' kom over noe når det faktisk var kryptert. Ett eksempel er 'rot13' (Cæsar-rotasjon tretten plasser), som brukes mye på Internett. Denne koden brukes til å si fra at 'her kommer det en melding du kanskje ikke vil lese, så bruk rot13 hvis du virkelig vil lese den'.

Svak kryptering er altså å kode en melding slik at det er mer eller mindre lett for andre å lese den - det kreves ikke så store ressurser for å knekke koden. Fra noen millisekunder (for Cæsar-koder) til et par uker kjøretid på en en klynge av moderne PC-er eller en enkelt superdatamaskin (for 40 bit RC4 brukt bl.a. av Netscape), er ofte nok.

Det amerikanske forsvarsdepartementet har definert krypto-algoritmer med nøkkel-"styrke" på 40 bits eller mindre som 'svake'. Det finnes begrensninger på eksport av svake krypto-produkter, men mange flere og mer omfattende begrensninger for sterke krypto-produkter. Krypteringsmodulene i mange kommersielle programmer er derfor svake - med 40 bit nøkler eller mindre. Dette er godt nok for mange formål, men hjelper lite mot en seriøs angriper med en del prosessorkraft tilgjengelig.

Mange 'hemmelige koder' er i virkeligheten 'svake' koder, siden det er kjent hvordan de knekkes på kort tid, selv om man ikke har fått utdelt kodenøkkelen.

'STERK' KRYPTOGRAFI

``Sterk kryptering'' innebærer å kode en melding slik at det er svært vanskelig for andre å lese den, selv om de vet hvilken metode som har blitt brukt for å kryptere den, men uten at de vet hvilken kodenøkkel som ble brukt.

Med 'svært vanskelig' menes her at det ikke skal finnes noen vesentlig enklere måte å dekode meldingen på enn å lete gjennom samtlige mulige kodenøkler, teste hver eneste en, og stoppe først når den riktige nøkkelen er funnet. Dette krever svært stor regnekraft - store datamaskinressurser - og i gjennomsnitt vil det være nødvendig å lete gjennom halvparten av alle nøklene før man finner den man leter etter.

Styrken på en algoritme er delvis gitt matematisk ved tiden det vil ta å lete gjennom samtlige mulige nøkler, og dels ved de matematiske metodene som er brukt for å konstruere algoritmen slik at systematisk leting etter nøkkelen (som er en langsom metode) også blir den enkleste metoden.

Lenger nøkkel-lengder blir raskt vanskeligere å knekke, og "nøkler" som er like lange som meldingen er beviselig umulig å knekke uten å stjele kodenøkkelen. Maksimalt sikre krypteringmetoder brukes kun i spesielle tilfeller, f.eks. for å utveksle nøkler til mindre sikre (men fremdeles sterke) metoder.

Krypto-algoritmer kan også være tilsynelatende svært sterke, men likevel inneholde svakheter som gjør at en angriper kan finne snarveier. For å regnes som sikker må en algoritme må kunne motstå angrep der angriperen kjenner både klarteksten og den krypterte teksten, kanskje til og med har anledning til å velge klartekster for kryptering. Nøkkelen kan imidlertid antas å være hemmelig, men den skal til gjengjeld være den eneste delen av kryptosystemet som er hemmeligholdt.

DES (Data Encryption Standard), som er den mest brukte algoritmen i dag, har en nøkkellengde på 56 bits, og må idag regnes som middels sterk. Selv dette vil i løpet av få år være for lite pga. utvikling av raskere utstyr, og nye, sterke, algoritmer bruker gjerne minst 80 bits. Mange krypto-algoritmer er hemmelige. Dette vanskeliggjør selvfølgelig et angrep, men det gjør det også umulig for utenforstående å evaluere styrken av algoritmen. Norsk Standard Kryptoalgoritme (NSK) er ett eksempel på en hemmelig algoritme. NSK er spesifisert som en meget sterk algoritme. I sin almindelighet skal en være forsiktig med å stole på hemmelige algoritmer, siden en ikke vet om designerne kan jobben sin godt nok, eller om de bevisst eller ubevisst har lagt inn bakdører eller andre feller. Hemmelige algoritmer må implementeres i spesialelektronikk. Det er umulig å hemmeligholde en metode som er implementert i programkode.

Det er her instruktivt å se hva som skjedde med DES (Data Encryption Standard) algoritmen. DES ble på midten av syttitallet den første offentlig tilgjengelige algoritmen som ble sertifisert som sikker av det amerikanske National Security Agency (NSA), som ikke gjør annet enn å utvikle og knekke kodesystemer. NSA foreslo endel endringer i det orginale designet som de sa ville gjøre det sikrere, men de ville ikke si hvorfor, det var hemmelig. I 1990 publiserte to Israelere en metode kalt "Differensial kryptoanalyse" som påviste fundamentale svakheter i DES, svakheter som ville gjort den helt ubrukelig som en sterk algoritme, hvis ikke endringene NSA foreslo hadde blitt tatt inn i designet. Det var altså mer enn femten år skille mellom NSAs kjennskap til differensial kryptoanalyse og den offentlige publikasjonen. Vi vet ingen ting om hvilke metoder de i dag holder hemmelige, og hvordan disse er anvendbare på algoritmer som er kjent i dag. Det vi vet er at NSA og deres søsterorganisasjoner er veldig dyktige, er blant verdens største arbeidsgivere for matematikere og kodeeksperter, og at det er dumt å undervurdere dem. Den beste sikringen vi har er å stole på de kodeekspertene som ikke jobber for dem til sammen er i stand til å sjekke i alle fall noen algoritmer slik at vi er rimelig sikre på at de ikke er mulige å knekke. For å få til dette kreves åpenhet om algoritmene, og derfor er det i dag også flere gode og offentlig kjente algoritmer (DES, IDEA og Blowfish er blant disse).

En god krypteringsmetode har derfor et svært stort antall mulige nøkler. En middels god metode som DES har ca 70.000.000.000.000.000 eller 70 millioner milliarder nøkler (56 bit). Dette er imidlertid et forsvinnende lite antall i forhold til bedre krypterings-metoder: IDEA, som bl.a. brukes i PGP har 128 bit og er dermed mye mer enn hundre millioner milliarder ganger sterkere enn DES. Hvis en søkte gjennom en milliard nøkler i sekundet, ville det da fremdeles ta ti tusen milliarder milliarder år å knekke koden. Til sammenligning mener man at solen kun har fem milliarder år igjen å leve.

Grunnen til at en slik nøkkel regnes som sikker er altså at det per idag kreves mere store maskin- og tidsressurser for å bryte koden enn det som finnes totalt på jorden, eller vil finnes her i overskuelig tid.

For å oppnå sterk kryptering er det ikke nok å benytte en sterk krypteringsmetode. Det finnes mange eksempler på at systemer der en sikker krypteringsmetode er brukt på feil måte slik at svakheter er blitt innført i totalsystemet.

STERK KRYPTOGRAFI: EN LIVSNØDVENDIGHET?

"Kryptering" omfatter en stor gruppe mekanismer og dataprogrammer. Generelt brukes de til å holde ting hemmelige, men de brukes også til å lage digitale signaturer, slik at det er mulig å forsikre seg om at den som står oppført som avsender virkelig er avsenderen.

En digital signatur sikrer integriteten av en melding, slik at du kan være sikker på at det du mottar, er det samme som avsenderen skrev.

Kryptering er altså som en forseglet konvolutt:

    Du kan legge hva som helst inne i den.
    Du kan signere den og forsegle den slik at mottager er sikker på at kun du kan ha forseglet den.
    Videre kan du adressere konvolutten på en slik måte at kun mottager kan åpne den og lese innholdet.

En ukryptert melding derimot, er som et postkort. Alle som kikker på postkortet kan lese det. Noen anvendelser av kryptering:

    Privatliv. Du kan skrive ned ting om ditt privatliv, og være sikker på at ingen - eller ingen andre enn de du vil - kan lese dem.
    Bedriftshemmeligheter. Du kan skrive ned bedriftshemmeligheter og være sikker på at ingen - eller ingen andre enn de du vil - kan lese dem.
    Autentisering. Datafiler kan signeres elektronisk, slik at det er mulig å vite at filene faktisk kommer fra produsenten og ingen annen.
    Integritet. Integritet er en konsekvens av autentisering: Hvis du er sikker på at du kan stole på avsenderen, da kan du være sikker på at innholdet - f.eks. et dataprogram - ikke er manipulert med, at det f.eks. ikke inneholder virus.
    Tilgjengelighet. Siden du kan stole på at alle delene av datasystemet ditt har ubrutt integritet, kan du også garantere høyere tilgjengelighet. Dersom du tror du har blitt angrepet av et virus eller en cracker, kan du sjekke at filene dine ser slik ut som produsenten sa de skulle, uten å faktisk måtte sammenligne med orginalfilene. Dette er en ekstremt tidsbesparende metode.

HVA BETYR KRYPTERING FOR DEG?

    At du kan lage elektroniske signaturer som ingen kan forfalske.
    At du kan betale ting gjennom elektronisk betalingsformidling uten risiko for at uvedkommende kan se hva du kjøpte.
    At du kan betale ting gjennom elektronisk betalingsformidling uten risiko for at uvedkommende kan få tak i din kontoinformasjon og misbruke din konto eller dine elektroniske penger.
    At du kan kontrollere at uvedkommende ikke skal få lov til å lese en tekst du har skrevet, selv om de klarer å stjele datafilen teksten ligger på.

Det er allment akseptert blant fagfolk at god datasikkerhet i nettverk og åpne systemer krever bruk av sterk kryptografi. Kryptografiske metoder kan beskytte data under lagring og overføring, og de kan brukes til autentisering istedenfor passord (som er en meget svak metode).

Når sikkerheten i dagens datasystemer er for dårlig, skyldes dette i stor grad begrensninger i tilgjengeligheten av skikkelige krypto-produkter. Mye av teknologien vi bruker stammer fra USA, og som nevnt, er det en rekke restriksjoner og begrensninger på mulighetene for å eksportere både sterke og svakere krypto-produkter fra USA.

Uten kryptering sender du i praksis elektroniske "postkort", slik at alle som kommer over en melding, også kan lese den. Kryptering er ikke noe annet enn en konvolutt rundt en tekst, og denne skal være sterk nok til å motstå forsøk på åpning. De som vil forby deg å bruke kryptering vil altså i praksis forby deg å bruke konvolutt rundt meldingene dine - de vil med andre ord ta fra deg retten til privat kommunikasjon.

Lovgivningen i USA er antagelig den største bremseklossen for å få tatt i bruk krypto-produkter i hverdagsprodukter. Kryptografisk teknologi blir imidlertid etterhvert også tilgjengelig andre land enn USA

TILFELLER DER DET ER ØNSKELIG Å KUNNE SKAFFE SEG TILGANG TIL HEMMELIGE KODENØKLER

    Prøve å begrense kriminalitet ved å gjøre det lettere for etterforskere å få tilgang til informasjon, f.eks. der det er mistanke om:
        Barneporno, bombeoppskrifter, smugling, terrorisme
        Opphavsrettslige krenkelser
        Misbruk av betalingsmidler.
    Begrensninger i bruk av kryptografi vil gi ordensmakten bedre evne til innsyn i opplysninger lagret elektronisk, i forbindelse med etterforskning av forbrytelser.
    Når den som hadde nøkkelen ikke er i stand til å gi den fra seg f.eks. etter en ulykke, eller data som inngår i en del av et arveoppgjør.
    Når innholdet i 'forseglede' data skal gjøres tilgjengelige etter en rettslig avgjørelse.

TILFELLER DER DET ER NYTTIG Å HA HEMMELIGE KODENØKLER SOM ALDRI BLIR GJORT KJENT

    Når nøkkelen kun brukes til å signere data er det som regel ønskelig at signaturen aldri skal kunne forfalskes.
    Det er noen hemmeligheter det er ønskelig å kunne gå i graven med.

NØKKELDEPONERING

Nøkkeldeponering (engelsk: key escrow) er en metode for å sikre at enkelte utenforstående har muligheten til å dekryptere meldinger som er beskyttet med en sterk krypteringsmetode. Ett eller flere nøkkeldeponier har da kopier av alle nøklene som brukes, og kan dermed dekryptere meldinger.

Nøkkeldeponeringen kan enten være frivillig eller tvungen. Det omstridte amerikanske Clipper-initiativet er et eksempel på tvungen nøkkeldeponering som hvis det blir gjennomført bl.a. vil gi den amerikanske ordensmakten mulighet til å avlytte alle telefonsamtaler selv om disse krypteres.

Et eksempel på frivillig nøkkeldeponering kan være en liten bedrift der innehaveren beskytter sine data med kryptering. Da vil det kunne være ønskelig å lagre en kopi av krypteringsnøkkelen hos en eller flere tiltrodde tredjeparter som en "livsforsikring" slik at firmaet ikke nødvendigvis går under selv om innehaveren faller under en trikk.

HVORFOR ER DET I PRAKSIS UMULIG Å FORHINDRE BRUK AV STERK KRYPTERING?

Fordi dette krever både at det er mulig å hindre kryptert materiale å flyte fritt og å fjerne alle kryptografiske programmer som allerede er i bruk. Begge deler er av tekniske årsaker nær umulig. Et forbud vil derfor være meget vanskelig å håndheve.

De tekniske årsakene til dette er mange, her nevnes tre:

    Skjulte kanaler. Dette er informasjonsstrømmer som skjuler en annen informasjonsstrøm. Man kan f.eks. velge om det mellom ord skal være ett eller to mellomrom. Ett mellomrom betyr '0' og to betyr '1'. Teksten:

                    "dette er  en hemmelig  melding"

    ... vil da kunne dekodes til strengen '0101'. Dersom både sender og mottager kjenner til denne kodemekanismen, kan et program kode en hemmelig melding i en ellers helt uskyldig utseende tekst. Tilsvarende metoder finnes for bilder, lyd og alle andre elektroniske medier. Poenget er altså at meldinger kan gjemmes på en slik måte at utenforstående ikke en gang kan oppdage at det er noen melding der, og at dette kan gjøres på utallige måter. Gitt at det er mulig å kode meldinger i skjulte kanaler, og at det er umulig å oppdage dem, så betyr dette at det dermed også er umulig å oppdage om en gitt melding er kodet med en "sterk" kryptografisk kode.
    Tilgjengelighet av krypteringsprogrammer. Programmer for å utføre sterk kryptering finnes i dag tilgjengelig over Internett, og metodene de benytter er beskrevet i fritt tilgjengelig litteratur. Det er helt urimelig og urealistisk å tro at denne kunnskapen skal kunne fjernes ved et pennestrøk.
    Uklarhet om hva som er en kode.
        En kryptert tekst kan framstå som en tilfeldig strøm av tegn. Det er derfor ofte umulig å si om noe er en kryptert tekst, eller bare "søppel".
        Dersom det blir forbud mot koder som myndighetene ikke kan knekke, blir det straks problematisk å avgrense hva som utgjør en slik kode. Dersom f.eks. ingen i politiet kunne snakke arabisk, ville arabisk kunne regnes som en kryptografisk kode; men det ville likevel være urimelig å gjøre det forbudt å snakke arabisk i telefonen. Kryptering er analogt med dette.

På grunn av disse forholdene vil forsøk på å hindre bruk av kryptografi være dømt til å mislykkes, selv om tilgjengeligheten vil bli vanskeliggjort. De som vil bli rammet, er lovlydige borgere og bedrifter, mens de som gir blaffen i regelverket (ikke nødvendigvis fordi de er kriminelle) likevel lett vil kunne skaffe seg de verktøyene de trenger.

Vi mener derfor at forsøk på å hindre bruk av kryptografi fra politiker side ikke vil kunne gjøre noe annet enn å skape et inntrykk av at de "gjør noe", mens situasjonen i virkeligheten ikke er endret på annet vis enn at lovlydige borgere mister rettigheter.

HVORDAN KAN KRYPTERING FORHINDRE DATAKRIMINALITET?

Det fremholdes ofte at adgang til sterk kryptografi vil gjøre livet lettere for forbrytere. Det som ikke nevnes, er at manglende tilgjengelighet av skikkelig kryptografi muliggjør datakriminalitet som ellers kunne ha vært forhindret, jfr. pkt. (3) og (4) over.

Siden datakriminalitet ofte er svært vanskelig å oppdage, blir det tilsvarende viktig å ha god beskyttelse mot den - slik som kryptografiske produkter - i utgangspunktet.

Selv om det per idag ikke foreligger forslag i Norge om å forby sterk kryptografi, finnes det slike forslag, og til og med vedtatte lover, i andre land. Vi mener derfor at det er grunn til å være på vakt også her i landet. Norge kan også risikere å bli bundet opp av vedtak innen EU og EØS.

KRYPTERINGSMETODER SOM KAN AVLYTTES

I mange land er det planer om å tilby krypto-tjenester som muliggjør avlytting. USAs Clipper-initiativ er det mest kjente. Slike systemer vil beskytte mot utenforstående (forutsatt at det brukes sterke metoder), mens politi og andre offentlige myndigheter har mulighet til å skaffe seg kopi av nøklene som brukes, fortrinnvis etter rettslig kjennelse eller lignende.

Avhengig av hvordan tilgangen til nøkler kontrolleres, vil mange kunne akseptere et slikt system. Det er imidlertid mange årsaker til at andre ikke ønsker å basere sikkerheten sin på avlyttbare algoritmer.

    Bedrifter ønsker ikke å ta sjansen på (selv en antatt liten) mulighet for at "utro tjenere" innen det offentlige skal få tak i og lekke opplysninger.
    Privatpersoner eller andre kan ha opplysninger de ikke ønsker at myndighetene skal kunne få tak i på noen måte. Det behøver slett ikke å være noe suspekt i et slikt ønske - for mange er det en del av privatlivets fred å slippe å gi flere opplysninger om seg selv enn nødvendig.
    En del vil ikke stole på at avlyttingen blir kontrollert strengt nok. Ut fra opplysninger om telefonavlytting både i Norge og i andre land kan det være gode grunner til en slik skepsis.

Vi mener at et avlyttbart system godt kan tilbys som en offentlig tjeneste, men ikke uten at annen sterk kryptografi er tilgjengelig for dem som ønsker det.

NHDS RAPPORT OM UTVIKLING AV NASJONAL KRYPTOPOLITIKK (6. APRIL 2001)

Denne rapporten er i all hovedsak positiv i forhold til EFNs vurderinger og anbefalinger. I en kort oppsummering av rapporten i hovedpunkt 12 fremmes det visse anbefalinger for en nasjonal kryptopolitikk:

    En grunnleggende positiv holding til bruk av kryptering.
    Avvisning av obligatorisk deponering av krypteringsnøkler som en innehar som privatperson.
    Oppmerksomhet rettet mot koordinering på et internasjonalt, ikke bare europeisk nivå.
    Tilrettelegging av forholdene for sterkere vekst i nasjonal kryptoindustri.
    Minst mulig belastning av brukergrupper ved implementering av politikken.
    Utforming av politikken i tråd med forslaget om bruk av elektroniske signaturer (jf NOU 2001:10).
    Utforming av politikken slik at den ikke krever endring i de alminnelige regler for saksbehandling i offentlig forvaltning, men sikrer bedre realisering av forvaltningslovens målsettinger ved overgang til elektronisk forvaltning.

Rapporten finnes fra:
http://odin.dep.no/nhd/norsk/p10001865/p10001878/024101-990051/index-dok000-n-n-a.html

Det finnes også et sammendrag av rapporten her:
http://odin.dep.no/nhd/norsk/p10001865/p10001878/024101-990058/index-dok000-n-n-a.html

REFERANSER
Bøker:

    Scheiner, Bruce: (1994), Applied Cryptography: Protocols, Algorithms and Source Code in C. John Wiley & Sons. Inc.
    Garfinkel, Simson: (1995), PGP - Pretty Good Privacy. O'Reilly & Associates, Inc.

Artikler:

    Peachey, D.: "Euro-Clipper Chip Scheme Proposed". Communications Week no. 151 (18 Sept. 1995) s. 1-81.
    Thorel, J.: "EC Plans Encryption Rules in Bid to Police Information Superhighway". Nature vol. 377 no. 6547 (28 Sept. 1995) s. 275.

Internett:

    http://csrc.ncsl.nist.gov/
    (National Institute of Standards and Techology. Computer Security Resource Clearinghouse)
    http://www.faqs.org/faqs/cryptography-faq/
    (Omfattende dokument med spørsmål og svar om kryptering; opprinnelig sci.crypt FAQ.)
    http://www.uninett.no/pca
    (UNINETTs kryptotjeneste)

Elektronisk Forpost Norge er en rettighetsorganisasjon som jobber med medborgerskap og juridiske rettigheter i IT-samfunnet.
www.efn.no.

Dette dokumentets adresse:
http://folk.uio.no/thomas/efn/krypto-notat.html

Sist oppdatert av   Thomas Gramstad     4. februar   2002.

Support the Blue Ribbon Campaign for Free Speech! Best Viewed With Any Browser Valid HTML 4.0! Frames Free! Ribbon Campaign Created with GNU Emacs www.linux.org - a GNU and better computer for you



