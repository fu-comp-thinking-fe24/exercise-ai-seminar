# AI-workshop

Nedan följer ett antal uppgifter / frågor som ni utför / svarar på efter bästa förmåga. På alla frågor där ni inte enbart skall klistra in kod vill jag att ni svarar i minst 3 meningar. Går åsikterna inom gruppen isär så skriver ni ner båda svaren. Det finns inga dåliga svar, däremot finns det för korta svar. För att testa den JavaScript 

Frågorna och uppgifterna i detta kapitel syftar på att få er att fundera på vilket sätt ni kan / bör använda AI i er utbildning.

## AI och datalogiskt tänkande

### 01

Be ChatGPT och AIZO att applicera de fyra datalogiska delprocesserna på tärningsspelet **Stegen** från veckans övningskompendium.
Skiljer sig svaren åt, och isåfall på vilket/vilka sätt?

### 02

Be ChatGPT och Aizo att utifrån sina skapade flödesscheman även skapa pseudokod för spelet.
Ser båda svaren likadana ut, eller hur skiljer de sig åt?
Klista in ett av svaren och skriv från vilken tjänst lösningen kommer från.

### 03

Be ChatGPT och Aizo att fixa den färdiga JavaScript-koden för spelet, samt att logga ut kontroller och resultat i konsollen. Testa koden i det medskickade programmet om det fungerar och redovisa resultat.


## AI som studiekamrat

### 04

Hur tror ni att ChatGPT och Aizo skulle lösa större och mer komplicerade kodproblem? Var någonstans går gränsen tror ni för vilken typ av uppkodning där det skulle börja uppstå problem? 

### 05

Klistra in nedanstående CSS och be ChatGPT och Aizo att förklara vad som händer.

```
box-shadow: 12px 12px 2px 1px rgba(0, 0, 255, .2);
```

Vilka språkliga skillnader, om det finns några, kan ni se?

### 06

Klista in följande prompt i ChatGPT:

```
Skriv om följande kod så att den fungerar:

import { errorHandler } from "../../middlewares/errorHandler.mjs";
import { validateKey } from "../../middlewares/validateKey.mjs";
import { validateRegistration } from "../../middlewares/validateRegistration.mjs";
import { sendResponse } from "../../responses/index.mjs";
import middy from '@middy/core';
import { db } from "../../services/db.mjs";
import { hashPassword } from "../../utils/index.mjs";

export const handler = middy(async (event) => {
    const user = JSON.parse(event.body);

    try {
        await db.put({
            TableName: 'user-db',
            Item: {
                username : user.username,
                password : await hashPassword(user.password)
            }
        }); 
    } catch(error) {
        return sendResponse(404, { message : 'Could not add user'});
    }

  return sendResponse(201, 'Registration successful!');
}).use(validateKey())
  .use(validateRegistration())
  .use(errorHandler());

```

Upprepa sedan steget ytterligare tre gånger genom att skriva ```Skriv om följande kod så att den fungerar:```, och klistra in den kod ChatGPT föreslagit under föregående runda.

Får ni någon gång tillbaks samma kod som ni först skickade in? Gissningsvis kommer ChatGPT lägga till ```.promise()``` i slutet av följande del i koden:

```
await db.put({
    TableName: 'user-db',
    Item: {
        username: user.username,
        password: hashedPassword,
    },
}).promise();
```

Detta är en utdaterad funktion som inte längre fungerar på den typ av databasanrop vi gör. Varför tror ni att ChatGPT isåfall föreslår den lösningen?

### 07 - Anpassa ChatGPT

Be ChatGPT att beskriva skillnaderna mellan begreppen *pattern recognition* och *abstraction*, samt att ge exempel.

Klicka därefter på er profilbild uppe i det högra hörnet, och välj därefter alternativet *Anpassa ChatGPT*.

I det övre fältet skriver du in följande:

```
Jag är en nybörjare på webbutveckling som nyligen påbörjat mina studier inom frontendutveckling.
```

Och i det undre fältet skriver du in detta:

```
Jag vill att du förklarar saker för mig som att jag vore en nybörjare. Jag vill heller inte ha några raka svar, utan snarare tips på hur jag skall tänka för att lösa uppgiften själv.
```

Testa därefter att ställa samma fråga som innan om skillnaderna mellan begreppen *pattern recognition* och *abstraction*.

Skiljer sig svaren åt, och isåfall på vilket sätt? Märker ni om er anpassning gjorde någon skillnad.

### 08

Klistra in följande prompt i ChatGPT:

```
Kan du skapa en funktion som tar emot ett ord och returnerar ordet med en stor bokstav i början, samt efter alla mellanslag och bindestreck?
```

Ta sedan bort era anpassningar och ställ samma fråga igen. Märker ni några skillnader i sättet som ChatGPT svarar?

### 09

I vilka scenarion kan ni som **studenter** känna att det är okej att be AI om hjälp? Och i vilka scenarion är det inte okej?

### 10

Förutom att åka dit för fusk, diskutera vilka de tre största riskerna för er som **studenter** är att använda er av AI verktyg för att lösa era uppgifter.

## AI som kodkompis

Titta på [denna film om Github Copilot](https://www.youtube.com/watch?v=hPVatUSvZq0).

### 11

Vilka styrkor och svagheter / risker ser ni hos Github Copilot för er som **studenter**?

### 12

Kan ni se några scenarion för er som **studerande** där Github Copilot skulle vara okej att använda?

### 13

Vad tycker ni verkar vara mest "najs" med Github Copilot?

## AI i yrkeslivet

### 14 

Hur ser ni på våra roller som utvecklare i framtiden, där vissa oroliga röster höjs inför hotet om AI som skall ta över våra jobb på lång sikt?

### 15

Vilka risker ser ni med att använda sig av AI som en källa för kodskrivande i yrkeslivet?

## AI Generellt

### 16

Vilka andra AI tjänster kan vara relevanta för oss utvecklare att känna till och använda oss utav. Leta reda på 3 tjänster och skriv 3-4 menigar om vardera.

### 17

Av de verktyg som ni letat upp samt de som tagits upp i tidigare frågor, vilket tror ni att ni skulle ha mest användning av i er roll som **studerande**, samt i er yrkesroll? Motivera.




