💡 CONTEXTE
Tu es un intégrateur Front-End senior.  
Tu dois livrer un mini-site statique (GitHub Pages) pour la marque « Cimes & Sens », savonnerie paysanne.

👥 ÉQUIPE
• Intégrateur (moi) — structure, GA4, Stripe.  
• Responsable produits — édite un fichier JSON unique.  
• Designer — fournit logo, polices, palette et retouche le CSS.

📐 CROQUIS & NAVIGATION
— Bandeau haut : logo centré, réseaux sociaux à gauche, compte + panier à droite.  
— Barre de navigation sous le bandeau.  
— Page d’accueil (index.html) : hero + boutique + mini-section “Esprit” + “Où nous trouver”.  
— Autres pages : esprit.html, ingredients.html, mentions.html, cgv.html, confidentialite.html.  
(!) La boutique doit apparaître **directement sur la home**.  
(!) On conserve les autres pages pour le SEO / contenu éditorial.

🔧 EXIGENCES TECHNIQUES
1. **GitHub Pages** : site 100 % statique, pas de build.  
2. **Stripe Payment Links** : URL checkout `https://buy.stripe.com/...` (aucune clé secrète).  
3. **Google Analytics 4** : snippet classique (mettre `TODO`).  
4. **Tailwind 3.x** via CDN + un petit `style.css` (variables design).  
5. **Fichier unique `products.json`** — structure obligatoire :  

```json
[
  {
    "title": "Savon Menthe Poivrée",
    "description": "Un savon rafraîchissant à l'huile de menthe.",
    "ingredients": ["Huile d'olive", "Huile de coco", "Menthe poivrée", "Eau", "Soude"],
    "price": "6.50",
    "currency": "EUR",
    "image": "assets/savon-menthe.jpg",
    "link": "https://buy.stripe.com/test_ABC123",
    "category": "Savons"
  },
  …
]

    JavaScript vanilla :

        index.html lit products.json, génère la grille produits et les filtres catégories.

        ingredients.html lit le même JSON et affiche, pour chaque produit, son titre, sa description et la liste d’ingrédients (image optionnelle).

        Pas de framework, ES 6 natif.

    Responsive : grille 1 col → 2 cols ≥ 640 px → 3 cols ≥ 1024 px.

    Accessibilité : images alt, contraste AA, navigation clavier.

    Bandeau cookies (RGPD) : code commenté prêt à activer (Klaro.js ou CookieConsent).

🎨 DESIGN (modifiable par la designer via style.css)

:root{
  --color-primary:#6b705c;   /* vert sauge */
  --color-secondary:#ffe8d6; /* beige clair */
  --color-accent:#cb997e;    /* terracotta */
  --font-title:'Playfair Display', serif;
  --font-body:'Inter', sans-serif;
}

Tous les titres utilisent --font-title, le reste --font-body.
Boutons : fond --color-primary, texte blanc.

📂 STRUCTURE ATTENDUE

/
├─ index.html            # landing + boutique dynamique
├─ esprit.html           # page éditoriale longue
├─ ingredients.html      # liste ingrédients (dynamique depuis JSON)
├─ mentions.html
├─ cgv.html
├─ confidentialite.html
├─ products.json         # SANS commentaire, conforme au schéma ci-dessus
├─ style.css
└─ assets/
   ├─ logo.svg
   ├─ icônes (insta.svg, facebook.svg, cart.svg)
   ├─ images hero + ferme
   └─ photos produits

🔑 LIVRABLES À GÉNÉRER

    Tous les fichiers HTML mentionnés, avec header/footer cohérents.

    products.json contenant au moins 3 produits répartis sur 2 catégories pour exemple.

    style.css contenant uniquement les variables + petite déco (section-title, bouton nav).

    JavaScript intégré dans index.html et ingredients.html (pas de fichier séparé).

    README.md expliquant :

        comment déployer sur GitHub Pages ;

        comment ajouter un produit / modifier ingrédients ;

        où mettre l’ID GA4 ;

        où remplacer les Payment Links ;

        comment changer couleurs/polices.

✍️ CONSIGNES DE RÉDACTION
– Aucune clé Stripe ou GA réelle : mets TODO.
– Aucun paquet NPM, Tailwind par CDN seulement.
– Images pointent vers assets/… et doivent etre dasn un premier temps des images fausse.
– Utilise seulement du HTML 5, CSS 3 et JS ES 6 (fetch API).

