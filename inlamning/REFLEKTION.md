## Produktens livscykel

Vi börja med M1, med att göra vår första commit. I M2 skapa vi ny ruleset för vår branch och så ansvara en av oss för en funktion i backend och den andra för frontend. Vi commita ändringarna på våra egna branches och gjorde sedan var sin PR och reviewa dom. Så ändra båda av oss en rubrik i frontend, som skapa en konflikt, som vi löste.

I M3 fick vi lära oss att använda Docker. Vi körde docker compose för att bygga upp frontenden och backenden för våran app. Så laga vi .dockerignore filer för frontend och backend, där inkluderade vi cache filer som skulle ignoreras. I M4 uppstod ett fel av fel ordning av kod som måste fixas, det fixa vi enkelt med att flytta en block kod över en annan. Så fanns det också ett annat fel i backenden där det fattades en bit kod för att en uträkning skulle stämma. 

Till M5 lade vi till mer checks i vår ruleset och testade ifall de också funkade, som de gjorde. Så la vi också till workflow_dispatch i ci filen, som gjorde möjligt att köra run workflow på CI. I M6 automatisera vi bygget och publiceringen av container images, så måste vi inte mer manuellt göra det. 

I M7 skapa vi vår egna VM i molnet, laga SSH nycklar för båda, nätverksregler och IP adresser. På VM:en ladda vi ner docker och pulla både frontend och backend images. Sen vid M8 skapa vi en ny VM på Terraform och fick automatiskt installerat docker och startat apparna. Till slut på M9 koppla vi ihop allt till Github, alltså när images byggs så ansluts GitHub actions till VM:en.  


## Vad går sönder utan automation?

Ett bra exempel är testen som körs. I M4 missade vi kod som inte uppdaterade teckenantalet rätt efter att ta bort en note. Utan testet skulle detta fel ha kommit med på main branchen. Också i M5 såg vi hur checken hindrade vår avsiktligt fel kod från att merga till main. Om man skulle göra testen manuellt kan det lätt gå att man glömmer dem eller att man missar ett fel.  