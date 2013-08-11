 EFNs logo

KRYPTOGRAFI, KRIMINALITET OG PERSONVERN

Copyright Bj�rn Remseth og Thomas Gramstad
Dette dokumentet er tilgjengelig under GNU Free Documentation License.

    HVA ER KRYPTERING?
    'SVAK' KRYPTOGRAFI
    'STERK' KRYPTOGRAFI
    STERK KRYPTOGRAFI: EN LIVSN�DVENDIGHET?
    HVA BETYR KRYPTERING FOR DEG?
    TILFELLER DER DET ER �NSKELIG � KUNNE SKAFFE SEG TILGANG TIL HEMMELIGE KODEN�KLER
    TILFELLER DER DET ER NYTTIG � HA HEMMELIGE KODEN�KLER SOM ALDRI BLIR GJORT KJENT
    N�KKELDEPONERING
    HVORFOR ER DET I PRAKSIS UMULIG � FORHINDRE BRUK AV STERK KRYPTERING?
    HVORDAN KAN KRYPTERING FORHINDRE DATAKRIMINALITET?
    KRYPTERINGSMETODER SOM KAN AVLYTTES
    NHDS RAPPORT OM UTVIKLING AV NASJONAL KRYPTOPOLITIKK (6. APRIL 2001)
    REFERANSER

HVA ER KRYPTERING?

Tradisjonelt har man med "kryptering" ment koding av informasjon p� en slik m�te at den kun kan dekodes (dekrypteres) og leses av personer som kjenner en spesiell "n�kkel". Ordet "kryptografi" er avledet av gresk og betyr "skjult skrift".

Kryptering brukes ogs� for autentisering av informasjon. "Digitale signaturer" benyttes for at mottakeren av en melding skal kunne forsikre seg om identiteten til avsenderen og at meldingen ikke er endret av uvedkommende. Slik virker digitale signaturer omtrent som h�ndskrevne signaturer p� papirdokumenter, men med den forskjellen at man ikke beh�ver � v�re skrift-ekspert for � vurdere om en signatur er ekte, alt som kreves er at man har en datamaskin som kan kj�re en ganske lite program.

'SVAK' KRYPTOGRAFI

Krypto-algoritmer har forskjellig styrke, fra helt trivielle til umulig � knekke. En 'svak' algoritme er ikke i stand til � motst� et seri�st angrep.

Helt tilbake i oldtiden finner man eksempler p� svake kryptosystemer, et av de mest kjente tillegges Julius C�sar. Da C�sar �nsket � sende viktige meldinger til sine offiserer ute i felten krypterte han dem (alts� kodet dem) ved � flytte alle bokstavene i alfabetet tre plasser til h�yre. P� denne m�ten ville meldingen "Angrip ved daggry" bli "Dqjuls yhg gdjju�f", idet en "A" blir til en "D", en "B" blir til en "E" osv. N�r offiserene - som kjente til C�sars system - fikk den krypterte meldingen, dekrypterte de den ved � flytte bokstaven tre plasser til venstre.

Dersom man �nsker � bruke et slikt system bestemmer man seg for hvor mange plasser man skal flytte bokstavene, f.eks. 3, og vi sier da at 3 er n�kkelen.

Idag gir C�sars system ingen sikkerhet, fordi det er lett � knekke (dvs. selv om fienden ikke vet hvor mange plasser bokstavene er flyttet kan de meget raskt finne det ut ved hjelp av regnekraften til datamaskiner). Dette er derfor et eksempel p� en svak kode.

P� den annen side, selv helt trivielle koder har en misjon: Du kan ikke i ettertid si at du 'tilfeldigvis' kom over noe n�r det faktisk var kryptert. Ett eksempel er 'rot13' (C�sar-rotasjon tretten plasser), som brukes mye p� Internett. Denne koden brukes til � si fra at 'her kommer det en melding du kanskje ikke vil lese, s� bruk rot13 hvis du virkelig vil lese den'.

Svak kryptering er alts� � kode en melding slik at det er mer eller mindre lett for andre � lese den - det kreves ikke s� store ressurser for � knekke koden. Fra noen millisekunder (for C�sar-koder) til et par uker kj�retid p� en en klynge av moderne PC-er eller en enkelt superdatamaskin (for 40 bit RC4 brukt bl.a. av Netscape), er ofte nok.

