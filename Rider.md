# Raider

**ärikasutajad**

kõik kasutajad. Iga kasutajatüüb saab teostada raideriga toiminguid.

**olemid, atribuudid**

omanik

loomiskuupäev

muutmiskuupäev

kasutajate nimekiri, kes on raideriga seotud

Pealkiri

arhiveeritud staatus (boolean)

tähistatud (starred) staatus (boolean)Raider_list

0..n pillirida

	instrument

	microfon

	kaabel

	staatus (boolean)

Raideriga seotud objektid, millega ollakse seotud

stage plan

soundengineersview

**sündmused ajas, mis muudavad raiderit süsteemis**

Ajalised sündmused, näiteks projekti algus või lõpp ei muuda raideri staatust-atribuute süsteemis.

**seosed teiste registritega**

Users - 1...n - Üks raider on seotud vähemalt ühe kasutajaga. Saab olla jagatud enamate kasutajate vahel.

Stage plan - 1 - Iga raider on seotud stageplaniga.

Channel list - 1 - Igast raideri tabelist tuletatakse channel list

Rights - Igal raideri kasutajal on teatud õigused raideri suhtes.

Invite - 0...n - Igal raider võib olla seotud invite’tega, mis saadetud välja kasutajatele, keda soovitakse projektiga siduda.

Project 0...n - Iga raider on seotud tavaliselt projektidega, aga ei pruugi.

**ärieesmärgid**

Raideri tabeli loomine, selle muutmine vastavalt vajadusele. Raideri tabeli põhjal geneeritakse sound engineers view ehk channel list. Üldeesmärk - kiirendada tööd, ülevaadet, ülesleidmist, koostamist, haldust. Raideri alusel agregeerivad-summeerivad funktsioonid. Jagamine erinevate kasutajate vahel. Raideri info stuktureeritud kujul, et infovahetus ja koostamine muutuks lihtsamaks, kiiremaks, intuitiivsemaks ning ülevaatlikus selgemaks.

**Põhiobjektid, alamobjektid**

**Raider** (instrumendid, üldandmed)

**stageplan-**> raideris olevad instrumendid kujutatakse stageplanil süsteemi poolt. Saab sobivalt ümber tõsta

**channel** **list** -> raideris olevad instrumendid aluseks channel listi geneerimiseks (sound engineers view)

**raider_item** -> raider koosneb raider_itemitest: veerud - instrument, kaabel, mikrofon, staatus

**kasutusjuhud üldised, kasutajad, eesmärgid, uml  - algusest + mockupid**

Raiderite tähistamine (star)

	Kõik kasutajad, kes raideriga seotud.

		Iga kasutaja saab ära märgistada talle sobivad raiderid. Selle aluseks, et iga raider on unikaalne ühele kasutajale. See tähendab, et ühe kasutaja poolt tehtud tähistus ei ole nähtav teisele sama raideri kasutajale.

Infovaated: saab teostada library vaates, raideri detailvaates.

Näide:

1. Kasutaja valib library view’s või sidebar’ilt ühe või mitu raideriobjekti. Pärast selekteerimist saab kontekstmenüüst valida "Star selected riders". Teine variant on, et igal raideri objektil on olemas võimalus teda tähistada.

2. Igal raideril on detailvaates lahter sisuga "Star current rider" vms.

Raideri koostamine

Iga süsteemi kasutaja saab luua

Esialgne raideri loomine, kus määratakse ära tema detailandmed ja vajadusel täidetakse ära channel list.

Infovaade: raideri koostamist saab alustada library view’s (pluss+märk ikoon). Samuti sama võimalus sidebar’ilt (pluss+märk).

Sammud:

1. Sisestatakse raideri nimi esmasesse avanevasse dialoogiaknasse

2. Kasutajale avaneb seejärel detailvaade

3. Siin saab sisestada väljadesse täiendavaid ja täpsustavaid andmeid: kuupäev, üldkirjeldus raiderile.Lisaks vabaväljad - personel, transport and luggage, schedule, performing area, sound system, FOH and FOH equipment, monitoring, makeup, wireless

