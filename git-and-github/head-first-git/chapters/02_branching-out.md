# Branching Out

Branches tillåter dig att arbeta på flera olika disconnected pieces of work samtidigt på samma kodbas, oberoende utav varandra.

När vi arbetar på en branch så är våra commits sekventiella, dom radas upp på varandra.

Så ifall du är halvt färdig med att arbeta på en ny funktion i en sido-branch, men sedan behöver fixa en bugg i koden som är i produktion, så kan du inte försöka fixa den i din nuvarande sido-branch.

För när du sedan gör en PR till vår main-branch så kommer även den halvfärdiga funktionen du arbetade tidigare på att följa med!

Därför behöver du skapa ytterligare en ny separat branch, där du bara försöker lösa buggen. Utan tidigare commits.

> Viktigt är att skapa den nya branchen när vi är på vår main branch. För att en branch börjar där branchen vi är på slutar. Så om vi skapar en ny branch ifrån vår branch med massa experimentell kod så kommer denna och dess commits att kopieras till den nya branchen.

För commit radas upp på varandra och du kan inte bara välja att pusha din senaste commit.

> **En commit representerar en punkt i tiden.**

> **En branch representerar ett flertal commits.**

Så branches är olika commit histories, inom samma repository.
En branch är bara en pointer till commits.

Och commits är bara en snapshot av allt du har lagt till i index, tillsammans med massa metadata och commit message. I andra ord, en commit minns staten av din Index när du gjorde din commit.

> 💡 “Every time you switch branches, Git rewrites your working directory to look like it did when you made the most recent commit on the branch you just switched to.”

---

### Merging:

Vi kan se branches som en bra tv-serie. Den har en main plot, men grenar ibland ut till små mini-historier, för att sedan knyta ihop allt igen till vår main plot.

Det är så vi kan se våra branches.

Dom är till för att vi sedan ska knyta ihop dessa med vår main branch.

Att flytta ihop kod som skapades i olika branches kallas för **merging.**

Kommandot för detta är: **git merge**

Att mergea i git inkluderar oftast två branches, vi har branchen som vi är på, som kan kallas för vår “proposer”. Och branchen vi vill mixa in, vi kan kalla det för vår proposee.

Tänk dig att du bakar en tårta.

Vi kan börja förbereda glasyren medan vår tårtbotten håller på att svalna.

Vid en tidpunkt så vill vi mixa ihop dessa två. Här hade vår tårtbotten varit vår “proposer”, och vår glasyr hade varit vår “proposee”.

Översätter vi detta till git så ser det ut såhär:

Vi har två branches:

**`*bake-cake`**
`prepare-icing`

Vi är färdiga med båda branches, så vi hoppar över till bake-cake, här använder vi sedan kommandot **`git merge prepare-icing`** för att mergea prepare-icing till bake-cake.

**Merge errors?**

Tänk dig att du har två mappar fyllda med bilder i din dator. I du vill kopiera alla dessa bilder till en mapp. Men vad händer om du har duplicates?
