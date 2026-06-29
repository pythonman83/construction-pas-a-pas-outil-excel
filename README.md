# Pas à pas — Construire l'Outil de Diagnostic TSSR en PowerShell 5.1

> Guide pédagogique interactif, **phase par phase**, 
  pour construire un outil de diagnostic Windows en **PowerShell 5.1**.
> Conçu pour les stagiaires **TSSR grands débutants**, sans aucun prérequis.

**Centre de formation MODE 83 — Draguignan (Var, France)**
TSSR · DWWM · Médiateur numérique

---

## 📖 Présentation

Cette page est un **guide de construction progressive** : 
le stagiaire écrit un **unique script PowerShell** 
(`outil-diagnostic-pc-24-options.ps1`) qui grandit étape après étape. 
À chaque phase, on **ajoute** un morceau de code, on **lance** le script et on **vérifie immédiatement** le résultat dans la console — puis, à partir de la phase 8, sur le Bureau avec un export Excel.

Le principe directeur, répété tout au long du guide :

> **On n'efface jamais ce qui marche déjà : on ajoute, on relance, on vérifie.**

L'ensemble tient dans **un seul fichier HTML autonome**, 
sans aucune étape de build, prêt à être ouvert dans un navigateur ou hébergé tel quel.

---

## ✨ Caractéristiques principales

- **10 phases progressives** (00 → 09), chacune suivant le même rythme rassurant : objectif → notions → code à recopier → on lance → ce que vous devez voir.
- **24 diagnostics système** Windows 10/11 natifs collectés par le script final.
- **1 export Excel premium** généré nativement au format `.xlsx` (OpenXML, UTF-8 sans BOM) déposé sur le Bureau.
- **Bonus de compilation** : transformer le script en exécutable `.exe` avec `ps2exe`.
- **Thème clair / sombre** « Obsidienne & Or » avec bascule mémorisée.
- **Boutons « Copier »** sur chaque bloc de code.
- **Sommaire latéral** qui surligne automatiquement la phase en cours de lecture.
- **Bouton retour haut de page** premium animé, avec sons générés en Web Audio.
- **Date/heure** et **météo** en temps réel dans l'en-tête.
- **Accessibilité soignée** (WCAG) : police basse vision, contrastes, navigation clavier, mouvement réduit.

---

## 🧭 Le guide en 10 phases

| N° | Phase | Notion clé abordée |
|----|-------|--------------------|
| 00 | Préparer le terrain | Ouvrir PowerShell, autoriser les scripts, créer et lancer un `.ps1` |
| 01 | Les couleurs du thème | La **variable** |
| 02 | Les fonctions d'affichage | La **fonction** |
| 03 | Première vraie information système | Objets système, date/heure en français |
| 04 | Les tableaux : disque et processus | Le **pipeline** `\|` |
| 05 | Le menu interactif | Boucle et lecture de saisie |
| 06 | Tous les autres diagnostics | Les 24 collecteurs de données |
| 07 | Reprise & message de remerciement | Structure du programme, fonctions de fin |
| 08 | L'export Excel premium… sur le Bureau | `.xlsx` natif, UTF-8 sans BOM, moteur `Export-ExcelPremium`, 24 collecteurs |
| 09 | Bonus : compiler l'outil en `.exe` | `ps2exe` |

---

## 🛠️ Stack technique

