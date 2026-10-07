# Spiderpoutine

Experience interactive de physique pour Imane et Kenzo autour d'une question : comment les pouvoirs de Spider-Man fonctionneraient-ils dans le monde reel ?

Site : https://spiderpoutine.helloredwan.me

## Intention

Mini-exposition type Cite des sciences, pas cours scolaire.

Structure cible de chaque chapitre :

1. Question Spider-Man
2. Prediction de l'enfant
3. Experience manipulable
4. Observation
5. Explication simple
6. Point de reference reel
7. Verdict pour Spider-Man

Public cible : enfants autour de 7 ans, curieux, capables de comprendre une idee scientifique lorsqu'elle est concrete.

## Les 8 questions

1. La chute : gravite, acceleration, hauteur, vitesse.
2. La toile : distance, vitesse, temps.
3. Le son : Mach, vitesse du son, onde de choc.
4. La corde : tension vs compression.
5. L'impact : energie cinetique, distance d'arret, deceleration.
6. Les g : Terre, grand huit, pilote de chasse, impact.
7. Le swing : mouvement circulaire, tension, vitesse.
8. L'elasticite : distance d'arret, deceleration, absorption d'energie.

## Architecture

Site statique sans backend.

- index.html contient HTML, CSS et JavaScript (aucun framework, aucun build, aucune dépendance hors Google Fonts).
- Les 8 chapitres et la mission finale sont chacun une scène Canvas 2D interactive, pilotée par une seule boucle requestAnimationFrame.
- Chaque scène ne s'anime que lorsqu'elle est visible (IntersectionObserver).
- Son via Web Audio (déclenché après le premier toucher), vibration optionnelle, mode savant pour les formules.
- Progression 1/8 à 8/8 dans la barre de chapitres, record du jeu en localStorage.
- labo.html redirige vers la mission finale (ancienne page de démo).
- Responsive, mobile-first, devicePixelRatio pris en compte, prefers-reduced-motion respecté.

## Les scènes

1. La chute : on glisse le héros en hauteur, chute stroboscopique (ombres toutes les 0,25 s), compteur km/h, coussin et g à l'arrêt.
2. La toile : course sur 30 m entre héros, voiture, TGV, avion, toile et son.
3. Le son : ondes sonores visibles, le cône de Mach apparaît au-delà de 343 m/s.
4. La corde : pousser (la corde flambe) ou tirer avec une pointe (elle suit), au doigt.
5. L'impact : énergie de la pointe de 5 g en carrés de 10 J, comparée à une balle de tennis servie.
6. Les g : canapé, avion de ligne, grand huit, pilote, pointe ; héros écrasé sur son siège et balance.
7. Le swing : pendule avec flèches de forces (poids et tension), toile molle détectée.
8. L'élasticité : toile rigide contre toile réglable, même chute de 46 m.
Mission finale : jeu de swing à travers la ville, jauge de g en direct, réglage rigide/élastique.

### Important : ne pas doubler les moteurs de rendu

Une dette apparue pendant le developpement etait la coexistence des anciennes scenes DOM et de leurs remplacements Canvas. Cela produisait scenes dupliquees et HUD coupes sur mobile.

Les anciennes scenes remplacees sont explicitement masquees. Ne pas ajouter une nouvelle scene sans retirer/remplacer l'ancienne.

## References physiques

Valeurs simplifiees et arrondies pour l'apprentissage :

- gravite : environ 9,81 m/s2 ;
- vitesse du son : environ 343 m/s vers 20 C ;
- chute sans resistance de l'air : v = sqrt(2gh) ;
- energie cinetique : E = 1/2 mv2 ;
- mouvement circulaire : Fc = mv2/r ;
- Statue de la Liberte : environ 46 m pour la statue et 93 m sol-torche ;
- tour Eiffel : environ 330 m ;
- Empire State Building : environ 381 m de hauteur architecturale.

## Deploiement

Repo : Redoudou/Spiderpoutine

GitHub Pages est deploye via .github/workflows/pages.yml sur chaque push main.

Custom domain : spiderpoutine.helloredwan.me

DNS : CNAME vers redoudou.github.io.

## Roadmap

Priorite : homogeniser les 8 chapitres autour de :

Prediction -> Tester -> Observer -> Comprendre -> Comparer -> Verdict

Idees :
- prediction avant chaque experience ;
- revelation apres simulation ;
- "Ce qu'on vient de decouvrir" en une phrase ;
- verdict vert/orange/rouge par pouvoir ;
- laboratoire final combinant vitesse, longueur, elasticite et masse ;
- progression 1/8 a 8/8 ;
- araignee comme source d'indices occasionnels ;
- tests systematiques a 320, 375, 390 et 430 px.

## Regle editoriale

Une valeur scientifique ne doit presque jamais apparaitre seule.

Exemple : "93 m" devient "93 m : environ la hauteur totale de la Statue de la Liberte, socle compris."

Le but est que l'enfant puisse se representer le nombre, pas seulement le lire.
