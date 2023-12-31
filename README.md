MEMORY GAME

1. UVOD

Za svoj završni projekt iz predmeta Objektno programiranje izabrao sam memory igricu. Ovu temu sam izabrao prvenstveno iz razloga što mi je izgledala jednostavna za odraditi i tipičan je primjer projekta kroz koji se može puno toga naučiti. S obzirom da sam odlučio raditi Interface za ovu igricu te sam se malo puta sreo sa nečim sličnim, htjeo sam i ponešto naučiti.

Memory je vrsta igrice gdje korisnik ima određen broj karata za stolom i ima mogućnost birati dvije karte koje želi otkriti. Ako su karte iste, ostaju otkrivene, no ako su različite, skrivaju se. Igrica je gotova tek kada su otkriveni svi parovi za stolom. U završnom projektu pisati ću općenito o igrici, opis izrade završnog projekta, problemi i moguće nadogradnje. Program u kojem sam radio projekt je RAD Studio 12.

2. OPĆENITO

   2.1 Igra pamćenja

   Memory ili na Hrvatskom igra pamćenja, dječja je igra gdje igrač bira parove kartica i testira se vlastito pamćenje. Društvena vrsta je igre gdje je pobjednik onaj koji je otkrio najviše parova među karticama. Završetak igre je kada su sve kartice otkrivene. U programiranju, jedan je od najboljih vrsta projekata za testiranje naučenog.

   2.2 RAD Studio

   Rad Studio je vrsta aplikacijskog softvera za izradu Win32 aplikacija. Sastoji se pregršt alata za izradu aplikacija koji pojednostavljuju izradu. Alati su dostupni u različitim verzijama, te trenutna verzija studia je 12. Jedna od posebnih značajki Rad Studia je ta što se može kreirati grafičko sučelje povlačenjem i ispuštanjem komponenti iz palete sa alatom na površinu na kojoj će biti aplikacija. Može se također aplikacije prilagoditi verziji Windows sustava koji se koristi.

