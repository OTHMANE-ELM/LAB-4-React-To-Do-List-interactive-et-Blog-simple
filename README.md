# ⚛️ TP 4 – Projet de synthèse React



## 🎯 Objectifs communs

- Créer et organiser des **composants fonctionnels** réutilisables
- Gérer l'état global avec **`useState`**
- Réagir aux **événements utilisateurs** (clic, saisie, soumission)
- Mettre en place la **navigation** avec React Router
- Intégrer des **styles CSS** et des ressources externes

---

# ✅ Partie A – To-Do List interactive

## 📁 Structure des composants

```
src/
├── App.js             → State global + logique principale
├── Formulaire.js      → Champ de saisie + bouton d'ajout
├── ListeTaches.js     → Affichage des tâches avec map()
└── Tache.js           → Un élément avec bouton supprimer
```

## 📋 Résumé des étapes

| Étape | Sujet | Ce qu'on fait |
|-------|-------|---------------|
| 3A | Structure | Identifier les composants et leur hiérarchie |
| 4A | Formulaire | Champ contrôlé par `useState`, soumission et réinitialisation |
| 5A | Liste | Génération dynamique des tâches avec `map()` et `key` unique |
| 6A | Élément | Affichage du titre + bouton suppression via props |
| 7A | State global | Centraliser ajout et suppression dans `App.js` |

## 🔑 Concepts essentiels

**Formulaire contrôlé** — Le champ texte est lié à un état `useState`. À chaque frappe, l'état se met à jour. À la soumission, la tâche est ajoutée et le champ se vide automatiquement.

**Lifting state up** — Toute la logique (liste, ajout, suppression) vit dans `App.js`. Les composants enfants reçoivent les données et les fonctions via les props. C'est le pattern fondamental de React.

**Suppression par filtre** — Supprimer une tâche revient à recréer le tableau sans l'élément ciblé, grâce à `filter()`. Aucun tableau n'est modifié directement.

## ⚠️ Pièges à éviter

- Modifier le tableau de tâches directement avec `push()` → React ne détecte pas le changement, utiliser `[...taches, nouvelle]`
- Oublier la prop `key` dans `map()` → avertissement en console
- Gérer le state dans les composants enfants au lieu de `App.js` → perte de synchronisation

## 🧪 Exercices complémentaires

| # | Exercice | Notion travaillée |
|---|----------|-------------------|
| 1 | Marquer une tâche comme complétée (case à cocher) | `useState`, rendu conditionnel |
| 2 | Filtrer les tâches par statut (toutes / actives / terminées) | `filter()`, état |
| 3 | Compter les tâches restantes | `length`, affichage dynamique |
| 4 | Empêcher l'ajout d'une tâche vide | Validation avant soumission |

## 🎬 Vidéo de démonstration – To-Do List

https://github.com/user-attachments/assets/cc335871-4623-4dec-b5ea-703cfe93c4a5

# 📝 Partie B – Blog simple

## 📁 Structure des composants

```
src/
├── App.js               → Routeur principal + navigation
├── Accueil.js           → Page d'accueil avec introduction
├── ListeArticles.js     → Grille de tous les articles
├── DetailArticle.js     → Page de lecture d'un article
└── Contact.js           → Page de contact
```

## 📋 Résumé des étapes

| Étape | Sujet | Ce qu'on fait |
|-------|-------|---------------|
| 3B | Structure | Organiser les dossiers et identifier les pages |
| 4B | Liste articles | Afficher les articles en cartes cliquables avec `map()` |
| 5B | Détail article | Récupérer l'`id` dans l'URL avec `useParams()` |
| 6B | Pages principales | Accueil, Blog, Contact — chacune associée à une route |
| 7B | Navigation | `<NavLink>` pour mettre en évidence la page active |

## 🔑 Concepts essentiels

**Données statiques** — Les articles sont stockés dans un tableau d'objets (id, titre, résumé, contenu). Ce tableau sert de "base de données" locale au projet.

**`useParams()`** — Hook de React Router qui lit les paramètres dynamiques dans l'URL. Par exemple `/article/2` permet de récupérer l'`id` 2 et d'afficher l'article correspondant.

**`<NavLink>`** — Variante de `<Link>` qui applique automatiquement une classe CSS sur le lien de la page actuellement active, utile pour styliser la navigation.

## ⚠️ Pièges à éviter

- Oublier de déclarer la route dynamique `/article/:id` → la page de détail ne s'affiche pas
- Utiliser `<a href>` au lieu de `<Link>` → rechargement complet de la page
- Ne pas trouver l'article via `find()` → penser à gérer le cas où l'id n'existe pas

## 🧪 Exercices complémentaires

| # | Exercice | Notion travaillée |
|---|----------|-------------------|
| 1 | Ajouter une page "À propos" | Nouvelle route + lien nav |
| 2 | Afficher la date de publication de chaque article | Données enrichies |
| 3 | Trier les articles du plus récent au plus ancien | `sort()` |
| 4 | Ajouter un bouton "Retour à la liste" sur le détail | Navigation programmatique `useNavigate()` |

## 🎬 Vidéo de démonstration – Blog simple

https://github.com/user-attachments/assets/deb4d66d-74b5-42f5-b7a1-b66379ca0f13

*TP réalisé dans le cadre du cours de développement web – React*
