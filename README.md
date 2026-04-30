<div align="center">

# AEGIS

**La néobanque éthique & transparente pour les créateurs de contenu**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![No Framework](https://img.shields.io/badge/No%20Framework-Vanilla-blueviolet?style=flat-square)
![Mobile First](https://img.shields.io/badge/Mobile-First-0f0c2e?style=flat-square)
![Accessible](https://img.shields.io/badge/Accessibility-WCAG%202.1-green?style=flat-square)

</div>

---

## Aperçu

AEGIS est une **landing page** pour une néobanque fictive ciblant les talents du digital — streamers, créateurs de contenu et indépendants. L'interface est conçue sans framework, de zéro, avec un design system maison, une architecture CSS modulaire et une attention particulière portée à l'accessibilité.

> Projet réalisé dans le cadre du cours **CON-2026-EFP**.

---

## Fonctionnalités

| Fonctionnalité | Détail |
|---|---|
| **Responsive** | Mobile-first · breakpoints 768 px et 1280 px |
| **Design system** | Custom properties CSS centralisées (`colors`, `layout`, `decoration`) |
| **Glassmorphism** | `backdrop-filter: blur()` avec fallback gracieux |
| **Animations** | `fade-up`, `float`, `pulse-glow` — coupées si `prefers-reduced-motion` |
| **Typographie locale** | Montserrat & Lato chargées depuis `assets/fonts/` — aucun appel réseau |
| **Accessibilité** | ARIA complet · `focus-visible` stylisé · rôles sémantiques |
| **BEM** | Convention `bloc__element--modificateur` sur toutes les classes |

---

## Stack technique

- **HTML5** sémantique — balises de structure (`header`, `main`, `footer`, `nav`, `section`)
- **CSS3 pur** — variables, `clamp()`, flexbox, `@keyframes`, `@import`
- **Polices locales** — aucune dépendance CDN, 0 requête externe
- **SVG inline** — illustration neon optimisée directement dans le markup

---

## Structure du projet

```
AEGIS FINAL/
│
├── index.html                  # Point d'entrée unique
│
├── style.css                   # Composants & layout (@import styles/)
│
├── styles/                     # Design tokens — jamais liés directement au HTML
│   ├── all_variables.css       # Point d'entrée des tokens (importe les 3 fichiers)
│   ├── colors.css              # Palette & couleurs sémantiques
│   ├── layout.css              # Espacements, rayons, z-index
│   └── decoration.css          # Ombres, gradients, transitions
│
└── assets/
    ├── img/
    │   └── hero-bg.png         # Fond hero (WebP recommandé en prod)
    └── fonts/
        ├── Montserrat-Bold.ttf
        ├── Montserrat-SemiBold.ttf
        ├── Montserrat-Regular.ttf
        ├── Lato-Black.ttf
        ├── Lato-Bold.ttf
        ├── Lato-Light.ttf
        └── Lato-Regular.ttf
```

---

## Lancer le projet

Aucune installation requise. Le projet tourne directement dans le navigateur.

```bash
# Cloner le dépôt
git clone https://github.com/<user>/aegis-landing.git
cd aegis-landing

# Ouvrir avec VS Code + Live Server, ou simplement :
open index.html
```

> Pour un rendu optimal, utiliser **Live Server** (VS Code) ou tout serveur local — certains navigateurs bloquent `backdrop-filter` sur `file://`.

---

## Partis pris techniques

### Architecture CSS en couches

Les styles sont organisés en deux niveaux distincts :

1. **`styles/`** — design tokens uniquement (variables `:root`). Ces fichiers ne contiennent aucune règle de mise en page. Ils sont importés via `@import` dans `style.css`, **jamais liés directement au HTML**, ce qui garantit qu'un seul point d'entrée CSS est déclaré.

2. **`style.css`** — composants, layout et media queries. Ce fichier est le seul `<link>` dans le `<head>`.

### Mobile-first

La base CSS cible les écrans < 768 px. Les breakpoints élargissent progressivement :

```css
/* Base → mobile */
/* @media (min-width: 768px)  → tablette / desktop */
/* @media (min-width: 1280px) → grand écran */
```

### `clamp()` plutôt que des breakpoints pour les tailles

La majorité des valeurs de police, padding et espacement utilisent `clamp(min, préféré, max)` pour un scaling fluide sans media query supplémentaire.

---

## Accessibilité

- `aria-label` sur tous les éléments interactifs sans texte visible (burger, icônes sociales)
- `aria-expanded` / `aria-controls` sur le menu burger
- `role` explicites (`banner`, `contentinfo`, `list`, `listitem`)
- Styles `:focus-visible` sur chaque élément focusable
- `prefers-reduced-motion` : toutes les animations sont neutralisées
- HTML sémantique complet — pas de `<div>` superflu là où une balise native suffit

---

## Auteur

**Flow** — [pouleurflorian@gmail.com](mailto:pouleurflorian@gmail.com)

---

<div align="center">
<sub>Projet académique · CON-2026-EFP · Pas de licence commerciale</sub>
</div>