| Élément | Détail |
|---------|--------|
| **Langage cible (pédagogie)** | PowerShell 5.1 (Windows 10/11 natif) |
| **Page** | HTML5 statique, fichier unique, zéro build |
| **CSS** | Système de design maison + [Bootstrap 5.3](https://getbootstrap.com/) (CDN) |
| **Polices** | Playfair Display (titres), Atkinson Hyperlegible (corps, basse vision), JetBrains Mono (code) — via Google Fonts |
| **JavaScript** | Vanilla (aucune dépendance), `IntersectionObserver`, Web Audio API |
| **APIs externes** | [OpenWeatherMap](https://openweathermap.org/) (météo) + [ipapi.co](https://ipapi.co/) (géolocalisation de repli) |
| **Persistance** | `localStorage` (préférence de thème, clé `guide-theme`) |

---

## 🎨 Système de design « Obsidienne & Or »

Toutes les couleurs sont pilotées par des **variables CSS** déclinées en deux thèmes, ce qui garantit une lisibilité homogène dans les deux modes :

- **Thème sombre (obsidienne)** : fond `#0D0D0D`, or clair `#E3C04B`.
- **Thème clair (parchemin doré)** : fond `#F4EFDF`, or assombri `#8A6D0F` (contraste AA sur blanc).

La bascule clair/sombre est accessible depuis l'en-tête et le choix est mémorisé entre les visites.

---

## ♿ Accessibilité

La page vise un bon niveau de conformité **WCAG** :

- **Lien d'évitement** clavier vers le contenu principal.
- **Focus visible** sur tous les éléments interactifs (liens, boutons, `summary`).
- **Police de corps Atkinson Hyperlegible**, conçue pour la basse vision, taille ≥ `1.05rem`.
- **Attributs ARIA** sur les régions, le minuteur date/heure et la météo.
- Respect de **`prefers-reduced-motion`** : animations désactivées pour les utilisateurs concernés.
- **Barre de défilement** thématisée et lisible en clair comme en sombre (navigateurs WebKit/Blink).

---

## 🌐 Compatibilité navigateurs

Optimisée pour les navigateurs récents. 
Certaines finitions visuelles sont spécifiques à **Google Chrome / Edge / Opera** 
(moteur WebKit/Blink) :

- la **barre de défilement** personnalisée (pseudo-éléments `::-webkit-scrollbar`) ;
- les sons du **bouton retour haut** reposent sur la Web Audio API (disponible sur tous les navigateurs modernes) et ne se déclenchent qu'après une interaction de l'utilisateur.

---

## 🚀 Installation & utilisation

Aucune installation, aucune compilation :

1. Récupérez le dossier du projet (voir structure ci-dessous).
2. Ouvrez **`index.html`** dans un navigateur, **ou** déposez les fichiers 
sur n'importe quel hébergement statique.

> 💡 La date/heure et la météo nécessitent une **connexion Internet** 
(Google Fonts, Bootstrap CDN, API météo). 
Le guide reste entièrement lisible hors ligne, sans ces fonctionnalités annexes.

---

## 📁 Structure suggérée des fichiers

```
.
├── index.html                       # La page du guide (fichier unique et autonome)
├── README.md                        # Ce fichier
└── images/
    ├── favicon-32x32.png
    ├── favicon-192x192.png
    ├── favicon-500x500.webp         # Badge affiché à droite des textes du héros
    └── apple-touch-icon.png
```

---

## ⚙️ Personnalisation

- **Couleurs / thème** : modifiez les variables CSS sous `:root[data-theme="dark"]` et `:root[data-theme="light"]` dans le bloc `<style>`.
- **Polices** : remplacez les variables `--font-titre`, `--font-corps`, `--font-code`.
- **Contenu des phases** : chaque phase est une `<section class="phase" id="phase-N">` indépendante, facile à éditer ou à dupliquer.
- **Métadonnées / SEO** : pensez à remplacer les URLs `https://www.ton-site.fr/...` (balises `canonical`, Open Graph, Twitter) par votre domaine réel.

### 🔐 Clé API météo — à sécuriser

La météo utilise une **clé OpenWeatherMap codée en dur** côté client, 
donc **publiquement visible** dans le code source. 
Avant toute mise en ligne, il est recommandé de :

- remplacer la clé par la vôtre ;
- la **restreindre** (quotas, domaines autorisés) depuis votre compte OpenWeatherMap ;
- ou de router l'appel via un petit proxy serveur si la clé doit rester confidentielle.

---

## 👤 Auteur & crédits

- **Auteur** : Jean-Claude Lugo
- **Structure** : MODE 83 — Centre de formation numérique, Draguignan (Var)
- **Public visé** : stagiaires TSSR grands débutants

---

## 📄 Licence

Aucune licence n'est précisée dans la page. Ajoutez ici la licence de votre choix
(par exemple [MIT](https://opensource.org/licenses/MIT) pour un usage libre, ou une mention
« Tous droits réservés » si le support reste interne à MODE 83).
