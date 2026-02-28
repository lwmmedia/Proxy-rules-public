# Guide de Contribution

Merci de votre intérêt pour **Proxy Rules Public** ! Ce document explique comment contribuer efficacement au projet.

## Avant de Commencer

- Vérifiez les [Issues existantes](https://github.com/lwmmedia/Proxy-rules-public/issues) pour éviter les doublons.
- Pour les grandes modifications, ouvrez d'abord une Issue afin d'en discuter.
- Assurez-vous d'avoir lu le [Code de Conduite](CODE_OF_CONDUCT.md).

## Types de Contributions

### Ajouter un nouveau fichier de règles

1. **Fork** le dépôt et créez une branche depuis `main` :
   ```bash
   git checkout -b ajout/nom-du-service
   ```

2. **Créez** votre fichier dans la catégorie appropriée :
   - `rules/streaming/` — Services vidéo/audio (YouTube, Netflix, Twitch…)
   - `rules/social/` — Réseaux sociaux et messagerie (Telegram, Discord…)
   - `rules/global/` — Services tech internationaux (Google, Apple, Microsoft…)

3. **Nommez** le fichier en minuscules : `nomduservice.list`

4. **Respectez** le format standard :
   ```ini
   # Nom du Service — description courte
   # Domaines principaux
   DOMAIN-SUFFIX,exemple.com
   DOMAIN-SUFFIX,api.exemple.com
   # CDN et ressources statiques
   DOMAIN-SUFFIX,cdn.exemple.com
   # IP ranges si nécessaire
   IP-CIDR,1.2.3.0/24,no-resolve
   ```

5. **Testez** vos règles dans une application proxy (Loon, Shadowrocket ou Stash) avant de soumettre.

6. **Mettez à jour** le `README.md` : ajoutez votre service dans le tableau correspondant.

7. **Soumettez** une Pull Request avec :
   - Un titre clair : `feat: ajouter les règles pour [Service]`
   - Une description indiquant les domaines couverts et comment vous avez testé

### Corriger des règles existantes

- Signalez d'abord via une Issue avec le label `bug`.
- Fournissez le domaine manquant ou incorrect et la preuve de son appartenance au service.
- Les PR de correction doivent inclure un message de commit explicite : `fix: ajouter domaine CDN manquant pour Netflix`.

### Améliorer la documentation

- Corrections de fautes, clarifications, traductions : directement en PR.
- Restructuration importante : ouvrez une Issue en premier.

## Standards de Qualité des Règles

| Critère | Attendu |
|---|---|
| **Domaines officiels** | Uniquement des domaines légitimes du service |
| **Couverture** | Inclure les domaines principaux, API, CDN et médias |
| **Tests** | Vérifiés dans au moins une application proxy |
| **Commentaires** | Expliquer les domaines non évidents |
| **Format** | Syntaxe cohérente, une règle par ligne |

## Convention de Messages de Commit

```
type: description courte en français

# Types acceptés :
feat:   ajout d'un nouveau fichier de règles ou d'une fonctionnalité
fix:    correction d'un domaine manquant ou incorrect
docs:   modification de la documentation uniquement
chore:  maintenance, mise à jour des dépendances
```

## Signaler un Problème

Utilisez les [Issues GitHub](https://github.com/lwmmedia/Proxy-rules-public/issues) en précisant :

- **Service concerné** et nom du fichier `.list`
- **Application proxy** utilisée (Loon, Shadowrocket, Stash) et sa version
- **Comportement observé** vs **comportement attendu**
- **Domaine(s) problématique(s)** si identifiés

## Questions ?

Ouvrez une Issue avec le label `question`. Nous faisons de notre mieux pour répondre rapidement.
