# Git Intro

När vi använder git add på en fil så kopierar git innehållet i denna fil till index (staging area).

När vi sedan commit denna fil så tar git innehållet i index och sparar detta i sin memory bank som den representerar med ett commit object.

Detta betyder att vi har 3 olika kopior av vår fil.

(Vi kan ha ytterligare en kopia om vi har en remote på t.ex. GitHub)

En i vårt working directory, en i vårt index, och en i vårt commit object.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/492ae093-663d-4921-b40c-78695cbd9395/687f161a-32e7-4fca-845e-d299a2afbda1/Untitled.png)

När vi commitat en fil så kommer git att jämföra kopian i sitt commit object med samma fil i vår index. Den kommer även jämföra vår kopia i index med vår fil i vår working directory.

Ifall vi ändrar filen i vår working directory så kommer denna att markeras som modified men unstaged.

När vi sedan kör git add . så kommer filen att vara staged and modified.

När vi sedan commitar filen så kommer den att vara unmodified, och vi kommer ha en likadan kopia längs working directory, index, och commit object.

Så ändrar vi på filen i vårt working directory så kommer den fortfarande vara tracked, men också modified.

När vi använder git add . så kommer filen vara **staged,** och modified.

När vi commitar kommer den vara unmodified.

Så en added file kommer aldrig bli untracked igen,

### File States

- **Untracked**: Files that are not in the repository and not staged.
- **Tracked**: Files that are in the repository. Tracked files can be:
  - **Unmodified**: No changes have been made since the last commit.
  - **Modified**: Changes have been made, but not staged for commit.
  - **Staged**: Changes have been staged and are ready to be committed.

Varje commit kommer med ett SHA.

Och för varje commit du skapar efter din första, så kommer dessa commits att även ha ett SHA för “parent”. Detta är SHA till commiten som kom innan din nuvarande commit.

Alla dina commits kan alltså länkas ihop som ett träd.

Detta kallas för vår commit history, och är en väsentlig del av hur git fungerar.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/492ae093-663d-4921-b40c-78695cbd9395/cb179c3d-0c7b-4a53-8e2a-bab409d0c239/Untitled.png)

Dessa pointers är unidirectional. Barnen pekar på sina föräldrar, men föräldrarna har inget SHA som pekar på dess barn.

Hur som haver så finns det inget som hindrar en parent ifrån att ha flera olika direkta barn, eller ett barn ha flera föräldrar.

Sammanfattningsvis:

En helt ny fil är untracked - git vet inte om denna.

En fil som vi använder git add på, blir tracked och **kopieras** till vårt Index (staging area) och blir **tracked**.

När vi skapar en ny commit så skapar git en kopia av filen i vår index, och lagrar detta i vårt commit object. Som sparar en metadata kring commiten, samt en pointer till filerna som precis lagrades. Såväl som data kring author, email, commit message.

Varje commit förutom den första, innehåller en pointer genom ett commit id (sha) till sin föräld-er(rar).
