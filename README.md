# Cimes & Sens - Savonnerie Paysanne

Un  mini-site statique pour la marque « Cimes & Sens », savonnerie paysanne, optimisé pour GitHub Pages.

## 🚀 Déploiement sur GitHub Pages

1. **Activer GitHub Pages** :
   - Aller dans les paramètres du repository GitHub
   - Section "Pages" → Source : "Deploy from a branch"
   - Branch : `main` → Folder : `/ (root)`
   - Sauvegarder

2. **Publier les modifications** :
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```

3. **Accès au site** :
   - URL : `https://le-cmyk.github.io/Cimes-Sens/`
   - Délai de propagation : 2-10 minutes après chaque push

## 📂 Structure du Projet

```
/
├─ index.html            # Page d'accueil + boutique dynamique
├─ esprit.html           # Page éditoriale "Notre esprit"
├─ ingredients.html      # Liste des ingrédients (dynamique)
├─ a-propos.html         # À propos, mentions légales et CGV simplifiées
├─ products.json         # Base de données produits (sans commentaires)
├─ style.css             # Variables CSS personnalisables
└─ assets/
   ├─ logo.svg          # Logo de la marque
   ├─ icones/           # Icônes réseaux sociaux et interface
   ├─ images/           # Images hero et photos de la ferme
   └─ produits/         # Photos des savons et produits
```

## 🛒 Gestion des Produits

### Ajouter un nouveau produit

Éditer le fichier `products.json` et ajouter un objet avec cette structure :

```json
{
  "title": "Nom du Produit",
  "description": "Description courte du produit",
  "ingredients": ["Ingrédient 1", "Ingrédient 2", "..."],
  "price": "Prix",
  "currency": "EUR",
  "image": "assets/produits/nom-produit.jpg",
  "link": "https://buy.stripe.com/YOUR_PAYMENT_LINK",
  "category": "Catégorie"
}
```

### Modifier les ingrédients

1. Ouvrir `products.json`
2. Localiser le produit à modifier
3. Modifier la liste `"ingredients": [...]`
4. Sauvegarder et pousser les modifications

### Ajouter une nouvelle catégorie

Les catégories sont automatiquement générées à partir du champ `"category"` de chaque produit.

## 💳 Configuration Stripe

1. **Créer les Payment Links** dans votre tableau de bord Stripe
2. **Remplacer les URLs** dans `products.json` :
   - Remplacer `https://buy.stripe.com/test_ABC123` par vos vrais liens
3. **Mode Test vs Production** :
   - Test : `https://buy.stripe.com/test_...`
   - Production : `https://buy.stripe.com/...`

## 📊 Configuration Google Analytics 4

1. **Obtenir votre ID GA4** (format : `G-XXXXXXXXXX`)
2. **Remplacer dans tous les fichiers HTML** :
   ```html
   <!-- Remplacer TODO_GA4_ID par votre ID -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=TODO_GA4_ID"></script>
   ```
3. **Également remplacer** dans le script :
   ```javascript
   gtag('config', 'TODO_GA4_ID');
   ```

## 🎨 Personnalisation du Design

### Modifier les couleurs et polices

Éditer le fichier `style.css` et modifier les variables CSS :

```css
:root {
  --color-primary: #6b705c;    /* Vert sauge principal */
  --color-secondary: #ffe8d6;  /* Beige clair */
  --color-accent: #cb997e;     /* Terracotta */
  --font-title: 'Playfair Display', serif;  /* Police des titres */
  --font-body: 'Inter', sans-serif;         /* Police du texte */
}
```

### Ajouter des styles personnalisés

Le fichier `style.css` contient uniquement les variables et quelques styles de base. Vous pouvez y ajouter vos propres règles CSS.

## 🖼️ Gestion des Images

### Structure recommandée
```
assets/
├─ logo.svg              # Logo principal
├─ icones/
│  ├─ instagram.svg      # Icône Instagram
│  ├─ facebook.svg       # Icône Facebook
│  └─ cart.svg           # Icône panier
├─ images/
│  ├─ hero-bg.jpg        # Image de fond de la section hero
│  └─ ferme.jpg          # Photo de la ferme
└─ produits/
   ├─ savon-menthe.jpg   # Photos des produits
   └─ savon-lavande.jpg
```

### Optimisation des images
- **Format recommandé** : JPG pour les photos, SVG pour les icônes
- **Taille recommandée** : 800x600px pour les produits, 1920x1080px pour le hero
- **Compression** : Optimiser pour le web (qualité 80-85%)

## 🔒 RGPD & Cookies

Le bandeau cookies est inclus mais désactivé par défaut. Pour l'activer :

1. **Décommenter le code** dans la section `<!-- RGPD Cookie Banner -->` de chaque page HTML
2. **Configurer** selon vos besoins de tracking
3. **Tester** le consentement et la collecte de données

## 🛠️ Technologies Utilisées

- **HTML5** : Structure sémantique
- **CSS3** : Variables CSS + Tailwind 3.x via CDN
- **JavaScript ES6** : Fetch API, DOM natif
- **Stripe Payment Links** : Paiements sécurisés
- **Google Analytics 4** : Suivi et analytics

## 📱 Responsive Design

- **Mobile-first** : optimisé pour mobiles d'abord
- **Breakpoints** :
  - < 640px : 1 colonne
  - ≥ 640px : 2 colonnes
  - ≥ 1024px : 3 colonnes

## ♿ Accessibilité

- **Contraste AA** respecté
- **Navigation au clavier** fonctionnelle
- **Attributs alt** sur toutes les images
- **Structure sémantique** HTML5

## 🚨 Points d'Attention

1. **Pas de clés secrètes** dans le code (tout est côté client)
2. **Images** : vérifier que tous les chemins existent
3. **URLs Stripe** : tester en mode test avant la production
4. **GA4** : remplacer tous les `TODO_GA4_ID`
5. **Performance** : optimiser les images avant upload

## 🆘 Support

Pour toute question technique :
1. Vérifier la console du navigateur (F12)
2. Valider le JSON avec un validateur en ligne
3. Tester les Payment Links individuellement
4. Vérifier la configuration GitHub Pages

---

**Développé pour Cimes & Sens** - Savonnerie Paysanne  
🌿 *Produits naturels, savoir-faire artisanal*
