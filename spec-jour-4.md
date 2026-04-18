# 📘 Spécifications – Calculatrice hypothécaire

## 1. Contexte général

Cette interface représente une **calculatrice hypothécaire** destinée aux consommateurs canadiens.  
Elle permet de calculer les versements hypothécaires, de simuler des remboursements anticipés et d’estimer l’impact sur l’amortissement et les intérêts.

---

## 2. Objectifs fonctionnels

- Calculer les **versements hypothécaires réguliers**
- Simuler l’impact de **remboursements anticipés**
- Estimer la **durée d’amortissement** et les **économies d’intérêts**
- Offrir une **expérience utilisateur simple et claire**

---

## 3. Périmètre fonctionnel

### Inclus
- Saisie des paramètres du prêt hypothécaire
- Calcul des versements réguliers
- Simulation de remboursements anticipés
- Déclenchement du calcul via une action utilisateur

### Exclus
- Authentification utilisateur
- Sauvegarde ou export de scénarios
- Impression ou génération de PDF
- Personnalisation avancée des règles bancaires

---

## 4. Description fonctionnelle de l’interface

### 4.1 En-tête

- **Titre** : Calculatrice hypothécaire  
- **Sous-titre** : Agence de la consommation en matière financière du Canada  
- **Description** :  
  - Explique que la calculatrice détermine les versements hypothécaires
  - Mentionne les économies possibles grâce aux remboursements anticipés
  - Lien vers un outil d’évaluation d’admissibilité à un prêt hypothécaire

---

### 4.2 Bandeau informatif

- Message invitant l’utilisateur à répondre à un court sondage
- Objectif : amélioration continue de l’outil
- Lien de partage de commentaires

---

## 5. Formulaire – Versement régulier

### Champs fonctionnels

- **Montant du prêt hypothécaire**
  - Type : Numérique (devise $)
  - Valeur par défaut visible : 100 000 $
  - Règle : valeur strictement positive

- **Taux d’intérêt**
  - Type : Numérique (%)
  - Valeur par défaut visible : 5,00 %
  - Règle : valeur ≥ 0

- **Période d’amortissement**
  - Type : Liste déroulante
  - Exemple visible : 25 années
  - Règle : valeurs prédéfinies

- **Fréquence des versements**
  - Type : Liste déroulante
  - Exemple visible : Mensuels (12x par année)

- **Terme**
  - Type : Liste déroulante
  - Exemple visible : 5 années
  - Règle : doit être ≤ période d’amortissement

---

## 6. Formulaire – Remboursement anticipé

### Champs fonctionnels

- **Montant des remboursements anticipés**
  - Type : Numérique (devise $)
  - Valeur par défaut visible : 0,00 $
  - Règle : valeur ≥ 0

- **Fréquence**
  - Type : Liste déroulante
  - Exemple visible : Une seule fois

- **À partir du versement**
  - Type : Numérique entier
  - Valeur par défaut visible : 1
  - Règle : valeur ≥ 1

---

## 7. Action utilisateur

### Bouton « Calculer »

- Déclenche :
  - La validation des champs
  - Le calcul des versements hypothécaires
  - Le calcul de l’impact des remboursements anticipés
- Les résultats sont affichés dans une section non visible sur l’image

---

## 8. Règles fonctionnelles

- Les calculs supposent :
  - Un taux d’intérêt fixe
  - Une fréquence de versement constante
- Les remboursements anticipés :
  - Réduisent le capital restant
  - Diminuent les intérêts totaux payés
- En absence de remboursement anticipé :
  - Le scénario correspond à un prêt hypothécaire standard

---

## 9. Spécifications techniques

### 9.1 Hypothèses techniques

- Application web (HTML / CSS / JavaScript ou framework moderne)
- Calculs réalisés :
  - Côté client ou
  - Via un service backend exposé par API

---

### 9.2 Modèle de données (exemple)

```ts
interface HypothequeInput {
  montantPret: number;
  tauxInteretAnnuel: number;
  amortissementAnnees: number;
  frequenceVersement: 'mensuel' | 'bimensuel' | 'hebdomadaire';
  termeAnnees: number;
  remboursementAnticipe?: {
    montant: number;
    frequence: 'unique' | 'annuel' | 'mensuel';
    debutVersement: number;
  };
}
``