
# 🎓 Pôle Informatique EFREI — Site Web

> Projet académique — EFREI Paris · 2025  
> Stack : **HTML5 · CSS3 · Tailwind CSS · JavaScript**

Site web multi-pages responsive présentant le Pôle Informatique de l'EFREI Paris, avec chatbot intégré à reconnaissance d'intentions.



---

## Pages

| Page | Description |
|------|-------------|
| `accueil.html` | Hero section, piliers du pôle, call-to-action |
| `presentation.html` | Présentation générale de l'école |
| `enseignement.html` | Formations et cursus disponibles |
| `projets.html` | Projets étudiants et R&D |
| `vieetudiante.html` | Vie associative et événements campus |
| `contact.html` | Formulaire et coordonnées |
| `apropos.html` | L'équipe derrière le projet |

---

## Fonctionnalités

### Navigation responsive
- Header sticky avec effet glassmorphism
- Menu mobile avec toggle JavaScript
- Liens actifs mis en évidence par page

### Chatbot (🤖 Assistant Pôle Info)
Chatbot injecté dynamiquement en JavaScript, disponible sur toutes les pages :
- Interface bulle flottante (ouvrir/fermer)
- Indicateur de frappe animé (...)
- **Reconnaissance d'intentions par mots-clés** à partir d'un fichier `intents.json`
- Réponse aux questions sur les admissions, formations et vie étudiante

```javascript
// Algorithme de matching par mots-clés
function findResponse(input, data) {
    const lowerInput = input.toLowerCase();
    for (const intent of data.intents) {
        for (const keyword of intent.keywords) {
            if (lowerInput.includes(keyword)) return intent.response;
        }
    }
    return data.default;
}
```

### Design
- Palette couleurs EFREI (bleu institutionnel `#003366`)
- Police **Inter** (Google Fonts)
- Cartes avec effet zoom au survol
- Dégradés et overlays sur les sections hero

---

## Stack technique

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

---

## Lancer le projet

Aucune dépendance à installer — Tailwind est chargé via CDN.

```bash
git clone https://github.com/Eliott-agy/efrei-pole-info.git
cd efrei-pole-info
# Ouvrir accueil.html dans un navigateur
```

> ⚠️ Le chatbot utilise `fetch('intents.json')` — ouvrir via un serveur local (ex: Live Server sur VS Code) pour éviter les erreurs CORS.

---

## Structure du repo

```
efrei-pole-info/
├── accueil.html
├── presentation.html
├── enseignement.html
├── projets.html
├── vieetudiante.html
├── contact.html
├── apropos.html
├── styles.css
├── script.js
├── intents.json          # Base de connaissances du chatbot
└── img/
    ├── logoefrei.png
    ├── accueil_fond.jpg
    ├── enseignement.jpg
    └── ...
```
