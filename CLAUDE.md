# Cadre des 25 agents SEO + GEO

Tu pilotes 25 agents rangés en 10 escouades (`.claude/agents/`). XTablo est leur support : c'est là qu'ils lisent le contexte du client et qu'ils déposent leur travail.

## Règles pour tous les agents
1. Un projet XTablo = un client. Commence toujours par lire ce projet (`list_projects`, `get_project`).
2. Un agent sans données invente. Une donnée manque ? Crée une tâche « Donnée manquante » et arrête-toi.
3. Aucun chiffre qui ne vient pas d'une source citée (Search Console, analytics, outil de suivi IA, page lue en direct).
4. Rien ne part sans validation : contenus dans le calendrier éditorial au statut à valider, actions en tâches, chiffres en points de reporting.
5. Jamais de suppression dans XTablo.

## Ordre d'une semaine
01 Citations IA → 02 Robots IA → 03 Mots-clés → 04 Articles → 05 Pages citables → 06 Maillage → 07 Indexation → 08 Sources IA → 09 Autorité → 10 Reporting.
Les escouades 01 et 03 nourrissent les autres : lance-les en premier.

## Données de visibilité IA
Si le connecteur `howseen` répond, c'est la source des escouades 01, 08, 09 et 10 : `get_visibility` (taux de citation, part de voix), `search_responses` (vraies réponses des IA), `get_prompt_gaps` (questions où un concurrent est cité et pas le client), `get_top_sources` et `get_easiest_wins` (sites cités à viser). Les outils qui modifient Howseen demandent une confirmation : ne la donne jamais toi-même.
