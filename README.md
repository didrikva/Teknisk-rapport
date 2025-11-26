# AI genererad kod eller mänskligt skriven kod
Syftet med rapporten är att jämföra och analysera fördelar samt nackdelar med kod skriven av en AI tjänst som exempelvis ChatGPT eller Co-Pilot, kontra kod skriven av en människa. 

# Underhåll
Mänskligt skriven kod är genrellt sätt lättare att underhålla och felsöka. Ifall en person har skrivit koden är det lättare att förstå och underhålla eventuella fel eller fortsätta med utvecklingen av koden. Under utvecklingsprocessen hittar man redan fel som går att återgärda vilket leder till en säkrare kod. Jobbar man tillsammans i en grupp kommer enkel och tydlig kod att underlätta för dina kollegor att vidareutveckla och förstå koden som är skriven.

Vid generering av AI kod skapas det kod för den givna frågan till AI-tjänsten. Ifall koden som efterfrågas är en simplare och enkel kod kommer AI till stor sannolikhet att skapa en snarlik kod jämfört med en människa. Det är vid utvecklingen av större projekt som kan ta en människa veckor eller månader att skapa, som AI inte blir lika pålitlig. Den genererade koden skapas med en specifik modell vilket ofta leder till att bara förstå varför den genererade koden ens genereras blir svårt. Bara det blir en utmaning att underhålla och felsöka koden. AI genrerar inte från ingenting likt en människa utan hämtar från existerande kodbaser och försöker skapa en så bra kod som möjligt utifrån uppgifterna den hittar.

Detta gör att koden inte skapas med samma eftertänksamhet eller planering som om en människa hade gjort det. Detta kan leda till oeffektiva lösningar eller helt enkelt ofungerande kod. 
Sammanfattningsvis så blir AI genererad kod svårare att underhålla då den skapas utan eftertanke och därför behöver inte alltid all kod vara logisk. Där skiljer sig den mänskligt skrivna koden då den oftast är genomtänkt och många använder sig utav "clean code". Vilket leder till en enklare kod att förstå och underhålla.

# Tekniska val
Programmering handla inte heller bara av ren kod. Det handlar även om struktur och artitektur i applikationen. Människor kommmer oftast att göra sina val av ramverk till vilket ramverk som kommer att passa applikationen bäst. AI väljer oftast den snabbaste och enklaste lösningen. Detta leder till dåligt strukturerade applikationer där flera tekniska val inte alltid passar ihop eller är det optimala för just den applikationen. 

Varför gör AI inte optimala val?
Många AI modeller utgår inte från en större skala och väljer oftast därför de mest populära eller enklaste ramverken. Algoritmen baserar inte heller sitt val för framtiden eller underhåll utan väljer det som passar för tillfället, inte projektets långsiktiga utveckling. Ifall ett större projekt genereras med AI och fler komponenter behöver samarbeta tillsammans finns det stor risk att AI genererad kod inte alls fungerar bra tillsammans.

Detta är just varför människan och det mänskliga tänkandet alltid kommer att göra bättre tekniska val till ett projekt.

# Säkerhet
Många företag hanterar även känslig eller hemlig data som personuppgifter eller företagshemligheter. Skapas applikationen av en människa kommer antagligen programmeraren att ha i åtanke att just känslig information hålls säkert och följer viss standard. Det kommer att finnas personer som vill åt informationen och då måste den vara säkert förvarat. AI modeller genererar inte nära lika säker kod vilket leder till en sårbarhet för attacker och når sällan upp till den standard som behövs i dagens samhälle. 

# Kundkrav
Vid utveckling kommer kunden ha krav på applikationen som utvecklas. AI modeller kommer utgå ifrån kraven men väldigt ofta kommer koden inte nå upp till alla krav, men ifall den gör sker oftast buggar eller andra fel som inte gör systemet till ett fungerande system. Skulle AI modellen genererar ett bra system med bra säkerhet och få buggar som kunde blir nöjd med, då återkommer vi till underhållningsproblemet. Vill kunden senare utveckla sitt system har en människa mycket svårt för just detta. Människan kan enkelt kommunicera och förstå kundens behov för att göra ett så bra system som är så nära kundens krav. Under utvecklingen kan även en människa återkoppla till kunden för uppdatering av systemet och eventuella frågor, det gör inte AI utan skapar direkt från den information som getts. 

