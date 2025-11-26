# AI genererad kod eller mänskligt skriven kod
Syftet med rapporten är att jämföra och analysera fördelar samt nackdelar med kod skriven av en AI tjänst exempelvis ChatGPT eller Co-Pilot, kontra kod skriven av en människa. 
Är AI genrerad kod verkligen bättre? 

# Underhåll
Mänskligt skriven kod är genrellt sätt lättare att underhålla och felsök. Ifall en person har skrivit koden är det lättare att förstå och underhålla eventuella fel eller fortsatt utveckling av koden. Under utvecklingsprocessem hittar man redan fel som går att återgärda vilket leder till säkrare kod. Jobbar man tillsammans med en grupp kommer enkel och tydlig kod att underlätta för dina kollegor att vidareutveckla och förstå koden som är skriven.

Vid generering av AI kod skapas det kod för den givna frågan till AI-tjänsten. Ifall koden som frågas efter är en simplare och enkel kod kommer AI till större sannolikhet att skapa en snarlik kod jämfört med en människa. Det är större projekt där vi skapar stora databaser och applikationer som tar en människa veckor eller månader att skapa som AI blir ett större problem. Den genererade koden skapas med en modell vilket ofta leder till att förstå varför den genererade koden ens genereras. Detta gör det otroligt svårt att underhålla och felsöka. AI genrerar inte från ingenting likt en människa utan hämtar från existerande kodbaser och försöker skapa en så bra kod utifrån uppgiften.
Detta gör att koden inte skapas medsamma eftertänksamhet eller planering som en människa hade gjort det. Detta kan leda till oeffektiva lösningar eller helt enkelt ofungerande kod. 
Sammanfattningsvis så blir AI genererad kod svårare att underhålla då den skapas utan eftertanke och därför behöver inte alltid all kod vara logisk. Där skiljer sig den mänskligt skrivna koden då den oftast är genomtänkt och många använder sig utav "clean code". Detta leder till en enklare kod att förstå och underhålla.

# Tekniska val
Programmering handla inte heller bara av ren kod. Det handlar även om struktur och artitektur i applikationen. Människor kommmer oftast att göra sina val av ramverk till vilket ramverk som kommer att passa applikationen bäst. AI väljer oftast den snabbaste och enklaste lösningen. Detta leder till dåligt strukturerade applikationer där flera tekniska val inte alltid passar ihop eller är det optimala för just den applikationen. 

Varför gör AI inte optimala val?
Många AI modeller utgår inte från en större skala och väljer oftast därför de mest populära eller enklaste ramverken. Algoritmen baserar inte heller sitt val för framtiden eller underhåll utan väljer det som passar för tillfället, inte projektets långsiktiga utveckling. Ifall ett större projekt genereras med AI och fler komponenter behöver samarbeta tillsammans finns det stor risk att AI genererad kod inte alls fungerar bra tillsammans.

Detta är just varför människan och det mänskliga tänkandet alltid kommer att göra bättre tekniska val till ett projekt.

# Säkerhet
Många företag hanterar även känslig eller hemlig data som personuppgifter eller företagshemligheter. Skapas applikationen av en människa kommer antagligen programmeraren att ha i åtanke att just känslig information hålls säkert och följa viss standard. Det kommer att finnas personer som vill åt informationen och då måste den vara säkert förvarat. AI modeller genererar inte nära lika säker kod som är sårbar för attacker och når sällan upp till den standard som behövs i dagens samhälle. 

# Kundkrav
Vid utveckling kommer kunden ha krav på applikationen som utvecklas. AI modeller kommer utgå ifrån kraven men väldigt ofta kommer koden inte nå upp till alla krav, men ifall den gör sker oftast buggar eller andra fel som inte gör systemet till ett fungerande system. Skulle AI modellen genererar ett bra system med bra säkerhet och få buggar som kunde blir nöjd med, då återkommer vi till underhållningsproblemet. Vill kunden senare utveckla sitt system har en människa mycket sbårt för just detta. 
Så varför kan man inte fortsätta generera ett större system med AI?
AI kan absolut fortsätta att skapa större och större system, men hur bra kommer de nya delarna att fungera med de äldre? Ifall något i systemet buggar, kommer AI klara av att fixa problemet? Vidareutvecklingen av systemet kommer att vara bristfälligt med buggar och antagligen inte ens ett fungerande system.

# Kodexempel
Vad får vi för svar när vi frågar AI och vad finns det för brister?

Frågan som ställs till AI:
"Skapa en funktion i JavaScript för att skriva ut priset från svenska kronor till dollar"
** AI svar **
'''
function sekToUsd(sekAmount, exchangeRate) {
    if (typeof sekAmount !== "number" || typeof exchangeRate !== "number") {
        throw new Error("Belopp och växelkurs måste vara nummer.");
    }

    const usd = sekAmount * exchangeRate;
    return parseFloat(usd.toFixed(2)); // avrunda till 2 decimaler
}
'''

Vad saknas? 
* Det finns ingen säkerhetskontroll, ifall användaren skickar in infinity som också räknas som ett nummer kommer resultatet bli felaktigt.
* Ingen kontroll av negativa värden, växlar man pengar kan man inte växla -100kr vilket leder till fel.
* Felmedelandet är väldigt simpelt, det specificerar inte vad som är fel eller vilket argument som är felaktigt.



# Referenser
* https://www.unemyr.com/traditionell-kod-vs-ai-nar-ar-det-bast-att-valja-manuellt-skrivande-for-affarslogik/
* https://devsarch.com/blogs/ai-vs-human-code-who-writes-it-better/
* https://medium.com/@orbens/human-vs-ai-code-why-human-written-code-still-wins-24ec092f97f4
