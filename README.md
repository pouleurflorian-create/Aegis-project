# AEGIS — La néobanque éthique

Projet web réalisé dans le cadre du cours CON-2026-EFP.

AEGIS est une landing page pour une néobanque fictive ciblant les créateurs de contenu. L'objectif était de concevoir une interface mobile-first complète avec un design system cohérent, sans framework.

---

## Technologies

- HTML5 sémantique
- CSS3 (BEM, variables, clamp(), flexbox, animations)
- Polices locales (Montserrat, Lato) — aucun appel externe

## Structure

```
AEGIS FINAL/
├── index.html
├── style.css
├── fonts/
└── img/
```

## Parti pris techniques

**Mobile-first** : la base CSS est pensée pour mobile, les media queries élargissent à 768px et 1280px.

**BEM** : toutes les classes suivent la convention bloc__element--modificateur pour éviter les conflits de sélecteurs.

**Design system** : les couleurs, polices, rayons et ombres sont centralisés dans `:root` via des custom properties.

**Glassmorphism** : les cartes utilisent `backdrop-filter: blur()` avec un fond semi-transparent.

**Accessibilité** : `aria-label` sur les éléments interactifs, `focus-visible` stylisé, `prefers-reduced-motion` respecté.

---

Florian Pouleur — 2026
