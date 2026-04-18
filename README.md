# 🏠 Calculatrice hypothécaire Canada

Application web statique permettant de simuler un prêt hypothécaire et d’estimer l’impact des remboursements anticipés sur la durée d’amortissement et le coût total des intérêts.

## ✨ Fonctionnalités

- Calcul des versements hypothécaires réguliers
- Paramétrage du prêt (montant, taux, amortissement, terme, fréquence)
- Simulation de remboursements anticipés
- Estimation des économies d’intérêts
- Interface claire et moderne en français

## 🧰 Stack technique

- HTML5
- CSS3
- JavaScript (vanilla)
- Déploiement automatique via GitHub Pages (GitHub Actions)

## 🚀 Démarrer en local

### Option 1 — Ouvrir directement

1. Cloner le dépôt
2. Ouvrir `index.html` dans votre navigateur

### Option 2 — Serveur local (recommandé)

Avec VS Code, utilisez **Live Server** ou tout serveur HTTP local pour éviter les limitations liées au protocole `file://`.

## 🌐 Déploiement GitHub Pages

Le projet est déployé automatiquement à chaque push sur la branche `main` grâce au workflow :

- `.github/workflows/deploy-pages.yml`

URL du site (si GitHub Pages est activé dans le repo) :

- https://moupiidrice.github.io/calcul_hypothecaire_canada/

## 📁 Structure du projet

- `index.html` — interface utilisateur et logique de calcul
- `spec-jour-4.md` — spécifications fonctionnelles
- `.github/workflows/deploy-pages.yml` — pipeline CI/CD GitHub Pages

## 📌 Roadmap (idées d’amélioration)

- Ajout d’une validation de formulaire plus avancée
- Ajout de graphiques d’amortissement
- Export des résultats (CSV / PDF)
- Internationalisation (FR/EN)

## 👤 Auteur

Projet réalisé dans le cadre d’un exercice Bootcamp IA / GitHub Copilot.
