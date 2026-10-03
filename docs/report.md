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
## 5. Koppling till CIS Controls 6, 8 och 14

### 5.1 CIS Control 6 – Access Control Management
CIS Control 6 handlar om hur användares åtkomst till system och information hanteras. Kommunen bör kolla vilka behörigheter det berörda kontot har. Om behörigheterna är begränsade blir skadan mindre om kontot skulle bli komprometterat.

**Verifiering:** Gå igenom kontots behörigheter och dokumentera om de följer kommunens regler för åtkomst.

### 5.2 CIS Control 8 – Audit Log Management
CIS Control 8 handlar om logghantering. Med hjälp av loggar kan kommunen se om det har förekommit ovanliga inloggningsförsök eller annan misstänkt aktivitet.

**Verifiering:** Skriv ner vilka loggar och vilken tidsperiod som har granskats, och om något avvikande hittades.

### 5.3 CIS Control 14 – Security Awareness and Skills Training
CIS Control 14 handlar om säkerhetsmedvetenhet och utbildning. Medarbetarna behöver kunna känna igen misstänkta mejl och veta hur de ska rapportera dem.

**Verifiering:** Kolla att det finns en tydlig rutin för rapportering och att medarbetarna känner till den.

## 6. Prioriterade säkerhetsåtgärder

### Åtgärd 1: Undersök mejlen och länken
Titta på avsändaradressen, e-posthuvudena och webbadressen som länken går till. Ta reda på om fler medarbetare har fått mejlet. Länken ska inte öppnas på en vanlig arbetsdator för att testa den.

**Varför:** Då går det att bedöma om mejlet är skadligt och vilka som kan vara berörda.

**Verifiering:** Dokumentera vilka mejl och länkar som har undersökts och vilka slutsatser som faktiskt stöds av evidens.

### Åtgärd 2: Granska loggar och kontot
Gå igenom relevanta inloggningsloggar, loggar från e-postsystemet och loggar från den berörda enheten. Leta efter ovanliga inloggningsförsök eller annan misstänkt aktivitet. Om det finns konkreta tecken på att kontot har utsatts för något bör kommunen skydda det enligt sina rutiner.

**Varför:** Det kan visa om någon har fått obehörig åtkomst.

**Verifiering:** Dokumentera vilken tidsperiod och vilka loggar som har granskats, och eventuella avvikelser. Att man inte hittar något betyder inte automatiskt att inget intrång har skett.

### Åtgärd 3: Förbättra rutinerna för rapportering
Se till att medarbetarna vet hur de rapporterar misstänkta mejl, och att de aldrig ska lämna ut inloggningsuppgifter via länkar de inte väntat sig.

**Varför:** Med tydliga rutiner blir det lättare att upptäcka och hantera misstänkta mejl tidigare.

**Verifiering:** Kolla att instruktionerna finns tillgängliga och att medarbetarna vet hur man rapporterar ett misstänkt mejl.

## 7. Teknisk koppling

Ett möjligt sätt att angripa är att skicka ett mejl som leder till en falsk inloggningssida. Om en användare skriver in sina uppgifter där kan angriparen försöka använda dem för att logga in på användarens konto.

Det är inte bekräftat att länken i det här fallet går till en falsk sida, eller att några inloggningsuppgifter har samlats in.

Kommunen kan undersöka händelsen genom att titta på mejlets tekniska information, länken och de inloggningsloggar som är relevanta. Om kommunen använder flerfaktorsautentisering bör den också kolla om det finns tecken på misstänkta inloggningsförsök.

Tekniska kontroller behöver kombineras med tydliga rutiner och begränsade behörigheter. Ingen enskild kontroll kan garantera att alla phishingförsök stoppas.

## 8. English Security Summary
A municipal department has received several emails that look like they come from internal IT support. The emails tell employees to log in through a link so they keep access to an internal system. One employee opened the link but says they did not enter any login details. No break-in has been confirmed, and it is not known whether AI was used to write the emails.

The emails may be a phishing attempt to steal login details. If an account is compromised, an attacker could get access to information or systems they should not see. How serious this is depends on the account's permissions and on the security controls already in place.

The analysis uses the CIA triad and CIS Controls 6, 8 and 14. I recommend checking the emails and the link, going through the relevant logs and account permissions, and making sure employees know how to report suspicious emails. There is not enough evidence to say that a security breach has happened.
## 9. AI- och källredovisning

Jag har använt ChatGPT (OpenAI) och Claude (Anthropic) som stöd för att förstå uppgiften och förbättra språket i min egen text. Jag har själv granskat AI-förslagen och ansvarar för den slutliga analysen och texten.

Jag ansvarar själv för analysen och de slutliga bedömningarna. Jag har gått igenom AI-verktygens förslag och försökt skilja mellan bekräftade fakta, antaganden och sådant som är okänt.

Jag har inte behandlat information från AI-verktygen som bevis. Det är fortfarande inte bekräftat att ett intrång har skett eller att AI användes för att skriva phishingmejlen.

Källorna som använts i analysen redovisas i `docs/references.md`.

## 10. Slutsats

Mejlen kan vara ett phishingförsök, men det finns inte tillräckligt med evidens för att säga att ett intrång har skett eller att AI har använts. Kommunen bör därför undersöka mejlen och länken, gå igenom relevanta loggar och kontrollera vilka behörigheter det berörda kontot har.

Det är också viktigt att medarbetarna vet hur de ska rapportera misstänkta mejl. Resultaten av undersökningen bör dokumenteras, och riskbedömningen bör uppdateras när det finns mer information.