Det amerikanske forsvarsdepartementet har definert krypto-algoritmer med n�kkel-"styrke" p� 40 bits eller mindre som 'svake'. Det finnes begrensninger p� eksport av svake krypto-produkter, men mange flere og mer omfattende begrensninger for sterke krypto-produkter. Krypteringsmodulene i mange kommersielle programmer er derfor svake - med 40 bit n�kler eller mindre. Dette er godt nok for mange form�l, men hjelper lite mot en seri�s angriper med en del prosessorkraft tilgjengelig.

Mange 'hemmelige koder' er i virkeligheten 'svake' koder, siden det er kjent hvordan de knekkes p� kort tid, selv om man ikke har f�tt utdelt koden�kkelen.

'STERK' KRYPTOGRAFI

``Sterk kryptering'' inneb�rer � kode en melding slik at det er sv�rt vanskelig for andre � lese den, selv om de vet hvilken metode som har blitt brukt for � kryptere den, men uten at de vet hvilken koden�kkel som ble brukt.

Med 'sv�rt vanskelig' menes her at det ikke skal finnes noen vesentlig enklere m�te � dekode meldingen p� enn � lete gjennom samtlige mulige koden�kler, teste hver eneste en, og stoppe f�rst n�r den riktige n�kkelen er funnet. Dette krever sv�rt stor regnekraft - store datamaskinressurser - og i gjennomsnitt vil det v�re n�dvendig � lete gjennom halvparten av alle n�klene f�r man finner den man leter etter.

Styrken p� en algoritme er delvis gitt matematisk ved tiden det vil ta � lete gjennom samtlige mulige n�kler, og dels ved de matematiske metodene som er brukt for � konstruere algoritmen slik at systematisk leting etter n�kkelen (som er en langsom metode) ogs� blir den enkleste metoden.

Lenger n�kkel-lengder blir raskt vanskeligere � knekke, og "n�kler" som er like lange som meldingen er beviselig umulig � knekke uten � stjele koden�kkelen. Maksimalt sikre krypteringmetoder brukes kun i spesielle tilfeller, f.eks. for � utveksle n�kler til mindre sikre (men fremdeles sterke) metoder.

Krypto-algoritmer kan ogs� v�re tilsynelatende sv�rt sterke, men likevel inneholde svakheter som gj�r at en angriper kan finne snarveier. For � regnes som sikker m� en algoritme m� kunne motst� angrep der angriperen kjenner b�de klarteksten og den krypterte teksten, kanskje til og med har anledning til � velge klartekster for kryptering. N�kkelen kan imidlertid antas � v�re hemmelig, men den skal til gjengjeld v�re den eneste delen av kryptosystemet som er hemmeligholdt.

DES (Data Encryption Standard), som er den mest brukte algoritmen i dag, har en n�kkellengde p� 56 bits, og m� idag regnes som middels sterk. Selv dette vil i l�pet av f� �r v�re for lite pga. utvikling av raskere utstyr, og nye, sterke, algoritmer bruker gjerne minst 80 bits. Mange krypto-algoritmer er hemmelige. Dette vanskeliggj�r selvf�lgelig et angrep, men det gj�r det ogs� umulig for utenforst�ende � evaluere styrken av algoritmen. Norsk Standard Kryptoalgoritme (NSK) er ett eksempel p� en hemmelig algoritme. NSK er spesifisert som en meget sterk algoritme. I sin almindelighet skal en v�re forsiktig med � stole p� hemmelige algoritmer, siden en ikke vet om designerne kan jobben sin godt nok, eller om de bevisst eller ubevisst har lagt inn bakd�rer eller andre feller. Hemmelige algoritmer m� implementeres i spesialelektronikk. Det er umulig � hemmeligholde en metode som er implementert i programkode.

