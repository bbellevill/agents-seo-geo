# 25 agents SEO + GEO pour Claude Code

25 agents Claude Code, rangés en 10 escouades, qui font le SEO et le GEO (visibilité dans ChatGPT, Perplexity, Gemini et Google AI Overviews) de tes clients.

Ils travaillent dans **XTablo** : chaque client est un projet. Les agents y lisent le contexte du client et y déposent leur travail : articles au calendrier éditorial, actions en tâches, chiffres au reporting. Tu valides, ton client valide dans son portail. Les posts LinkedIn et Instagram partent seuls depuis le calendrier ; les articles et corrections du site arrivent prêts à coller.

## Installation (10 min)

1. **Le dépôt.** Clone-le, ou ouvre-le dans Claude Code sur le web (claude.ai/code) pour qu'il tourne dans le cloud.
   ```
   git clone https://github.com/bbellevill/agents-seo-geo
   ```
2. **La clé XTablo.** Dans XTablo : Paramètres > Clés d'API, crée une clé avec les droits lecture + écriture + messages. Pas de compte ? [xtablo.com](https://www.xtablo.com).
   ```
   export XTABLO_API_KEY=ta_cle
   export HOWSEEN_API_KEY=ta_cle   # suivi des réponses des IA, voir plus bas
   ```
3. **Un projet par client.** Dans XTablo, crée le projet du client et écris dans sa description : secteur, offre, site, 3 concurrents, ce qu'on a le droit de dire.
4. **Lance.**
   ```
   claude
   /geo-semaine Nom du client
   ```
   Au premier lancement, accepte le serveur « xtablo ». Pour une seule escouade : `/escouade 04 Nom du client`.

Pour que ça tourne seul chaque lundi : dans Claude Code, `/schedule` puis « chaque lundi 8h, /geo-semaine Nom du client ».

## Les données à brancher

| Donnée | Pour quelles escouades | Comment |
|---|---|---|
| Suivi de visibilité IA (réponses de ChatGPT, Perplexity, Gemini, AI Overviews) | 01, 07, 08, 09, 10 | Déjà branché : Howseen. Mets la clé d.API de ton compte Howseen : `export HOWSEEN_API_KEY=ta_cle`. Autre outil de suivi ? Ajoute son connecteur MCP dans `.mcp.json`. |
| Search Console | 01, 03, 07 | Export des requêtes, ou connecteur Search Console |
| Analytics du site | 10 | Export des sources de trafic (référents IA) |
| Le site lui-même | 02, 04, 05, 06, 07 | Lu en direct par les agents, rien à brancher |

Sans suivi IA, les escouades 01, 08 et 10 s'arrêtent sur une tâche « Donnée manquante » : elles ne peuvent pas deviner ce que répond ChatGPT.

## Les 10 escouades

### 01 · Citations IA
- **Audit de citations** : Savoir qui ressort dans les réponses des IA sur 20 questions du marché du client.
- **Part de voix IA** : Mesurer la part du client face à ses 3 concurrents dans les réponses des IA.
- **Suivi de prompts** : Tenir la liste des 50 questions qu'un acheteur pose avant d'acheter chez le client.

### 02 · Robots IA
- **Accès des robots IA** : Vérifier que GPTBot, ClaudeBot, PerplexityBot et Google-Extended peuvent lire le site.
- **Fichier llms.txt** : Donner aux modèles la carte du site : les pages qui comptent, en une phrase chacune.
- **Rendu sans JavaScript** : Voir ce qu'un robot lit vraiment : parfois une page vide.

### 03 · Mots-clés
- **Trous de contenu** : Montrer ce que les concurrents couvrent et que le client ne couvre pas.
- **Vraies questions** : Trouver les questions que les gens posent vraiment, pas celles qu'on imagine.

### 04 · Articles
- **Découpe en passages** : Découper chaque page en passages autonomes : un titre par vraie question.
- **Réponses citables** : Écrire, pour chaque question, une réponse de 40 à 60 mots qu'une IA peut reprendre telle quelle.

### 05 · Pages citables
- **Données structurées** : Poser un JSON-LD relié aux entités du client (Organization, Product, Article, FAQ).
- **Entités et sameAs** : Faire en sorte que le client soit le même partout : nom, description, liens.
- **Preuves** : Ajouter un chiffre ou une source à chaque affirmation importante.

### 06 · Maillage
- **Liens internes** : Relier chaque page aux pages proches, dans les deux sens.

### 07 · Indexation
- **AI Overviews** : Trouver les requêtes où Google répond sans clic, et y entrer.
- **Fraîcheur** : Garder les pages datées et à jour : une page oubliée passe derrière.

### 08 · Sources IA
- **Comparatifs et annuaires** : Entrer dans les listes « meilleurs outils » et les annuaires que les IA lisent.
- **Reddit** : Trouver les fils cités par les IA, et la réponse utile à y laisser.
- **Sources citées** : Lister les pages que les IA reprennent déjà sur le sujet du client.

### 09 · Autorité
- **Concurrent cité** : Trouver le passage exact qui vaut sa citation au concurrent.
- **Digital PR** : Faire parler du client avec une donnée que lui seul possède.
- **E-E-A-T** : Signer les pages : auteur, expérience, preuves de sérieux.
- **Fiche Google** : En local, l'IA répond souvent avec la fiche Google : la rendre complète.

### 10 · Reporting
- **Reporting GEO** : Dire chaque mois au client sur combien de questions il est cité.
- **Trafic IA** : Compter les visites venues de ChatGPT, Perplexity, Gemini et Copilot.

## La règle qui compte

Un agent sans données invente, et il invente surtout ta place dans les réponses des IA.
Chaque agent dit donc de quelles données il a besoin (Search Console, analytics, outil de suivi IA, pages lues en direct). S'il en manque une, il crée une tâche « Donnée manquante » dans XTablo et s'arrête.

Rien n'est publié sans toi : les contenus arrivent au statut « à valider ».

---
Fait par [XTablo](https://www.xtablo.com), le portail client des agences.