4. Raideri tabeli enda koostamine pole kohustuslik. Kasutaja saab hetkel raideri salvestada.

5. Juhul, kui kasutaja otsustab pillitabeli ära täita, siis reeglid oleksid:

    1. Tabel koosneb 3st veerust. 1. veerg - pill (kohustuslik) 2. veerg - mikrofon3. veerg - kaabel4. veerg - staatus

Iga elementi saab valida dropdown’ist, millele toeks input field, mis aitab tulemusi filteerida. Näiteks sisestades input fieldi "kitarr", siis süsteem pakub erinevaid kitarri variante (basskitarr, elektrikitarr jne), millest kasutaja valib dropdown menüüst sobiva. Kasutaja sisestada ka vabas vormis pilli. Sel juhul on ta “other” tüüpi süsteemi jaoks ja ei saa olla aluseks stageplani koostamiseks. Aluseks on see, kas kasutaja poolt sisestatud pilli nimi kattub süsteemis oleva pilli nimega.Veergude mikrofon ja kaabel puhul sama sisestusmehhanism, küll aga ei ole kohustuslik sisestada. Staatus veergu saab sisestada kirjelduse, mis seis on antud pilliga (väärtused nagu “tellitud, vaja tellida, puudu, laval…”.)Tabelis olevaid ridu saab liigutada ülesalla üksida ja koos teiste ridadega. -  Juhul kui liigutan ühte eset, siis teised peavad sellega koos kaasa liikuma (näiteks saan valida kolm eset ja neid korraga liigutada). NB! Kui koos ridasid liigutada, siis saab liigutada järjestikku olevaid ridasid.Tabelisse saab lisada juurde ka uusi veerge.

6. Tabeli lõpus on summeeruvad väljad: 

1. Pillide arv kokku

2. kui palju läheb vaja kaablit x, kaablit y (arvestus kaabli tüübi järgi)

7. * Sisestamisloogika on sarnane Excelile -  saan tab’iga edasi liikuda, Enteriga uut rida tekitada. Juhul kui olen rea lõpus ja vajutab tab tekitatakse mulle uus rida uuesti juurde. Ei pea kasutama hiir, et tabelit täita!

NB! Kogu protsessi jooksul toimub automaatne salvestamine. Küll aga on olemas undo võimalus. Kasutajaliideses selleks vastav funktsioon.



