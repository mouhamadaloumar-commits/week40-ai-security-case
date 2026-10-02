# AI Security Case Investigation
## Case A – AI-phishing mot en kommun

**Kurs:** ITSX26  
**Examination:** Individuell examination, vecka 40  
**Valt case:** Case A

## 1. Sammanfattning

En kommunal förvaltning har fått flera mejl som är väl skrivna och ser ut att komma från intern IT-support. I mejlen uppmanas medarbetarna att logga in via en länk för att inte förlora åtkomsten till ett internt system. En medarbetare har öppnat länken men säger att inga inloggningsuppgifter skrevs in. Det finns inga bekräftade uppgifter om att någon har tagit sig in, och det är inte heller klarlagt om mejlen har skrivits med hjälp av AI.

Den största risken är att mejlen är ett phishingförsök där målet är att få medarbetare att lämna ut sina inloggningsuppgifter. Om ett konto blir komprometterat kan en angripare få obehörig åtkomst till information eller system. Hur illa det blir beror på kontots behörigheter och vilka säkerhetskontroller som redan finns.

Jag använder CIA-triaden (konfidentialitet, riktighet och tillgänglighet) i analysen. Jag tittar också på CIS Controls 6, 8 och 14, som handlar om åtkomstkontroll, logghantering och säkerhetsmedvetenhet. De åtgärder jag prioriterar är att undersöka mejlen och länken, gå igenom relevanta loggar samt kontrollera kontobehörigheter och rutiner för rapportering.

Min slutsats är att händelsen bör utredas snabbt, men att underlaget inte räcker för att säga att ett intrång har skett.

## 2. Fakta, antaganden och avgränsning

### 2.1 Givna fakta
- Flera medarbetare har fått välskrivna mejl.
- Avsändarnamnet liknar intern IT-support.
- Mejlen uppmanar mottagarna att logga in via en länk för att behålla åtkomsten till ett internt system.
- En medarbetare har öppnat länken.
- Medarbetaren säger att inga inloggningsuppgifter lämnades.
- Det finns inga bekräftade uppgifter om intrång.
- Det är inte fastställt om AI har använts för att skapa mejlen.

### 2.2 Hypoteser och antaganden
Mejlen kan vara ett phishingförsök, och länken kan leda till en falsk inloggningssida. AI kan ha använts för att skriva mejlen, men det är inte bekräftat. Det här är bara möjligheter som måste undersökas innan de kan behandlas som fakta.

### 2.3 Sådant som behöver kontrolleras
- Vilken webbadress länken går till.
- Om avsändaradressen och e-posthuvudena visar tecken på förfalskning.
- Om användaren skrev in uppgifter eller laddade ned något.
- Om autentiseringsloggarna visar ovanliga inloggningsförsök.
- Om fler mottagare har klickat på länken.
- Vilka behörigheter det berörda kontot har.

### 2.4 Avgränsning
Jag begränsar analysen till det beskrivna phishingförsöket, risken för obehörig åtkomst till konton och vad det i så fall kan få för följder för kommunens information och interna system. Fokus ligger på CIS Controls 6, 8 och 14. Underlaget innehåller ingen bekräftad incidentutredning.

## 3. Tillgångar och händelsekedja

### 3.1 Tillgångar som berörs
1. **Medarbetarkonton:** ger åtkomst till interna system och information.
2. **Identitetstjänster:** sköter inloggning och åtkomst.
3. **Information i interna system:** kan läcka eller ändras om ett konto missbrukas.
4. **Verksamhetssystem:** används i kommunens dagliga arbete.
5. **E-postsystem och säkerhetsloggar:** behövs för kommunikation, för att upptäcka problem och för att utreda dem.

### 3.2 Möjlig händelsekedja
1. Mejlen skickas till flera medarbetare.
2. En medarbetare öppnar länken.
3. Länken kan leda till en falsk inloggningssida.
4. Om uppgifter lämnas och angriparen kan använda dem kan angriparen få åtkomst till kontot.
5. Beroende på behörigheterna kan information läsas eller ändras, eller så kan verksamheten påverkas.

Steg 3–5 är sådant som kan hända, inte bekräftade fakta.

## 4. CIA-analys och enkel riskbedömning

### 4.1 Konfidentialitet
Konfidentialiteten kan påverkas om en angripare kommer åt ett konto och läser information som kontot har behörighet till. Ingen informationsläcka är bekräftad.

### 4.2 Riktighet
Riktigheten kan påverkas om ett obehörigt konto används för att ändra information i interna system. Ingen sådan ändring är bekräftad.

### 4.3 Tillgänglighet
Tillgängligheten kan påverkas om konton eller system missbrukas så att medarbetare förlorar åtkomst eller verksamheten störs. Ingen sådan störning är bekräftad.

### 4.4 Enkel riskbedömning

| Risk | Sannolikhet just nu | Möjlig konsekvens |
|---|---|---|
| Insamling av inloggningsuppgifter | Medel | Hög om ett konto med viktiga behörigheter komprometteras |
| Obehörig åtkomst till information | Låg–medel | Hög, beroende på information och behörigheter |
| Obehörig ändring av information | Låg | Medel–hög, beroende på system och data |
| Störning i verksamhetssystem | Låg | Medel–hög, beroende på hur viktigt systemet är |

Bedömningarna är preliminära eftersom jag har begränsad information. De bör ses över igen när det finns mer evidens.
