
---

## 🎨 Vue d’ensemble : qu’est‑ce que fait ce code ?
Ce code construit **un Homer Simpson entièrement en CSS**, sans images, uniquement via :

- des `<div>` positionnés en **absolute**
- des formes créées avec `border-radius`
- des ombres internes (`box-shadow`)
- des transformations (`transform: rotate()`)
- des animations CSS pour les paupières (clignement)

C’est un exemple classique de **CSS art**, très détaillé et très manuel.

---

## 🧱 Structure HTML
Le HTML est minimaliste :

- Un conteneur `#homer`
- Une `div.head` qui contient :
  - cheveux
  - crâne
  - yeux + pupilles + paupières animées
  - nez
  - bouche (8 couches différentes)
  - oreilles
  - cou

Chaque élément du visage est une `<div>` avec une classe dédiée.

Ce style de structure est typique du **CSS art pré‑Flexbox/GRID**, où chaque élément est une brique positionnée pixel par pixel.

---

## 🎨 Structure CSS : comment l’art est construit ?

### 1. Positionnement absolu global
```css
#homer * {
    position: absolute;
    box-sizing: content-box;
}
```
Cela signifie :

- chaque élément est positionné **relativement à `#homer`**
- aucun flux normal : tout est placé manuellement
- `content-box` est utilisé pour éviter que les bordures n’affectent les dimensions

### 2. Le conteneur principal
```css
#homer {
    position: relative;
    width: 94px;
    height: 133px;
}
```
C’est la “toile” sur laquelle tout est dessiné.

### 3. Les formes
Le code utilise intensivement :

- `border-radius` pour créer des ovales
- `box-shadow` pour simuler des volumes
- `transform: rotate()` pour orienter les éléments
- `background` pour les couleurs

Exemple : les cheveux sont des demi‑cercles inclinés.

### 4. Les animations (clignement)
Les paupières utilisent une animation très simple :

```css
@keyframes homerlefteyelidtop {
  0% { top: -21px; }
  2% { top: 0px; }
  4% { top: -21px; }
  100% { top: -21px; }
}
```

C’est un clignement rapide toutes les 10 secondes.

---

## 💡 Points forts du code
- **CSS pur**, aucune image → très léger
- **Animations subtiles** → donne de la vie au personnage
- **Détails impressionnants** (oreille, ombres internes, bouche en plusieurs couches)
- **Compatibilité large** grâce aux préfixes `-webkit-` et `-moz-`

---

## ⚠️ Limites et problèmes
### 1. Code très verbeux et difficile à maintenir
Chaque élément est positionné au pixel près. Modifier la taille ou l’échelle est presque impossible.

### 2. Utilisation massive de `position: absolute`
Cela empêche toute adaptabilité ou responsivité.

### 3. Préfixes obsolètes
Les préfixes `-moz-` et `-webkit-` ne sont plus nécessaires pour :

- `border-radius`
- `transform`
- `box-shadow`

### 4. Pas de séparation claire des responsabilités
Tout est dans un seul fichier CSS, sans variables, sans structure moderne.

### 5. Pas d’accessibilité
Aucun `alt`, aucun rôle, aucun texte → normal pour du CSS art, mais à noter.

---


