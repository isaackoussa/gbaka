# GBAKA — Suivi de Caisse (synchronisé entre appareils)

Suivi des recettes journalières et dépenses d'entretien de ton gbaka, avec tes données de juin/juillet déjà importées depuis ton fichier Excel d'origine.

**Nouveau** : les données sont maintenant synchronisées entre tous tes appareils (téléphone, ordinateur...) — une modification faite sur l'un apparaît sur les autres dès que tu rouvres l'app ou reviens dessus.

⚠️ Ceci nécessite une fonction serveur — il faut déployer via GitHub connecté à Netlify (pas de simple glisser-déposer).

## Comment ça marche

- **Saisie du mois** : une fiche par jour avec la vraie date, pour noter la recette journalière ; une liste de dépenses (vidange, assurance, pneu, etc., + "Autre" pour écrire librement ce que tu veux)
- **Caisse** : montant total dans la caisse (cumul de tous les mois) et solde du mois en cours, clairement séparés, + graphique des recettes sur 12 mois
- **Historique** : généré automatiquement à partir de tes saisies
- **Entretien** : total par catégorie de dépense, calculé automatiquement

## Déploiement

```bash
git init
git add .
git commit -m "Premier envoi"
git branch -M main
git remote add origin https://github.com/TON-COMPTE/gbaka-suivi-caisse.git
git push -u origin main
```

Puis sur https://app.netlify.com : **Add new project → Import an existing project → GitHub** → choisis le dépôt.

## Variables d'environnement à ajouter

Dans **Project configuration → Environment variables** :

| Nom | Valeur |
|---|---|
| `NETLIFY_SITE_ID` | Project ID de ton site (Project details) |
| `NETLIFY_AUTH_TOKEN` | Ton jeton d'accès personnel (User settings → Applications → Personal access tokens) |

Puis **Deploys → Trigger deploy → Deploy site**.

## Note sur la synchronisation

Les données se rafraîchissent automatiquement à chaque fois que tu reviens sur l'onglet/l'app (par exemple en revenant d'une autre appli sur ton téléphone). Si tu modifies en même temps sur deux appareils exactement au même moment, la dernière sauvegarde écrase l'autre — évite de saisir simultanément sur deux appareils à la fois.
