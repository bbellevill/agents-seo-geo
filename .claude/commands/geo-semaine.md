---
description: Lance les 10 escouades sur un client, dans l'ordre
argument-hint: <nom du projet client dans XTablo>
---
Client : $ARGUMENTS

1. Trouve le projet « $ARGUMENTS » dans XTablo. S'il n'existe pas, arrête-toi et dis-le.
2. Lance les escouades dans l'ordre de CLAUDE.md, avec les agents de `.claude/agents/`. Les agents d'une même escouade tournent en parallèle.
3. Termine par l'agent reporting-geo.
4. Rends en 5 lignes : ce qui a été déposé dans XTablo (tâches, entrées du calendrier, points de reporting) et les données manquantes.
