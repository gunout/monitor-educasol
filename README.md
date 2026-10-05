<div align="center">

# Monitor Programmes — Éducation Nationale

**Tableau de bord d'analyse des programmes d'enseignement français**

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/fr/docs/Web/JavaScript)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

[![Made in France](https://img.shields.io/badge/Made%20in-France-000091?style=for-the-badge)](https://www.education.gouv.fr)
[![Éducation Nationale](https://img.shields.io/badge/Éducation-Nationale-E1000F?style=for-the-badge)](https://www.education.gouv.fr)
[![Open Data](https://img.shields.io/badge/Open%20Data-data.education.gouv.fr-16a34a?style=for-the-badge)](https://data.education.gouv.fr)

[![Version](https://img.shields.io/badge/version-1.0.0-blue?style=flat-square)](https://github.com/)
[![Statut](https://img.shields.io/badge/statut-stable-brightgreen?style=flat-square)](https://github.com/)
[![Zéro dépendance](https://img.shields.io/badge/dépendances-0-success?style=flat-square)](https://github.com/)

**Analysez, filtrez et visualisez les programmes officiels de l'Éducation nationale dans un dashboard tout-en-un.**

</div>

---

## Présentation

**Monitor Programmes** est un tableau de bord web autonome (un seul fichier HTML) permettant d'explorer, filtrer et analyser les programmes d'enseignement officiels publiés par le Ministère de l'Éducation nationale.

Il consomme un fichier `programmes.json` structuré, extrait des données ouvertes du Bulletin officiel et de la plateforme data.education.gouv.fr, et offre une visualisation complète : liste filtrable, matrice croisée, graphiques, évolution temporelle et rapport de qualité.

Cas d'usage : recherche pédagogique, veille curriculaire, comparaison de programmes, préparation de concours (CAPES, Agrégation), documentation pour formateurs et inspecteurs.

---

## Fonctionnalités

| | Fonctionnalité | Description |
|---|---|---|
| 📋 | Liste filtrable | 100+ programmes avec recherche plein texte, tri par année/niveau/discipline |
| 📂 | Vue Disciplines | Cartes synthétiques par matière |
| 🔲 | Matrice Niveaux x Disciplines | Tableau croisé avec intensité colorée |
| 📊 | Analyses graphiques | Diagramme circulaire + 4 graphiques à barres |
| 📈 | Évolution temporelle | Courbe des entrées en vigueur + variations annuelles |
| 🔍 | Rapport qualité | Taux de complétude des 6 champs clés |
| 📥 | Export CSV / JSON | Export des résultats filtrés |
| 🌙 | Thème clair/sombre | Persistance via localStorage |
| 🇫🇷 | Charte de l'État | Bandeau tricolore, Marianne |
| 📱 | Responsive | Adapté mobile et tablette |
| ⚡ | Zéro dépendance | Aucun framework, fonctionne hors ligne |

---

## Installation

Prérequis : un navigateur moderne (Firefox, Chrome, Edge, Safari). Aucune installation logicielle.

Étape 1 : cloner le projet

    git clone https://github.com/votre-utilisateur/monitor-programmes.git

Étape 2 : entrer dans le dossier

    cd monitor-programmes

Étape 3 : vérifier les fichiers présents

    monitor-programmes.html
    programmes.json
    README.md

Étape 4 : ouvrir le dashboard

    firefox monitor-programmes.html

---

## Utilisation

Chargement des données

1. Ouvrez `monitor-programmes.html` dans votre navigateur.
2. Glissez-déposez `programmes.json` dans la zone prévue à gauche.
3. Le dashboard s'initialise : KPI, liste des niveaux, top disciplines.

Filtres disponibles

| Filtre | Emplacement | Comportement |
|---|---|---|
| Recherche texte | Barre supérieure | Filtre sur descriptif, texte officiel, discipline, niveau, voie |
| Années | Barre de filtres | Clic = unique, Ctrl/Cmd + clic = multi |
| Voie | Select déroulant | Générale / Technologique / Professionnelle |
| Niveaux | Sidebar gauche | Clic = unique, Ctrl/Cmd + clic = multi |
| Tri | Select supérieur | Année, Niveau, Discipline |

Raccourcis clavier

| Touche | Action |
|---|---|
| / | Focus sur la recherche |
| Ctrl ou Cmd + clic | Multi-sélection |
| Échap | Fermer les modales |

---

## Vues du dashboard

1. Programmes — Liste paginée avec badges colorés (niveau, discipline, voie, statut). Chaque carte affiche le descriptif, le texte officiel et les liens Légifrance / PDF.

2. Disciplines — Vue par cartes, triée par nombre de programmes.

3. Matrice Niveaux x Disciplines — Tableau croisé avec intensité bleue proportionnelle au nombre de programmes.

4. Analyses — Diagramme circulaire + 4 graphiques à barres (niveaux, voies, années, statut).

5. Évolution — Courbe d'entrée en vigueur par année avec variations annuelles.

6. Qualité — Taux de complétude des 6 champs clés avec code couleur.

---

## Structure du projet

    monitor-programmes/
        monitor-programmes.html     Dashboard tout-en-un
        programmes.json             Données source (100 programmes)
        convert.py                  Optionnel : conversion texte vers JSON
        README.md                   Ce fichier

Structure d'un enregistrement programmes.json

    {
      "voie": "Technologique",
      "descriptif": "Programme de l'enseignement de philosophie",
      "texte_officiel": "arrêté du 19-7-2019 - J.O. du 23-7-2019",
      "niveau_d_enseignement": "Terminale STL",
      "abroge_a_la_rentree": "-",
      "contenu_sur_le_site": "https://cache.media.education.gouv.fr/",
      "entre_en_vigueur_a_la_rentree": "2020",
      "discipline": "Philosophie",
      "lien_vers_le_texte_officiel": "http://www.legifrance.gouv.fr/"
    }

---

## Sources de données

| Source | URL | Description |
|---|---|---|
| data.education.gouv.fr | https://data.education.gouv.fr | Programmes du second degré |
| Bulletin officiel | https://www.education.gouv.fr/bo | Textes réglementaires |
| Légifrance | https://www.legifrance.gouv.fr | Textes consolidés |
| Éduscol | https://eduscol.education.gouv.fr | Ressources pédagogiques |

Régénérer programmes.json via l'API :

    curl -s "https://data.education.gouv.fr/api/records/1.0/search/?dataset=fr-en-programmes-enseignement-2nd-degre&rows=100" | jq '[.records[].fields]' > programmes.json

---

## Charte graphique

| Couleur | Code | Usage |
|---|---|---|
| Bleu Marianne | #000091 | Éléments principaux |
| Rouge Marianne | #E1000F | Alertes, abrogations |
| Or | #fbbf24 | Disciplines |
| Vert | #16a34a | Statut en vigueur |

Typographie : Marianne (fallback system-ui).

---

## Technologies

- HTML5 sémantique
- CSS3 : variables, grid, flexbox, animations
- JavaScript ES6+ vanilla
- FileReader API, LocalStorage, SVG

---

## Roadmap

- [x] V1.0 — 6 vues, filtres, exports, thème
- [ ] V1.1 — Cycles 1 et 2 (maternelle, CP, CE1, CE2)
- [ ] V1.2 — Vue Abrogés dédiée
- [ ] V1.3 — Comparaison de deux disciplines
- [ ] V2.0 — Support multi-fichiers

---

## Contribution

Créer une branche :

    git checkout -b feature/ma-fonctionnalite

Commit :

    git commit -m "feat: ajout de ma fonctionnalité"

Push :

    git push origin feature/ma-fonctionnalite

Conventions de commit

| Préfixe | Usage |
|---|---|
| feat: | Nouvelle fonctionnalité |
| fix: | Correction de bug |
| docs: | Documentation |
| style: | Formatage |
| refactor: | Refactorisation |
| data: | Mise à jour de programmes.json |

---

## Licence

Distribué sous licence MIT. Voir LICENSE.

Les données proviennent de sources publiques officielles et sont réutilisables sous Licence Ouverte 2.0.

---

## Auteur

**Gleaphe**
- La Réunion (974)

---

<div align="center">

**Liberté · Égalité · Fraternité**

*Fait avec soin pour la communauté éducative*

</div>