Det er her instruktivt � se hva som skjedde med DES (Data Encryption Standard) algoritmen. DES ble p� midten av syttitallet den f�rste offentlig tilgjengelige algoritmen som ble sertifisert som sikker av det amerikanske National Security Agency (NSA), som ikke gj�r annet enn � utvikle og knekke kodesystemer. NSA foreslo endel endringer i det orginale designet som de sa ville gj�re det sikrere, men de ville ikke si hvorfor, det var hemmelig. I 1990 publiserte to Israelere en metode kalt "Differensial kryptoanalyse" som p�viste fundamentale svakheter i DES, svakheter som ville gjort den helt ubrukelig som en sterk algoritme, hvis ikke endringene NSA foreslo hadde blitt tatt inn i designet. Det var alts� mer enn femten �r skille mellom NSAs kjennskap til differensial kryptoanalyse og den offentlige publikasjonen. Vi vet ingen ting om hvilke metoder de i dag holder hemmelige, og hvordan disse er anvendbare p� algoritmer som er kjent i dag. Det vi vet er at NSA og deres s�sterorganisasjoner er veldig dyktige, er blant verdens st�rste arbeidsgivere for matematikere og kodeeksperter, og at det er dumt � undervurdere dem. Den beste sikringen vi har er � stole p� de kodeekspertene som ikke jobber for dem til sammen er i stand til � sjekke i alle fall noen algoritmer slik at vi er rimelig sikre p� at de ikke er mulige � knekke. For � f� til dette kreves �penhet om algoritmene, og derfor er det i dag ogs� flere gode og offentlig kjente algoritmer (DES, IDEA og Blowfish er blant disse).

En god krypteringsmetode har derfor et sv�rt stort antall mulige n�kler. En middels god metode som DES har ca 70.000.000.000.000.000 eller 70 millioner milliarder n�kler (56 bit). Dette er imidlertid et forsvinnende lite antall i forhold til bedre krypterings-metoder: IDEA, som bl.a. brukes i PGP har 128 bit og er dermed mye mer enn hundre millioner milliarder ganger sterkere enn DES. Hvis en s�kte gjennom en milliard n�kler i sekundet, ville det da fremdeles ta ti tusen milliarder milliarder �r � knekke koden. Til sammenligning mener man at solen kun har fem milliarder �r igjen � leve.

Grunnen til at en slik n�kkel regnes som sikker er alts� at det per idag kreves mere store maskin- og tidsressurser for � bryte koden enn det som finnes totalt p� jorden, eller vil finnes her i overskuelig tid.

For � oppn� sterk kryptering er det ikke nok � benytte en sterk krypteringsmetode. Det finnes mange eksempler p� at systemer der en sikker krypteringsmetode er brukt p� feil m�te slik at svakheter er blitt innf�rt i totalsystemet.

STERK KRYPTOGRAFI: EN LIVSN�DVENDIGHET?

"Kryptering" omfatter en stor gruppe mekanismer og dataprogrammer. Generelt brukes de til � holde ting hemmelige, men de brukes ogs� til � lage digitale signaturer, slik at det er mulig � forsikre seg om at den som st�r oppf�rt som avsender virkelig er avsenderen.

En digital signatur sikrer integriteten av en melding, slik at du kan v�re sikker p� at det du mottar, er det samme som avsenderen skrev.

Kryptering er alts� som en forseglet konvolutt:

    Du kan legge hva som helst inne i den.
    Du kan signere den og forsegle den slik at mottager er sikker p� at kun du kan ha forseglet den.
    Videre kan du adressere konvolutten p� en slik m�te at kun mottager kan �pne den og lese innholdet.

En ukryptert melding derimot, er som et postkort. Alle som kikker p� postkortet kan lese det. Noen anvendelser av kryptering:

    Privatliv. Du kan skrive ned ting om ditt privatliv, og v�re sikker p� at ingen - eller ingen andre enn de du vil - kan lese dem.
    Bedriftshemmeligheter. Du kan skrive ned bedriftshemmeligheter og v�re sikker p� at ingen - eller ingen andre enn de du vil - kan lese dem.
    Autentisering. Datafiler kan signeres elektronisk, slik at det er mulig � vite at filene faktisk kommer fra produsenten og ingen annen.
    Integritet. Integritet er en konsekvens av autentisering: Hvis du er sikker p� at du kan stole p� avsenderen, da kan du v�re sikker p� at innholdet - f.eks. et dataprogram - ikke er manipulert med, at det f.eks. ikke inneholder virus.
    Tilgjengelighet. Siden du kan stole p� at alle delene av datasystemet ditt har ubrutt integritet, kan du ogs� garantere h�yere tilgjengelighet. Dersom du tror du har blitt angrepet av et virus eller en cracker, kan du sjekke at filene dine ser slik ut som produsenten sa de skulle, uten � faktisk m�tte sammenligne med orginalfilene. Dette er en ekstremt tidsbesparende metode.