Så varför kan man inte fortsätta generera ett större system med AI?
AI kan absolut fortsätta att skapa större och större system, men hur bra kommer de nya delarna att fungera med de äldre? Ifall något i systemet buggar, kommer AI klara av att fixa problemet? Vidareutvecklingen av systemet kommer att vara bristfälligt med buggar och antagligen inte ens ett fungerande system.

# Kodexempel
Vad får vi för svar när vi frågar AI och vad finns det för brister?

## Prompt 1

Frågan som ställs till AI: 

**"Skapa en funktion i JavaScript för att skriva ut priset från svenska kronor till dollar"**

**AI svar**

```
    function sekToUsd(sekAmount, exchangeRate) {
        if (typeof sekAmount !== "number" || typeof exchangeRate !== "number") {
            throw new Error("Belopp och växelkurs måste vara nummer.");
        }
    
        const usd = sekAmount * exchangeRate;
        return parseFloat(usd.toFixed(2)); // avrunda till 2 decimaler
    }
```

Vad saknas? 
* Det finns ingen säkerhetskontroll, ifall användaren skickar in infinity som också räknas som ett nummer kommer resultatet bli felaktigt.
* Ingen kontroll av negativa värden, växlar man pengar kan man inte växla -100kr vilket leder till fel.
* Felmeddelandet är väldigt simpelt, det specificerar inte vad som är fel eller vilket argument som är felaktigt.

## Prompt 2

Frågan som ställs till AI:

**"Skapa en funktion som returnerar alla primtal från en lista"**

**AI svar**

```
    function getPrimes(numbers) {
        return numbers.filter(isPrime);
    }
    
    function isPrime(num) {
        if (num <= 1) return false;
        if (num === 2) return true;
        if (num % 2 === 0) return false;
    
        const limit = Math.sqrt(num);
        for (let i = 3; i <= limit; i += 2) {
            if (num % i === 0) return false;
        }
        return true;
    }
```

Vad saknas?
* Det finns ingen typkontroll, ifall någon skickar in en sträng eller None kommer funktionen att krasha.
* Ingen säkerhetskontroll för tal som "infinity", det kommer att returneras som **true**.
* Ifall koden ska användas i ett större sammanhang bör inte funktionen "getPrime" vara en global funktion utan bör inporteras.

# När är AI användbart?
* AI kan vara användbart för att skapa en grund eller mindre enklare funktioner. Skulle man som programmerare ha absolut ingen aning om hur man ska påbörja ett projekt kan AI möjligtvis hjälpa till med en start. AI kan enkelt komma på ider som senare måste tittas igenom och ändras av en människa. 
* Många AI modeller har en mönsterigenkänning som många människor inte har. Detta kan underlätta att förstå och utgöra komplexare mönster som människor har svårare för. 
* Ifall ditt projekt baseras på något som redan skapats eller redan finns, kan AI hjälpa till att kolla upp brister och utveckling baserat på tidigare data angående ämnet. 
* AI kan hjälpa till att upptäcka nya ramverk eller nya sätt att utveckla på som kanske inte man själv hade tänkt på.


# Sammanfattning
## Bör vi undvika att använda oss utav AI?
Det enkla svaret är nej. AI kommer inte på många år om ens någonsin att ersätta mänskligt kodande av många anledningar. Människor har oftast erfarenhet, omdöme och ett fritt sinne att lösa problem med. Människor kommer enklare att förstå kundens behov, förstå kodens struktur, göra korrekt tekniska val och mycket mer för att underhålla ett starkt system. Ett mänskligt skrivet system kommer ha bättre säkerhet, lättare att underhåla och även mindre buggar.

## När bör vi använda AI?
AI bör användas som ett hjälpmedel till den männskliga utvecklingen. Vid korrekt användning av AI kan det vara ett bra hjälpmedel till människan för att utveckla system, AI bör aldrig själv användas till ett helt system. Istället för att helt skjuta ner iden av AI bör vi utnyttja möjligheten att förbättra de delarna människor inte gör lika bra och tillsammans komplettera varandra till ett perfekt system. Ifall vi ser AI som en miniräknare eller diskmaskin kan systemen som utvecklas kompletteras bra och utvecklandet förbättras.



# Referenser
* https://www.unemyr.com/traditionell-kod-vs-ai-nar-ar-det-bast-att-valja-manuellt-skrivande-for-affarslogik/
* https://devsarch.com/blogs/ai-vs-human-code-who-writes-it-better/
* https://medium.com/@orbens/human-vs-ai-code-why-human-written-code-still-wins-24ec092f97f4
* https://medium.com/@API4AI/ai-vs-human-code-review-pros-and-cons-compared-7fd04d093613

## Författare
Didrik Varma