Raideri lisamine projekti

	Raideri looja

		Üksiku raideri sidumine projektiga.			Infovaade: ühelt poolt läbi dragdrop’i library views, kus raidereid lohistada projekti ja vastupidi. Nii saame siduda raiderit projektiga. Samamoodi saame lohistada raideri objekte sidebar’ilt sidebari projektidesse või siis library objektidesse. Täpsemalt kirjeldatud siin [https://docs.google.com/document/d/12YNjWIBbf2VHZzkNrq8JWxgRZB54LTrfSf2dXiQ0YlE/edit#heading=h.uqrzih92vnkj](https://docs.google.com/document/d/12YNjWIBbf2VHZzkNrq8JWxgRZB54LTrfSf2dXiQ0YlE/edit#heading=h.uqrzih92vnkj)Küll aga saab siduda projekti raideriga ainult projektilooja ehk admin õigustega kasutaja.

Raideri sidumine teiste kasutajatega

Admin (st. raideri looja) või kasutaja, kellele on antud admin õigused

Raideri esmane looja on ka raideri admin õigustega kasutaja. Temal õigus teisi kasutajaid raideriga liidestada ja anda neile vastavad õigused

Infovaade: tegevus toimub raideri detailvaates eraldi tabil

Näide:

1. Kasutaja on loonud raideri

2. Kasutaja avab loodud raideri detailvaade 

3. Valib kasutajate tab’i.

4. Kasutajate lisamine toimub autocomplete meetodi põhjal. Selleks on väli "lisa kasutaja". Autocomplete toimib emaili põhjal. Süsteem annab vastuseks sisendile nende kasutajate emailid, kes on süsteemis ennast ära registreerinud. Vastused tulevad dünaamiliselt sisestamise käigus. 

5. Igale lisatud kasutajale peab vastavusse seadma õigused, mis tal raideri suhtes on. Selleks on iga kasutaja emaili kõrval (mis eelnevas punktis sai sisestatud) väli väärtustega "õigus lugeda", “õigus lugeda, muuta, kustutada” (admin õigused, sh lisada teisi kasutajaid).Kolmandaks selgitus kasutajale, miks temaga raiderit jagati (lisaväli, pole kohustuslik, vabatext). 

6. Iga kasutaja, kes raideriga liidetakse, saab teavituse, mis talle kuvatakse sisse logimisel ühekordselt. Näide: "Kasutaja x soovib teiega jagada raiderit nimega..... Kas soovite vastu võtta?"

7. Kasutaja saab aktsepteerida kutset või mittenõustuda. Aktsepteerimise korral ilmub raider nähtavale tema library view’i ja muudesse kohtadesse, kus näeb tema raidereid. Nt sidebar. Samuti saadetakse kutse välja saatnud kasutajale süsteemi sõnum, et kasutaja võttis kutse vastu. Mitteaktsepteerimise korral saadetakse ka kutse saatjale tagasi sõnum, et kasutaja ei nõustunud raideriga liituda.

8. Liidestatud kasutajal on need õigused raideri suhtes, mida talle eelnevalt määrati.

Raideri share’imine

Kõik kasutajad, kes on raideriga seotud

Võimalus süsteemist välja eksportida pdf kujul raiderit.

Infovaade: funktsionaalsus on raideri detailvaates. Samuti kui selekteerida raiderid library views või sidebaril. Seejärel valides share (parempoolne kontekstmenüü, mis avaneb hiirega) VÕI kui on ära selekteeritud nii sidebar’il/library’s soovitud raiderid, siis üleval library kohal tekib nupp "Share rider". Raideri jagamine toimub PDF kujul.

------------------------------

*Sound engineer näeb ka bändi raiderit, AGA talle tehakse bändi raiderist süsteemi poolt automaatselt koopia see tähendab, et ta ei muuda bändi raiderit!!!! Kui muudatused on tehtud, siis sound engineer saab saata koopia bändile (vajadusel) ehk shareda vastu neile.*

*----------------------------------*

Raideri õiguste määramineSee raider on seotud vastava projektikasutajatega. Nad saavad neid lugeda. Muuta ja kustutada saab sõltuvalt rolllist - projektijuht saab muuta/kustutada. 

Projektijuht määrab projekti teised kasutajavad ja nende vastavad õigused raiderit muutaVanu raidereid saab kopeerida uude projekti ning seal muuta

------------------------------------

Kuidas õigustega teeme täpsemalt. Kõige detailsem oleks vist teha eraldi projekti ja raideri õigused. Et nt bänd saaks muuta projekti all olevat raiderit mingi kuupäevani aga projekti enda andmeid muuta ei saaksReasonable. Hetke seisuga kasutajate õiguste analüüs puudub. Kuid eraldiseisvad projetki ja raideri õigused on mõistlik.

Hetkel on olemas meil tüübid nagu projektijuht/projekti looja)?

Raiderilooja? Keegi kes loob raideri?

Projektil on kõik õigused projektijuhil. Projektijuht saab hallata projektikasutajaid ja nende õiguseid.

Kui projekti lisatakse raider, siis raideriloojal (ja projekti loojal ka?) on kõik õigused raideri suhtes.

Raideri looja saab määratleda, kes ja kas seda raiderit veel saab muuta/lugeda jne.

Kui on olemas iseseisvad raiderid (ilma, et oleks projektis) ja projektides olevad raiderid, siis kui iseseisev raider tõstetakse projekti, siis kas selles projetkis oleva raderi kasutajate õigused on "sõltumatud" iseseisva raideri õigustest? Näiteks: alguselt iseseisev raider Z on õigustega ABC (sest raiderilooja annab need õigused), kuid kui raider Z tõstetakse projekti X, siis raider Z'i õigused projektis saab muuta CBA peale. Default on projektis oleva raideri õigusteks see, et projektijuht saab muuta raiderit.