HVA BETYR KRYPTERING FOR DEG?

    At du kan lage elektroniske signaturer som ingen kan forfalske.
    At du kan betale ting gjennom elektronisk betalingsformidling uten risiko for at uvedkommende kan se hva du kj�pte.
    At du kan betale ting gjennom elektronisk betalingsformidling uten risiko for at uvedkommende kan f� tak i din kontoinformasjon og misbruke din konto eller dine elektroniske penger.
    At du kan kontrollere at uvedkommende ikke skal f� lov til � lese en tekst du har skrevet, selv om de klarer � stjele datafilen teksten ligger p�.

Det er allment akseptert blant fagfolk at god datasikkerhet i nettverk og �pne systemer krever bruk av sterk kryptografi. Kryptografiske metoder kan beskytte data under lagring og overf�ring, og de kan brukes til autentisering istedenfor passord (som er en meget svak metode).

N�r sikkerheten i dagens datasystemer er for d�rlig, skyldes dette i stor grad begrensninger i tilgjengeligheten av skikkelige krypto-produkter. Mye av teknologien vi bruker stammer fra USA, og som nevnt, er det en rekke restriksjoner og begrensninger p� mulighetene for � eksportere b�de sterke og svakere krypto-produkter fra USA.

Uten kryptering sender du i praksis elektroniske "postkort", slik at alle som kommer over en melding, ogs� kan lese den. Kryptering er ikke noe annet enn en konvolutt rundt en tekst, og denne skal v�re sterk nok til � motst� fors�k p� �pning. De som vil forby deg � bruke kryptering vil alts� i praksis forby deg � bruke konvolutt rundt meldingene dine - de vil med andre ord ta fra deg retten til privat kommunikasjon.

Lovgivningen i USA er antagelig den st�rste bremseklossen for � f� tatt i bruk krypto-produkter i hverdagsprodukter. Kryptografisk teknologi blir imidlertid etterhvert ogs� tilgjengelig andre land enn USA

TILFELLER DER DET ER �NSKELIG � KUNNE SKAFFE SEG TILGANG TIL HEMMELIGE KODEN�KLER

    Pr�ve � begrense kriminalitet ved � gj�re det lettere for etterforskere � f� tilgang til informasjon, f.eks. der det er mistanke om:
        Barneporno, bombeoppskrifter, smugling, terrorisme
        Opphavsrettslige krenkelser
        Misbruk av betalingsmidler.
    Begrensninger i bruk av kryptografi vil gi ordensmakten bedre evne til innsyn i opplysninger lagret elektronisk, i forbindelse med etterforskning av forbrytelser.
    N�r den som hadde n�kkelen ikke er i stand til � gi den fra seg f.eks. etter en ulykke, eller data som inng�r i en del av et arveoppgj�r.
    N�r innholdet i 'forseglede' data skal gj�res tilgjengelige etter en rettslig avgj�relse.

TILFELLER DER DET ER NYTTIG � HA HEMMELIGE KODEN�KLER SOM ALDRI BLIR GJORT KJENT

    N�r n�kkelen kun brukes til � signere data er det som regel �nskelig at signaturen aldri skal kunne forfalskes.
    Det er noen hemmeligheter det er �nskelig � kunne g� i graven med.

N�KKELDEPONERING

N�kkeldeponering (engelsk: key escrow) er en metode for � sikre at enkelte utenforst�ende har muligheten til � dekryptere meldinger som er beskyttet med en sterk krypteringsmetode. Ett eller flere n�kkeldeponier har da kopier av alle n�klene som brukes, og kan dermed dekryptere meldinger.

N�kkeldeponeringen kan enten v�re frivillig eller tvungen. Det omstridte amerikanske Clipper-initiativet er et eksempel p� tvungen n�kkeldeponering som hvis det blir gjennomf�rt bl.a. vil gi den amerikanske ordensmakten mulighet til � avlytte alle telefonsamtaler selv om disse krypteres.

Et eksempel p� frivillig n�kkeldeponering kan v�re en liten bedrift der innehaveren beskytter sine data med kryptering. Da vil det kunne v�re �nskelig � lagre en kopi av krypteringsn�kkelen hos en eller flere tiltrodde tredjeparter som en "livsforsikring" slik at firmaet ikke n�dvendigvis g�r under selv om innehaveren faller under en trikk.

HVORFOR ER DET I PRAKSIS UMULIG � FORHINDRE BRUK AV STERK KRYPTERING?

