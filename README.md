# Base de lieux Facileo, part sous ODbL

Ce dépôt ne contient aucun code. Il publie, sous Open Database License (ODbL) v1.0,
la part de la base de lieux de [Facileo](https://facileo.org) qui dérive de
sources placées sous cette licence : OpenStreetMap et le référentiel des gares SNCF,
ainsi que les fiches ayant fusionné avec ces sources.

## Télécharger

Les exports vivent dans les [releases publiques](https://github.com/alastyn256/facileo-data/releases).
La publication suit l'actualisation mensuelle d'OpenStreetMap réussie ; une reprise
ou un export manuel peut produire plusieurs releases dans le même mois. Chaque release contient :

| Fichier | Contenu |
|---|---|
| `facileo-lieux-<date>.ndjson.gz` | les lieux, une ligne JSON par lieu |
| `README.txt` | le détail de chaque champ |
| `ATTRIBUTION.txt` | les sources et leurs licences |
| `LICENSE.txt` | le texte de la licence |
| `SHA256SUMS` | les empreintes, pour vérifier le téléchargement |

Lecture d'un export :

```bash
shasum -a 256 -c SHA256SUMS
gzip -dc facileo-lieux-*.ndjson.gz | jq .
```

Le nom du fichier indique la date de l'extraction Facileo, pas la date de relevé
de chaque producteur. `source_updated_at` renseigne celle de la source lorsqu'elle
est disponible. Consulter le `README.txt` de la release pour les champs et les volumes.

## Ce que ce dépôt contient, et ce qu'il ne contient pas

Facileo réunit plusieurs jeux de données publics, sous des licences
différentes. Deux d'entre elles sont sous ODbL : OpenStreetMap et le
référentiel des gares de SNCF Gares & Connexions. Seules les fiches qui en
dérivent sont publiées ici, parce que ce sont les seules que cette licence
oblige à partager.

Les fiches venues de sources sous Licence Ouverte, qui n'ont rencontré ni l'une
ni l'autre, n'y figurent pas : leur licence ne l'impose pas, et elles restent
disponibles auprès de leurs producteurs.

Les comptes, favoris, messages, photos et signalements des utilisateurs n'y figurent pas.
L'archive contient les fiches publiées et les fiches absorbées par une fusion, avec
leur provenance. Ce n'est donc ni toute la base interne ni uniquement les lieux
visibles sur la carte.

## Pourquoi cet export

Facileo sélectionne, normalise et rapproche les données ouvertes. Ces traitements
produisent une base dérivée, même sans ajouter de relevé manuel. L'offre d'un accès
lisible par machine répond à l'article 4.6 de l'ODbL. GitHub est le moyen
d'hébergement choisi ; la licence n'impose pas cette plateforme.

## Avertissement

Ces données viennent de sources publiques que Facileo réunit ; des erreurs sont
possibles, et un lieu peut avoir changé depuis le dernier passage. Ne les
utilisez pas comme seule garantie d'accessibilité pour une personne.

Le dédoublonnage est prudent par choix : mieux vaut un doublon visible qu'un
lieu accessible disparu. Vous rencontrerez donc des lieux proches qui sont le
même endroit vu par deux sources.

## Licence et attribution

Les données sont sous [ODbL v1.0](https://opendatacommons.org/licenses/odbl/1-0/).
Elles contiennent des données © les contributeurs d'OpenStreetMap et des
données de SNCF Gares & Connexions. La liste complète des sources et de leurs
licences est dans `ATTRIBUTION.txt`, joint à chaque release.

Le code de l'application Facileo n'est pas publié et reste privé.
