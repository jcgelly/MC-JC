# Instructions Copilot - Site Mariage MC & JC

## Vue d'ensemble
Site web statique de mariage en français pour Marie-Charline & Jean-Christophe (30 mai 2026, Château de Belvoir).
Single-page HTML avec Tailwind CSS via CDN - pas de build system.

## Stack technique
- **HTML/CSS/JS** : Fichier unique `index.html`, pas de framework
- **Tailwind CSS** : Chargé via CDN avec configuration inline dans `<script>tailwind.config</script>`
- **Fonts** : Cormorant Garamond (titres, serif) + Lato (corps, sans-serif) via Google Fonts
- **Icônes** : Font Awesome 6.4

## Palette de couleurs (définie dans tailwind.config)
| Nom | Hex | Usage |
|-----|-----|-------|
| `sage` | #8A9A5B | Couleur principale, accents |
| `sage-light` | #E3E8E1 | Fonds clairs |
| `blush` | #E8CDC9 | Rose poudré, accents secondaires |
| `paper` | #FDFBF7 | Fond principal (texture papier) |
| `charcoal` | #4A4A4A | Texte principal |
| `gold` | #C5A059 | Touches dorées discrètes |

## Conventions de style
- **Titres** : `font-serif italic` (ex: `class="font-serif text-4xl text-charcoal italic"`)
- **Labels** : Majuscules avec letter-spacing (ex: `class="uppercase tracking-widest text-sm font-bold"`)
- **Boutons/liens** : Bordures fines, transition sur hover vers `sage`
- **Images décoratives** : Classe `watercolor-border` pour effet organique

## Structure des sections
Chaque section suit ce pattern :
```html
<section id="nom-section" class="py-20 bg-[couleur-fond]">
  <div class="max-w-6xl mx-auto px-4">
    <div class="text-center mb-16">
      <span class="text-sage uppercase tracking-widest text-sm font-bold">Sous-titre</span>
      <h2 class="font-serif text-4xl md:text-5xl text-charcoal italic mt-2">Titre</h2>
    </div>
    <!-- Contenu -->
  </div>
</section>
```

## Images
- Photos du couple : racine du projet (ex: `_DSF8826.jpg`)
- Autres images : dossier `images/`
- Toujours inclure un `alt` descriptif en français
- **Dimensions recommandées** :
  - Hero/fond : max 1920×1080px
  - Galerie/vignettes : max 800×600px
  - Icônes/décor : max 200×200px
- **Format** : JPEG pour photos, PNG pour transparence, WebP recommandé
- **Poids** : viser < 200KB par image (compresser avec TinyPNG ou Squoosh)

## Mobile
- Navigation responsive avec menu hamburger (bouton `#mobile-menu-btn`)
- Classes responsive : `md:` breakpoint pour desktop
- Pattern courant : `class="hidden md:block"` / `class="md:hidden"`

## Langue et ton
- Tout le contenu est en **français**
- Style romantique et littéraire ("Chapitre Premier", guillemets français « »)
- Vouvoyer les invités implicitement

## Tester les modifications
Ouvrir `index.html` directement dans un navigateur - aucun serveur requis.

## Déploiement (GitHub Pages)
- Repository GitHub lié au projet
- Déploiement automatique via GitHub Pages depuis la branche `main`
- URL du site : configurée dans les settings du repo
- Commit & push pour publier les modifications

## Fonctionnalités planifiées
### Galerie photos (implémentée)
- 4 carrousels auto-rotatifs (toutes les 4s) organisés par thème
- Sous-répertoires : `images/Vie_couple/`, `images/Cartier/`, `images/Palais_Royal/`, `images/Tolkien/`
- Lightbox avec navigation clavier (← → Escape)
- Pause au survol, points de navigation cliquables

### Animation pétales de rose (Hero)
- Animation CSS/JS au chargement du header
- Pétales tombant du haut de l'écran
- **Palette** : roses pastel (`#F8D7DA`, `#FADBD8`, `#F5B7B1`, `blush`)
- Effet léger et romantique, ne doit pas gêner la lecture
- Désactiver sur mobile pour performance (`prefers-reduced-motion`)