Fordi dette krever b�de at det er mulig � hindre kryptert materiale � flyte fritt og � fjerne alle kryptografiske programmer som allerede er i bruk. Begge deler er av tekniske �rsaker n�r umulig. Et forbud vil derfor v�re meget vanskelig � h�ndheve.

De tekniske �rsakene til dette er mange, her nevnes tre:

    Skjulte kanaler. Dette er informasjonsstr�mmer som skjuler en annen informasjonsstr�m. Man kan f.eks. velge om det mellom ord skal v�re ett eller to mellomrom. Ett mellomrom betyr '0' og to betyr '1'. Teksten:

                    "dette er  en hemmelig  melding"

    ... vil da kunne dekodes til strengen '0101'. Dersom b�de sender og mottager kjenner til denne kodemekanismen, kan et program kode en hemmelig melding i en ellers helt uskyldig utseende tekst. Tilsvarende metoder finnes for bilder, lyd og alle andre elektroniske medier. Poenget er alts� at meldinger kan gjemmes p� en slik m�te at utenforst�ende ikke en gang kan oppdage at det er noen melding der, og at dette kan gj�res p� utallige m�ter. Gitt at det er mulig � kode meldinger i skjulte kanaler, og at det er umulig � oppdage dem, s� betyr dette at det dermed ogs� er umulig � oppdage om en gitt melding er kodet med en "sterk" kryptografisk kode.
    Tilgjengelighet av krypteringsprogrammer. Programmer for � utf�re sterk kryptering finnes i dag tilgjengelig over Internett, og metodene de benytter er beskrevet i fritt tilgjengelig litteratur. Det er helt urimelig og urealistisk � tro at denne kunnskapen skal kunne fjernes ved et pennestr�k.
    Uklarhet om hva som er en kode.
        En kryptert tekst kan framst� som en tilfeldig str�m av tegn. Det er derfor ofte umulig � si om noe er en kryptert tekst, eller bare "s�ppel".
        Dersom det blir forbud mot koder som myndighetene ikke kan knekke, blir det straks problematisk � avgrense hva som utgj�r en slik kode. Dersom f.eks. ingen i politiet kunne snakke arabisk, ville arabisk kunne regnes som en kryptografisk kode; men det ville likevel v�re urimelig � gj�re det forbudt � snakke arabisk i telefonen. Kryptering er analogt med dette.

P� grunn av disse forholdene vil fors�k p� � hindre bruk av kryptografi v�re d�mt til � mislykkes, selv om tilgjengeligheten vil bli vanskeliggjort. De som vil bli rammet, er lovlydige borgere og bedrifter, mens de som gir blaffen i regelverket (ikke n�dvendigvis fordi de er kriminelle) likevel lett vil kunne skaffe seg de verkt�yene de trenger.

Vi mener derfor at fors�k p� � hindre bruk av kryptografi fra politiker side ikke vil kunne gj�re noe annet enn � skape et inntrykk av at de "gj�r noe", mens situasjonen i virkeligheten ikke er endret p� annet vis enn at lovlydige borgere mister rettigheter.

HVORDAN KAN KRYPTERING FORHINDRE DATAKRIMINALITET?

Det fremholdes ofte at adgang til sterk kryptografi vil gj�re livet lettere for forbrytere. Det som ikke nevnes, er at manglende tilgjengelighet av skikkelig kryptografi muliggj�r datakriminalitet som ellers kunne ha v�rt forhindret, jfr. pkt. (3) og (4) over.

Siden datakriminalitet ofte er sv�rt vanskelig � oppdage, blir det tilsvarende viktig � ha god beskyttelse mot den - slik som kryptografiske produkter - i utgangspunktet.

Selv om det per idag ikke foreligger forslag i Norge om � forby sterk kryptografi, finnes det slike forslag, og til og med vedtatte lover, i andre land. Vi mener derfor at det er grunn til � v�re p� vakt ogs� her i landet. Norge kan ogs� risikere � bli bundet opp av vedtak innen EU og E�S.

KRYPTERINGSMETODER SOM KAN AVLYTTES

I mange land er det planer om � tilby krypto-tjenester som muliggj�r avlytting. USAs Clipper-initiativ er det mest kjente. Slike systemer vil beskytte mot utenforst�ende (forutsatt at det brukes sterke metoder), mens politi og andre offentlige myndigheter har mulighet til � skaffe seg kopi av n�klene som brukes, fortrinnvis etter rettslig kjennelse eller lignende.

