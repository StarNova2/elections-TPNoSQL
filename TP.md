# TP ELECTIONS

## Créer un env. de travail

- créer un dossier `elections`
- installer venv
- installer dépendances (pandas, matplotlib....)
- sauver le requirements
- créer un `docker-compose.yaml`
    <https://school.atontour.info/code/NEO4JJ>
    (pensez à renommer le container en `neo4j_elections` et éventuellement user et password)
- github/git (mettre venv en `.gitignore`)
- `git commit -m "First commit`
- partager avec `rcarlier`

## Récupérer les données

- Elections municipales 2026 - Listes candidates au premier tour
  <https://www.data.gouv.fr/datasets/elections-municipales-2026-listes-candidates-au-premier-tour>
  (renomer le fichier en `candidats-2026.csv`)
- Communes de france - Base des codes postaux
  <https://www.data.gouv.fr/datasets/communes-de-france-base-des-codes-postaux>
  `departements-france.csv`, `regions-france.csv`
  `20230823-communes-departement-region.csv` à renommer en `communes.csv`
- Data INSEE sur les communes
  <https://www.data.gouv.fr/datasets/data-insee-sur-les-communes>
  (MDB-INSEE-V2.xls à convertir en `insee_communes.csv` via tableur/pandas)
- mettre les csv dans un dossier data, **l'exclure du git**

## Analyse et ETL (pandas)

- connaitre la structure, quels sont les problèmes
  - lister dans le chat les problèmes possibles
  - code commune pas au même format "01000" -> 1000
  - code département pas au même format "01" -> 1 -> "1"
  - séparateur , ;
  - nom des champs, de jointure
  - utf8
- `extract-transform.py`
  - unifier les codes : soit 2 chars (département/région), code commune sur 5 chars
  - il faut filtrer `candidats-2026.csv` pour ne garder que les têtes de liste
  - il faut filtrer les jeux `candidats-2026.csv`, `communes.csv` et `insee_communes.csv` pour ne garder que VOTRE département
  - à sauver dans `clean/`
