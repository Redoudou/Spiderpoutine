# Historique

## 2026-10-07

### Le labo animé (labo.html)

Nouvelle page autonome, liée depuis l'accueil, avec trois scènes Canvas jouables et un héros original (combinaison orange, lunettes turquoise) :
- chute stroboscopique (ombres toutes les 0,25 s, compteur km/h, coussin et g à l'arrêt) ;
- tir de toile avec ondes sonores visibles : le cône de Mach apparaît au-delà de 343 m/s ;
- jeu de swing à travers la ville, jauge de g en direct, réglage rigide/élastique, record.

Son (Web Audio), vibration et mode savant en option. Aucune dépendance, aucun build.

### Origine

Analyse de la physique de Spider-Man : chute, vitesse de la toile, Mach 1, lancement d'une matiere flexible, impact, tension du swing et elasticite.

Le sujet devient une experience educative en francais pour Imane et Kenzo.

### V1

Page HTML avec 8 chapitres, equations simples, comparaisons et sliders.

Limite : trop proche d'une fiche de cours, animations surtout decoratives.

### V2

Ajout d'animations de chute, tir de toile, ondes, swing et elasticite.

Constat : envoyer un fichier HTML par WhatsApp est une mauvaise UX mobile.

### Publication

Repo Redoudou/Spiderpoutine.
Publication index.html.
Workflow GitHub Pages.
Custom domain spiderpoutine.helloredwan.me.

### Refonte visuelle

Ajout de palette rouge/bleu, skyline, personnages stylises, onomatopees, araignee-guide et navigation 1 a 8.

### Passage a Canvas

Migration des scenes principales vers Canvas 2D :
- chute ;
- tir de toile ;
- Mach 1 ;
- swing.

### Bug important : scenes dupliquees

Les anciennes scenes HTML restaient visibles sous les nouvelles scenes Canvas.

Symptomes :
- deux animations ;
- HUD coupe ;
- grandes zones de decor inutiles ;
- mauvais rendu mobile.

Correctif : masquage explicite des anciennes scenes et de leurs controles.

### Recentrage pedagogique

Les effets visuels avaient commence a prendre le dessus.

Nouvelle structure :
Question -> Experience -> Observation -> Explication -> Reference -> Verdict.

Ajout d'experiences aux chapitres corde, impact, g et elasticite.

### References reelles

Ajout d'une echelle de hauteur interactive :
- 46 m : Statue de la Liberte sans socle ;
- 93 m : Statue de la Liberte complete ;
- 115 m : 2e etage de la tour Eiffel ;
- 330 m : tour Eiffel ;
- 381 m : Empire State Building.

Le texte evolue avec le slider.

## Etat actuel

Site statique GitHub Pages avec custom domain.

Dette technique : plusieurs generations de CSS et composants restent dans index.html. Quand le concept sera stabilise, refactoriser vers styles.css et simulations.js et supprimer definitivement le code legacy.

Voir README.md pour principes et roadmap.
