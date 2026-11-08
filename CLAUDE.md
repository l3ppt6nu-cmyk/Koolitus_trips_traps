# Koolitus_trips_traps – Claude Code'i juhend

Claude Code loeb selle faili iga sessiooni alguses. Kasutaja üldjuhendi põhikoopia asub Google Drive'is ja pilvesessioon seda ei loe, seega on selle projekti jaoks olulised põhimõtted kirjas siin. Kui kasutaja otsene juhis on selle failiga vastuolus, järgi kasutaja juhist ja juhi vastuolule tähelepanu.

## Projekt
- Repositoorium: `l3ppt6nu-cmyk/Koolitus_trips_traps`, põhiharu `main`.
- Eesmärk: trips-traps-trulli mäng programmeerimise õppimiseks ja Claude Code'i töövoo katsetamiseks Androidi tahvlis.
- Repositoorium on avalik: ära lisa isikuandmeid, salasõnu, API võtmeid ega muud konfidentsiaalset materjali.

## Projekti seis ja käsud
Kontrolli alati tegelikke faile; ära eelda valmis koodi, raamistikku ega testikäske. Uuenda seda lõiku, kui struktuur või käsud muutuvad.
- Seis 8.11.2026: ainult `README.md` ja see fail. Koodi, teste ega GitHub Actionsi töövooge veel pole.
- Testide käivitamine: puudub (kavas `node --test`).

## Rollid
- Kasutaja kirjeldab eesmärki, vaatab muudatused üle ja ühendab PR-id. Vajadusel muudab ta koodi tahvlis ise (`github.dev` või GitHubi rakendus).
- Claude Code kirjutab koodi ja teste, käivitab kontrollid ja haldab Giti.
- ChatGPT aitab ülesandeid sõnastada ja teeb vajadusel sõltumatu koodikontrolli GitHubis.

## Keel ja suhtlus
- Kõik eesti keeles: vastused, koodikommentaarid, kasutajaliidese tekstid, commit-sõnumid ja PR-ide kirjeldused.
- Muutujate, funktsioonide ja failide nimed inglise keeles.
- Selgita lahendusi algajale arusaadavalt; mitteilmset loogikat kommenteeri lühidalt.
- Kvaliteet, töökindlus ja arusaadavus on tähtsamad kui kiirus.

## Tehniline suund
Vaikimisi valik, kuni kasutaja otsustab teisiti:
- HTML, CSS ja tavaline JavaScript (ES-moodulid) ilma raamistiku ja ehitustööriistadeta, et mäng töötaks otse brauseris.
- Mänguloogika on kasutajaliidesest eraldi moodulis, et seda saaks testida ilma brauserita.
- Testid Node.js-i sisseehitatud testikäivitajaga (`node --test`), mis ei vaja ühtegi npm-paketti.
- Enne uue sõltuvuse, raamistiku või ehitustööriista lisamist küsi kasutajalt ja põhjenda vajadust ühe lausega.

## Töökorraldus
- Alusta iga ülesannet Giti seisu kontrollist: aktiivne haru, `git status`, viimased commit'id ja `git fetch`, et näha kaugharu muudatusi.
- Väikese ja selge muudatuse tee kohe. Suure või riskantse muudatuse puhul esita enne lühike plaan ja oota kinnitust.
- Tööta sessiooni tööharus või kasutaja nimetatud harus. Ära push'i `main`-harusse ega ühenda PR-e – seda teeb kasutaja.
- Kui kasutaja palub erandkorras töötada otse `main`-harus, küsi luba enne iga commit'i.
- Üks commit = üks loogiline muudatus; sõnum eesti keeles, nt „Lisa võidu tuvastamine“.
- Kui töö on valmis ja kontrollitud, loo PR `main`-harusse, kui kasutaja pole palunud teisiti.
- Kasutaja võib samal harul ise muudatusi teha. Kui kaugharus on uusi commit'e, too need enne oma muudatusi sisse; konflikti korral peatu ja küsi juhiseid.
- Ära kirjuta üle kasutaja pooleliolevat tööd. Ära tee hävitavaid Giti toiminguid (nt force-push, `git reset --hard`) ega kustuta harusid. Faile kustuta ainult siis, kui ülesanne seda nõuab, ja nimeta need aruandes.

## Kvaliteet
- Veendu, et muudatus töötab: käivita olemasolevad testid. Kui teste pole, lisa muudatusega proportsionaalsed testid või kirjelda, kuidas kontrollisid.
- Mänguloogika puhul testi vähemalt: käiguvahetus, hõivatud ruut, võit (read, veerud, diagonaalid), viik, käik pärast mängu lõppu ja uus mäng – kui need funktsioonid on olemas.
- Veebivaate puhul kontrolli võimaluse korral paigutust ja kasutatavust puuteekraanil: Androidi tahvel (rõht- ja püstpaigutus) ning kitsas mobiilivaade. Ära väida visuaalset kontrolli tehtuks, kui seda ei tehtud.
- Ära lahenda testitõrkeid teste välja lülitades ega nõrgendades.

## Lõpparuanne
Lõpus anna lühike eestikeelne ülevaade:
- mis tehti ja millised failid muutusid;
- mida testiti (käsk ja tulemus) ning mis jäi kontrollimata;
- haru nimi, commit'i räsi ja PR-i link, kui need tekkisid;
- suurema muudatuse korral või kasutaja palvel üks lõik ülesande eesmärgist, tehtud muudatustest ja teadaolevatest riskidest, mille kasutaja saab ChatGPT-le ülevaatuseks edasi anda.

## Turvapiirangud
- Ära tee pärismakseid, tootmiskeskkonda juurutamist ega pöördumatuid andmemuudatusi.
- Ära loe ega jaga `.env` faile ega muid saladusi; näidisfail võib sisaldada ainult näidisväärtusi.
- Need on tööjuhised, mitte tehniliselt jõustatud õigused. Kasutaja vaatab muudatused enne `main`-harusse ühendamist GitHubis üle.

## Pilvesessiooni tehnilised märkused
- Node.js 22 on pilvekeskkonnas olemas; `node --test` töötab ilma paigalduseta.
- GitHubi päringud käivad puhverserveri kaudu: `gh pr` ja `gh issue` (GraphQL) ei tööta. Kasuta sisseehitatud GitHubi tööriistu või REST-päringuid kujul `gh api repos/l3ppt6nu-cmyk/Koolitus_trips_traps/...`.
- Puhverserver ei takista tehniliselt `main`-harusse push'imist – ülaltoodud harureegel kehtib sellest hoolimata.
