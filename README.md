# Maison Soleil — Hotel Booking Confirmation Page

Solution du challenge Frontend Mentor **"Hotel booking confirmation page"**.

Page de confirmation de réservation pour un hôtel fictif (Maison Soleil, Cassis), affichant le reçu de séjour, une welcome card du reçu de l'hôte, et les infos pratiques (arrivée, wifi, petit-déjeuner).

![Aperçu du projet](./preview.jpg)

## Sommaire

- [Aperçu](#aperçu)
- [Liens](#liens)
- [Mon process](#mon-process)
- [Constructed with](#constructed-with)
- [Ce que j'ai appris](#ce-que-jai-appris)
- [Pistes d'amélioration](#pistes-damélioration)
- [Auteur](#auteur)

## Aperçu

### Le défi

Les utilisateurs doivent pouvoir :

- Voir la page correctement selon la taille de leur écran (mobile / desktop)
- Voir les états `hover` sur les éléments interactifs
- Voir le reçu et la welcome card se chevaucher et "s'éventer" au survol

### Captures d'écran

Desktop | Mobile
:---: | :---:
![Desktop](./screenshots/desktop.jpg) | ![Mobile](./screenshots/mobile.jpg)

## Liens

- Code source : [ajouter le lien du repo]
- Démo en ligne : [ajouter le lien du site déployé]

## Mon process

### Constructed with

- HTML5 sémantique
- CSS3 (custom properties, Flexbox, media queries)
- [Bootstrap 5.3](https://getbootstrap.com/) — grille responsive et composants (navbar, badges)
- Font Awesome — icônes
- Approche Mobile-first

### Ce que j'ai appris

Sur ce projet, j'ai travaillé en particulier :

- L'inversion du comportement responsive classique : navbar horizontale collapsible en mobile, sidebar verticale pleine hauteur en desktop, en combinant `navbar-expand-md` de Bootstrap avec des classes flex custom (`flex-md-column`).
- Le chevauchement de cartes avec rotation et ombre portée pour un effet "photos posées sur une table" :

```css
.receipt-card {
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.12);
    transform: rotate(-6deg);
    z-index: 1;
}
.welcome-card {
    box-shadow: 0 15px 35px rgba(185, 60, 30, 0.25);
    transform: rotate(4deg);
    z-index: 2;
}
```

- L'utilisation de Flexbox (`align-items: stretch`) pour qu'une sidebar épouse naturellement la hauteur du contenu principal, sans recourir à un `position: fixed` qui la limiterait à la hauteur de l'écran visible.
- La création d'une couleur custom hors palette Bootstrap via une classe utilitaire (`.bg-creme`) plutôt que de forcer une correspondance avec les couleurs prédéfinies (`light`, `warning`, etc.).

### Pistes d'amélioration

Points identifiés à corriger dans une prochaine itération :

- Renommer les classes CSS non descriptives (`dol`, `som`, `dieu`, `cool`, `abdoul`, etc.) en noms sémantiques (`.welcome-card`, `.receipt-card`, `.info-card`...).
- Remplacer les styles inline répétés (`style="font-family: ..."`) par des classes utilitaires réutilisables.
- Remplacer les `<h3 class="btn">` par de vrais éléments `<button>` pour l'accessibilité.
- Factoriser les 3 cartes d'information (Arrival / Wifi / Breakfast) qui partagent une structure quasi identique.
- Corriger les coquilles de contenu ("liht breeze" → "light breeze", texte dupliqué entre les cartes Arrival et Breakfast).

## Auteur

- Frontend Mentor — [@ abdoumarie12]
- GitHub — [abdoumarie12]