3. OPIS PROJEKTA

   3.1 Instalacija projekta na računalo

   Instalacija projekta vrši se tako što se prvo instalira RAD Studio preko linka: https://www.embarcadero.com/products/rad-studio/start-for-free gdje se moraju unijeti podaci kako bi mogli instalirati program, jer ovaj program nije besplatan. Kada se program instalira, potom se instalira memory-oop.zip datoteka. Raspakiramo zip datoteku gdje ćemo imati folder memory u kojem se nalaze sve potrebne datoteke za igricu. Nakon toga otvaramo RAD Studio te otvaramo naš projekt tako što u izborniku File -> Open project i pronašemo naš projekt te otvorimo cbproj datoteku Project1.cbproj.

   3.2 Izrada projekta

   Prilikom izrade projekta trebali smo izabrati alat sa kojim ću napraviti Memory. Imali smo raznih opcija te je najjednostavnija opcija bila izrada preko RAD Studia jer je jednostavan za korištenje te ima već gotove komponente za ubacivanje. Prvo smo morali smislti kako će izgledati aplikacija te smo pomoću programa za izradu dizajna za aplikacije i slično Figma, izradili dizajn aplikacije.

   Dizajn aplikacije smo probali napraviti što jednostavnije, te je ideja bila da su memory kartice zapravo gumbi koji kad se pritisnu, prikaže se vrijednost gumba i ako se par pronađe, vrijednosti ostaju na gumbima, no ako se gumbovi ne poklapaju, vrijednost se pomakne. Kreirali smo projekt u RAD Studio tako što smo kreirali projekt preko Multi-Device Application – C++ Builder, koji automatski već napravi sučelje na kojem se može raditi projekt te je kod povezan sa tim sučeljem.

   Kreirali smo cpp flie za kod sa funkcijama, fmx file sa interfacom te header file sa pozvanim funkcijama. Unutar fmx file smo kreirali sučelje po dizajnu tako da smo stavili naslov i container unutar kojeg će mi se kreirati gumbi koji predstavljaju memory kartice. Nakon toga prešli smo u cpp file gdje smo kreirali klasu za karte koja se sastoji od vrijednosti kartice i boolean vrijednosti koji pregledava je li kartica otvorena ili nije.

   Nakon toga kreirali smo deset kartica sa zadanim vrijednostima te smo ih sve zajedno spremili u vektor gdje će biti pohranjene. Unutar glavnog koda smo koristili funkciju random_shuffle iz datoteke algorithm koja će nam kartice unutar vektora razmjestiti nasumično. Nakon toga smo izračunali koliko ćemo imati redova te koliko će gumbova ić po redu. Te vrijednosti nam trebaju kako bi mogli kreirati gumbove te da ih ravnomjerno smjestimo unutar container-a. Funkcijom new Tbutton kreirali smo gumbe te smo ih spremili u container. Zadali smo im visinu i širinu i odredili na kojim X i Y pozicijama će se nalaziti. Napravili smo vektor sa gumbima koji će nam kasnije poslužiti prilikom pronalaženja vrijednosti gumba. Na kraju smo na svaki gumb dodali funkcionalnost te smo tu funkciju nazvali ButtonClick.

   ButtonClick funkcija sastoji se od pokazivaca Sender koji klikom na gumb označava taj gumb i daje tom gumbu funkcionalnost ButtonClick funkcije. Unutar funkcije imamo vrijednost clickedButton koji je zapravo pokazivač i dohvaća pokazivač na kliknuti gumb. Preko vrijednosti index uzimamo indeks od tog gumba i unutar vektora sa kartama mijenjamo boolean vrijednost da je karta otvorena te da nam se prikazuje vrijednost tog gumba. Napravili smo i vektor sa odabranim kartama gdje se pritiskom na gumb, taj gumb sprema u vektor picks. Nakon toga smo napravili uvjet gdje se pita ako vektor picks ima 2 člana, poziva nam se funkcija CheckCards.

   Pozvali smo funkciju CheckCards u header file-u te smo je napravili u cpp file. Unutar te funkcije uzeli smo prvi i drugi član iz vektora picks te smo pomoću funkcije find pronašli njihove indekse unutar vektora sa kartama. Ako ih je pronašao ulazi u uvjet gdje smo inicijalizirali indekse tih dviju karata te ispitali da li se vrijednosti tih dviju karata poklapaju. Ako jesu gumbi se otvaraju, ostaju otvoreni i ne mogu se više pritisnuti. Ako se ne poklapaju boolean vrijednost se mijenja i sa gumba se miče vrijednost, koja više nije vidljiva. Nakon svega toga na kraju se briše sve iz vektora picks naredbom clear.

   3.3 Problemi i moguća poboljšanja

   Kod ovoga projekta najveći problem je bio pronaći alat preko kojega ćemo napraviti igricu, a jedan od problema je bio zadati veličinu containera gdje ćemo spremiti karte. Jedino poboljšanje kod ove igrice je da napravimo nekakvu stanku od naprimjer sekunde ili dvi prije pregledavanja parova kartica. Tako ćemo imati u uvid koja je vrijednost druge kartice.

4. ZAKLJUČAK

Za izradu memory igre trebali smo prvo osmislit kako će igrica funkcionirat te kartice koje će prikazivati parove, kako će biti prikazane u interfacu. Također, trebali smo se dosta upoznati sa RAD Studiom i komponentama koje ćemo koristiti pri izradi aplikacije.

Biblioteke koje smo trebali uključiti su algorithm, string i vector, gdje smo napravili klasu za karte koje su se sastojale od vrijednosti i boolean vrijednosti koja provjerava je li karta vidljiva ili nije. Karte smo spremali u vektor karata gdje smo koristili funkciju za poslagat ih nasumično.

Kod se sastoji od dvije funkcije gdje funkcija CheckCards() provjerava dvije izabrane karte i ako su iste drži ih otkrivenim, no ako su različite skriva ih. Funkcija ButtonClick() daje funkcionalnost komponentama koje predstavljaju karte. Klikom na komponentu prikazuje se vrijednost te karte i ako ta karta odgovara drugoj ostaje otkrivena, no ako ne odgovara, skriva se. U glavnom dijelu koda smo kreirali točno određeno komponenti koliko ima napravljenih karata.

Testiranjem igre zaključili smo da sve radi kako smo zamislili, no smatramo da se igra može unaprijediti tako da stavimo interval pregledavanja karte tako da nam se prikaže i druga vrijednost karte.

5. LITERATURA

   - https://zir.nsk.hr/islandora/object/etfos%3A1581/datastream/PDF/view
   - https://docwiki.embarcadero.com/RADStudio/Athens/en/What_Is_RAD_Studio
