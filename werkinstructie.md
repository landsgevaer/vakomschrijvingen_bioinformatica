# Werkinstructie voor bio-informatica docenten 

Het volgende beschrijft de manier van werken door BFV docenten om dit gitbook up-to-date te houden, gebruikmakend van git.

### Prerequisites

- Een github account
- Een lokale _git_ installatie

### Eerste keer gebruik

- Fork de repository https://github.com/MichielNoback/vakomschrijvingen_bioinformatica
- Clone hem lokaal op je computer `git clone https://github.com/<YourUserName>/vakomschrijvingen_bioinformatica.git`
- Breng wijzigingen aan in je lokale kopie
- Doe een Add `git add ...`, een Commit `git commit -m <een goede omschrijving van wijzigingen>` en een Push `git push origin master`
- Op je github fork (**Github website!**): Stuur een pull request naar de originele repo. Zie voor hulp: [https://help.github.com/articles/creating-a-pull-request-from-a-fork/](https://help.github.com/articles/creating-a-pull-request-from-a-fork/)

### Latere updates  

- Voordat je start: sync met de "Master" repo; 
    - Definieer een tweede remote, als je die nog niet hebt; zie [https://help.github.com/articles/configuring-a-remote-for-a-fork/](https://help.github.com/articles/configuring-a-remote-for-a-fork/) (`origin` is dan je eigen repo op github en `upstream` de Master repo die de coordinator van het curriculum beheert)
    - Sync die met je eigen locale repo: “git pull upstream master” of heel netjes volgens [https://help.github.com/articles/syncing-a-fork/](https://help.github.com/articles/syncing-a-fork/)
- Breng je nieuwe wijzigingen aan, add, commit en push gevolgd door een pull request (zie "Eerste keer gebruik")

### Publiceren als Gitbook op Github Pages (door ADMIN)  
Dit maakt gebruik van node/npm en node plugins gulp en yarn.  

Zie deze link [https://gldraphael.com/blog/publishing-gitbook-to-github-pages/](https://gldraphael.com/blog/publishing-gitbook-to-github-pages/)
voor een uitgebreide instructie.

Dus, na elke bewerking dienen de volgende stappen/commando's te worden uitgevoerd:

- git add + git commit + git push ("gewone" repo)
- gitbook build OF gitbook serve ("build" boek)
- gulp publish (commit html en resources naar branch hg-pages)

**NB**: update to node 10 caused errors that were solved using these actions:  

- Solution is delete node_modules dir and package-lock.json.
- Then run sudo npm install --unsafe-perm=true