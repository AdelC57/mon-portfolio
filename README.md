# Portfolio Adel - Vue.js

Portfolio personnel développé avec Vue.js, présentant mon profil de développeur web et mes projets.

## 📋 Prérequis

Pour installer et exécuter ce projet, vous aurez besoin de :

- Node.js (version 14.0 ou supérieure)
- npm ou yarn
- Un navigateur web moderne

## 🚀 Installation

1. Clonez le repository :
```bash
git clone https://github.com/votre-username/portfolio-vue
cd portfolio-vue
```

2. Installez les dépendances :
```bash
npm install
# ou avec yarn
yarn install
```

## 💻 Lancement

### Pour le développement
```bash
npm run dev
# ou
yarn dev
```
Le site sera accessible sur `http://localhost:5173`

### Pour la production
```bash
npm run build
# ou
yarn build
```

## 🛠️ Technologies Utilisées

- **Vue.js 3** - Framework JavaScript progressif
- **Vue Router** - Routage officiel pour Vue.js
- **HTML5** et **CSS3** (Flexbox)
- **JavaScript ES6+**
- **Vite** - Outil de build moderne

## 📁 Structure du Projet

```
portfolio-vue/
├── src/
│   ├── assets/
│   │   ├── img/         # Images et ressources
│   │   └── icons/       # Icônes
│   ├── components/      # Composants Vue réutilisables
│   ├── views/          # Pages/Vues principales
│   ├── router/         # Configuration du routage
│   ├── App.vue         # Composant racine
│   └── main.js         # Point d'entrée de l'application
├── public/             # Ressources statiques
├── docs/
│   └── validation/     # Captures d'écran validations W3C
├── index.html
├── package.json
└── README.md
```

## ✨ Fonctionnalités

- **Design Responsive** : Compatible avec tous les appareils
- **Navigation Intuitive** : Menu avec ancres fluides
- **Présentation** : Section "À propos" détaillée
- **Projets** : Showcase des réalisations avec modals détaillés
- **Contact** : Formulaire de contact fonctionnel
- **SEO** : Meta tags optimisés pour le référencement
- **Page 404** : Page d'erreur personnalisée

## 🌐 Validation W3C

Les captures d'écran de validation W3C sont disponibles dans le dossier `docs/validation/` :
- HTML : `docs/validation/html-validation.png`
- CSS : `docs/validation/css-validation.png`

## 🔧 Configuration

Si vous souhaitez configurer l'envoi d'emails du formulaire de contact :

1. Créez un fichier `.env` à la racine du projet
2. Ajoutez votre configuration :
```env
VITE_EMAIL_RECIPIENT=votre@email.com
```

## 📝 Note

Ce portfolio a été développé dans le cadre d'une formation au développement web. Il respecte les standards du web et les bonnes pratiques de développement front-end.