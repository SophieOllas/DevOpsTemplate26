### Produktens livscykel

Vi började i M1 med en första commit av vår enkla anteckningsapp. I M2 lade vi till funktioner och färger genom separata grenar och pull requests. Vi granskade varandras ändringar och använde regler i GitHub för att styra hur kod fick komma in i main. Det märktes att samarbete kräver tydlig granskning, när vi ändrade samma titel uppstod en konflikt som vi behövde lösa manuellt.

I M3 använde vi Docker och Docker Compose för att bygga och köra appens frontend och backend tillsammans. Då blev det enklare att få en likadan miljö och kontrollera att appen fungerade. I M4 hittade vi ett fel i appens summering, efter att en anteckning togs bort räknades tecknen fortfarande med. Ett nytt test visade felet, och vi uppdaterade koden så att summeringen blev rätt.

I M5 kopplade vi tester och lintning till GitHub Actions. En pull request med en oanvänd import gav en röd kontroll och kunde inte mergas förrän vi rättade felet. I M6 automatiserade vi bygget och publiceringen av container images till GitHub Container Registry. Då behövde vi inte bygga och ladda upp varje image för hand.

I M7 skapade vi en VM manuellt i molnet, ordnade SSH-nyckel, nätverksregler och IP-adress och installerade Docker. Vi hämtade images och kontrollerade appen med curl och webbläsaren. I M8 beskrev vi i stället infrastrukturen med Terraform. Terraform kunde skapa en ny VM, och cloud-init installerade Docker och startade appen automatiskt. I M9 kopplade vi ihop publicering och driftsättning, när image bygget lyckas ansluter GitHub Actions till VM:en och hämtar den nya versionen.

### Vad går sönder utan automation?

Till exempel CD-steget skulle bli mer riskabelt för hand. Vi såg till att driftsättningen väntade tills image-bygget var klart. Manuellt skulle vi behöva komma ihåg rätt ordning, logga in på VM:en och köra kommandona varje gång. Det tar längre tid och ökar risken att appen kör en gammal version eller att ett steg blir fel.