Avhengig av hvordan tilgangen til n�kler kontrolleres, vil mange kunne akseptere et slikt system. Det er imidlertid mange �rsaker til at andre ikke �nsker � basere sikkerheten sin p� avlyttbare algoritmer.

    Bedrifter �nsker ikke � ta sjansen p� (selv en antatt liten) mulighet for at "utro tjenere" innen det offentlige skal f� tak i og lekke opplysninger.
    Privatpersoner eller andre kan ha opplysninger de ikke �nsker at myndighetene skal kunne f� tak i p� noen m�te. Det beh�ver slett ikke � v�re noe suspekt i et slikt �nske - for mange er det en del av privatlivets fred � slippe � gi flere opplysninger om seg selv enn n�dvendig.
    En del vil ikke stole p� at avlyttingen blir kontrollert strengt nok. Ut fra opplysninger om telefonavlytting b�de i Norge og i andre land kan det v�re gode grunner til en slik skepsis.

Vi mener at et avlyttbart system godt kan tilbys som en offentlig tjeneste, men ikke uten at annen sterk kryptografi er tilgjengelig for dem som �nsker det.

NHDS RAPPORT OM UTVIKLING AV NASJONAL KRYPTOPOLITIKK (6. APRIL 2001)

Denne rapporten er i all hovedsak positiv i forhold til EFNs vurderinger og anbefalinger. I en kort oppsummering av rapporten i hovedpunkt 12 fremmes det visse anbefalinger for en nasjonal kryptopolitikk:

    En grunnleggende positiv holding til bruk av kryptering.
    Avvisning av obligatorisk deponering av krypteringsn�kler som en innehar som privatperson.
    Oppmerksomhet rettet mot koordinering p� et internasjonalt, ikke bare europeisk niv�.
    Tilrettelegging av forholdene for sterkere vekst i nasjonal kryptoindustri.
    Minst mulig belastning av brukergrupper ved implementering av politikken.
    Utforming av politikken i tr�d med forslaget om bruk av elektroniske signaturer (jf NOU 2001:10).
    Utforming av politikken slik at den ikke krever endring i de alminnelige regler for saksbehandling i offentlig forvaltning, men sikrer bedre realisering av forvaltningslovens m�lsettinger ved overgang til elektronisk forvaltning.

Rapporten finnes fra:
http://odin.dep.no/nhd/norsk/p10001865/p10001878/024101-990051/index-dok000-n-n-a.html

Det finnes ogs� et sammendrag av rapporten her:
http://odin.dep.no/nhd/norsk/p10001865/p10001878/024101-990058/index-dok000-n-n-a.html

REFERANSER
B�ker:

    Scheiner, Bruce: (1994), Applied Cryptography: Protocols, Algorithms and Source Code in C. John Wiley & Sons. Inc.
    Garfinkel, Simson: (1995), PGP - Pretty Good Privacy. O'Reilly & Associates, Inc.

Artikler:

    Peachey, D.: "Euro-Clipper Chip Scheme Proposed". Communications Week no. 151 (18 Sept. 1995) s. 1-81.
    Thorel, J.: "EC Plans Encryption Rules in Bid to Police Information Superhighway". Nature vol. 377 no. 6547 (28 Sept. 1995) s. 275.

Internett:

    http://csrc.ncsl.nist.gov/
    (National Institute of Standards and Techology. Computer Security Resource Clearinghouse)
    http://www.faqs.org/faqs/cryptography-faq/
    (Omfattende dokument med sp�rsm�l og svar om kryptering; opprinnelig sci.crypt FAQ.)
    http://www.uninett.no/pca
    (UNINETTs kryptotjeneste)

Elektronisk Forpost Norge er en rettighetsorganisasjon som jobber med medborgerskap og juridiske rettigheter i IT-samfunnet.
www.efn.no.

Dette dokumentets adresse:
http://folk.uio.no/thomas/efn/krypto-notat.html

Sist oppdatert av   Thomas Gramstad     4. februar   2002.

Support the Blue Ribbon Campaign for Free Speech! Best Viewed With Any Browser Valid HTML 4.0! Frames Free! Ribbon Campaign Created with GNU Emacs www.linux.org - a GNU and better computer for you



