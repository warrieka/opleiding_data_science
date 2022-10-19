LES 2
======

Basis GIT 

## Waarom
- Je eigen code georganiseerd bewaren met mogelijkheid om veranderingen ongedaan te maken.
- Samenwerken met anderen aan dezelfde codebase.
- Uitvoeren van code reviews in een project
- Issue tracking bij een project

## git configuren
- Download and install: https://git-scm.com/downloads

- Globale instelligen wijzingen --> global is overal, default
- Open *Powershell* :
```sh
git config --global user.name "Kay Warrie"
git config --global user.email kaywarrie@gmail.com 
```

- Settings enkel voor 1 repo, project 
```sh
git config user.name "Kay Warrie"
git config user.email kaywarrie@gmail.com 
```
- Settings oplijsten
```sh
git config --list
```
of alle globals
```sh
git config --list --global
```

## nieuwe git repo initialiseren 
- Maak nieuwe folder `repo`
- Hierin nieuwe code-file aanmaken
- Open *Powershell* 
- Type: 

```sh
cd # LOCATIE REPO #
git init 
```

- Huidige wijzingen zien:
  - rood: nog niet ge-add
  - groen: ge-add maar nog niet gecommit
```sh
git status
```

## Een commmit maken 
- eerst bewerkingen toevoegen *staging* 
- dan commit met duidelijke *message*
```sh
git add . 
git commit -m "commit boodschap"
```

- Commit taggen
  - Geen spacies in tags 
  - grote tag: belangrijk milestone `-l` en `-m` voor extra info bij tag
    ```sh
    git tag -l v1.0.0 -m "Versie 1, klaar voor release"
    ```
  - kleine tag, groeperen commits, extra info, ... om makkelijk commits te zoeken
    ```sh
    git tag klaar_met_deel_1
    ```

## Koppelen in github 
- Surf naar: https://github.com/
- -> Account aanmaken of inloggen
- -> *[New](https://github.com/new)* of via plusje rechts -> *Create a new repository* 
- Naam `repo` 
- Type (eenmalig): 
```sh
git branch -M main
git remote add origin https://github.com/warrieka/repo.git
```

- wijzigingen publiceren naar GITHUB (altijd na commit)
```sh
git push origin main
```

## Bestaande repo binnenhalen
- `git clone` repo url
- voorbeeld
```sh
git clone https://github.com/warrieka/tw-openlayers-viewer
```

## Forken en branchen
- Fork = permanent je eigen versie maken
- Branch = tijdlijke versie die terug zal samenvoegen met main branch
  - Vooral als met meerdere samenwerkt: ieder eigen versie
  - `branch` -> nieuwe branch
  - `checkout` -> start met werken in bepaald branch
  - `merge` -> brzch samenvoegen met *main*
```sh
git branch nieuwe_werk_branch
git checkout nieuwe_werk_branch
# werken #
git add . 
git commit -m "boodschap"
git checkout main
git merge nieuwe_werk_branch 
```
