# Cours 5 - Principes, directives et patrons de conception

## Les principes de conception

> Plus généraux, plus fondamentaux, plus vagues; s’appliquent dans plus de cas
> mais peuvent être moins évidents à appliquer

- Connaissez votre utilisateur
- Minimisez le besoin de mémoriser
- Optimisez les opérations
- Concevez en vue des erreurs possibles

### Principe de Shneiderman (principe conception) (IMPORTANT)
- Être cohérent (consistent)
- Concevoir pour différents utilisateurs (Seek universal usability)
- Donner un retour visuel informatif
- Indiquer à l’utilisateur que la tâche est complétée "Yield closure"
- Offrir une gestion d’erreur simple
- Rendre les actions réversibles 
- Mettre l’utilisateur en contrôle (user initiates task it's not forced upon him)
- Réduire la dépendance à la mémoire court-terme

### Principe autre que Shneiderman
- User Engineering Principles for Interactive Systems (Hansen, 1971) (principe conception)
- Rubinstein et Hersh (1984) (principe conception)
- Les principes de Joel Spolsky (principe conception)

## Les directives de conception

> Indiquent plus précisément quoi faire Plus précises, plus détaillées,
> s’appliquent dans moins de cas mais disent plus précisément quoi faire

Peux s'adapter selon le OS/environnement

- Permettre une navigation simple
- Rendre les cibles suffisamment grandes
- Réduire le désordre
- Afficher le texte suffisament grand
- Utiliser des contrôles tactiles
- Utiliser des formulaires simples
- Tenir compte de la position du pouce
- Concevoir une expérience cohérente

### Avantages
 - Stimules des idées de conception
 - Donnent des conseils utiles
 - Servent comme liste de vérification
 - Peuvent être utilisé pour évaluer une interface

### Désavantages
- Parfois contradiction avec 2 directives
- Souvent trop vague ou trop spécifique
- Peuvent être trop nombreux

## Patron de conception

En GUI, un patron de conception est une solution récurrente à un problème
commun de conception d’interface

### Exemple

- pull to refresh (apple mail)
- feature, search and brows (search bar in website)
- clear entry point (landing page where do i go from there for "something")
- grid of equals (Netflix film browser)
- skeuomorphic (visual style)
- filmstrip (mobile like infinit scroll of feed)
- two-panel selector split view (spotify/discord)
- action panel (window start button)
- datatips (give info on hover google maps)
- forgiving format (input field autoformating as you input phone number/credit card)

# Cours 6 - Esquisses et prototypage

## Prototype

Un prototype est un modèle ou un échantillon non complété servant à tester un
concept ou un processus

> On les utilise comme outils de conception et pour les tests avec les
> utilisateurs

### Types

- Prototypes statiques / dynamiques
- Prototypes de haute fidelité / basse fidelité
- Prototypes horizontaux (functionality) / verticaux (features)

### Avantages d’esquisser ou prototyper plusieurs alternatives en parallèle

- Permet d’explorer plus de possibilités et peut-être d’en combiner
- Permet d’éliminer une mauvaise idée de départ
- Séparation de notre égo des idées conçues – on accepte mieux les critiques
- Encourage la comparaison de différentes possibilités

### Dynamique

Un prototype qui offre un minimum de fonctionnalité à l’utilisateur

- Prototype animé
	- S’affiche écran par écran dans une forme de présentation par diapositives
- Prototype de type Magicien d’Oz
	- S’exécute sous forme de présentation par diapositives mais avec l’ajout d’intelligence pour afficher la diapo suivante selon l’action de l’utilisateur
- Prototype interactif
	- S’exécute sur l’ordinateur et répond à certains intrants en temps réel
- Prototype fonctionnel
	- S’exécute sur l’ordinateur, répond aux intrants en temps réel et performe certaines opérations en arrière-plan

### plusieurs moyen de prototyper statique

> statique -> inverse de dynamique

- papier
- wireframe
- images
- static HTML
- .exe no features
- figma
- axure

# Cours 7 - Modélisation KLM

## KLM

> se limite aux utilisateurs (experts) et aux taches familières

- Déterminer les tâches élémentaires de l'interface.
	- e.g. ajouter un client, acheter un produit, etc.
- Établir les modèles KLM de chacune de ces tâches.
	- Modèle = séquence d'actions élémentaires
- Estimer les temps d'exécution Ti de ces tâches.
- Estimer les fréquences Fi des tâches pour un usager-type.
- Quantifier l'efficience globale
	- cummation ($f_{i} \cdot t_{i}$).

### Rules
- Homing (H) - 400ms
- Pointage (P) - 1100ms
- Keystroke (K) - 200ms
- Button press or release (B) -  100ms
- Activité mentale (M) - 1200ms
- Réponse du système (R ou W) - $max(t, 1200)$ ms
- Défilement (Scroll) - 3960ms

- Placer les M
	- Écrire séquence sans les M
	- Placer un M devant chaaque P, B, k
	- Remplacer M consécutif par un M (MM->M)


### EG

- Écrire dlabbe au clavier
-> M K M K M K M K M K M K M K = $MK^5MK$
-> M au debut et fin

- {Click Delete} {Click Yes} {Click OK}
-> MHPBB          MPBB       MPBB
-> MHPK           PBB        PBB

Détruire un fichier depuis une liste

- M,H,P,BB 	Sélectionne l'icone du fichier
- M			Activité mental
- H			remet la main sur le clavier
- K			Pese sur (DEL)
- R(0.500)	Reponse (affiche la fenetre de dialogue)
- M			Activite mental
- H			Remet la mian sur le ponteur
- P			Pointe sur l bouton OK
- BB		Clique

On utilise FLM pour ecran tactile

# Cours 8 - Lois psychomotrices

## Loi de Fitts

$$\boxed{T = a+b \cdot \log_{2}(D/W + 1)}$$
- T ou MT = temps moyen de mouvement
- $D$ = distance
- $W$ = largeur cible (si 2D prend Min(x,y))
- $a$, $b$ constantes mesurées
- $IP = 1/b$ -> indice de performance

La loi de Fitts modélise les mouvements réciproques ("aller retour") et discrets
("un coup") en 1D ou en 2D

### Se joue sur

- Distance à parcourir avec curseur
- Taille du curseur
- Taille du bouton

### Passer à travers un but

## Loi de Hick hyman (temps de réaction)

La loi de Hick-Hyman décrit le temps de réaction/désicion selon
le nombre d’alternatives présentées

$$\boxed{\text{Temps de réaction} = a + b \cdot \log_{2}(N+1)}$$
- N = nb de choix
- a, b des constantes mesurées de facons expérimental

# Cours 9 - Perception visuelle et graphisme

## Perception (vision)

- Éléments essentiels pour l'utilisation des GUI
- Derrière une grande partie des principes de conception des GUI

- **Vision** = processus biologiquepar lequel on capte la lumière et la transforme en impulsions électriquesprocessus biologiquepar lequel on capte la lumière et la transforme en impulsions électriques.
- **Perception** = manière dont le cerveau interprète ces impulsions.

### Vision périphérique
- On centre la fovéa (partie de l'oeil) à quelque part et notre cerveau remplit le reste avec la vision périphérique et nos attentes/connaissances.
- Implications pour le GUI
	- Si on mets un message d'erreur trop loin d'où la fovea est focus, l'utilisateur peut ne pas le voir

### Effet du "pop-out" pré-attentif
Lorsque notre attention est attiré automatiquement par quelque chose dans notre champ visuel, sans y porter attention.

Plusieurs variables: couleur, forme, taille, orientation, mouvement, espacement, lissage ou ombrage.

Conjonction de deux variables => Pas d'effet "pop-out".

### Subitiser
- Limité jusqu'à 4 à 5 objets.
- Coûte 40 à 100ms par objet alors que compter coût 250 à 300ms par objet.

### Reconnaissance vs Rappel

- **Reconnaissance**: processus de reconnaissance d'information comme étant familière ou déjà vu précédemment. Très rapide, car ne nécessite pas de traîtement comparatif.
- **Rappel**: processus de récupération active d'une information à long terme sans l'aide de stimuli extérieurs. Plus long et difficile, car on doit aller chercher dans la mémoire à long terme.
- Exemples dans les interfaces:
	- Icônes = reconnaissance des formes
	- Suggestions de recherche (Spotlight) = reconnaissance
	- Rappel de username/password = reconnaissance des indices
	- Raccourcis clavier = rappel

### Distinction des couleurs

- Tris facteurs impactent grandement notre capacité à distinguer deux couleurs:
	- Pâleur (luminance élevée, saturation basse)
	- Taille de l'échantillon
	- Espacement

### Composantes HSV
- Teinte (hue): fréquence "dominante";
- Saturation: "pureté" de la teinte (ex: rouge est plus saturé que rose, gris et blanc ne sont pas saturés du tout)
- Valeur (luminance ou lumière): mesure de clarté

### Couleurs dans les GUI
- Couleurs pures (saturées):
	- Attirent l'attention
	- Peuvent communiquer de l'excitation
	- Besoin de plus de *focus* que les couleurs moins pures (désaturées)
	- Peuvent entraîner de la fatigue oculaire
- Utiliser les couleurs saturées dans le UI pour faire ressortir un élément (avertissement, erreur, etc...)

### Perceptions

- Perception de structure: l'utilisateur cherche à percevoir la structure de l'interface, surtout pour:
	- Identifier les éléments formant un groupe logique
	- Identifier les informations importantes
	- Comprendre l'ordre logique de l'interface

- Perception de gestalt: percoit les objects comme des ensembles cohérents plutôt que des éléments individuels. Quelques principes de Gestals:
	- Proximité
	- Similitude (continuité)
	- Sort commun (symétrie)
	- Figure / arrière plan

### Structurer l'information

#### Patron en F
- Les premières lignes et les premiers mots à gauche sont toujours plus regardées que les autres
- On l'utilise quand:
	- une page n'a pas de mise en forme pour le Web (ex: mur de texte mais pas de gras, de puces ou de titres)
	- on essaie d'être le plus efficace sur cette page
	- on n'est pas assez engagé ou intéressé

- Créer une hiérarchie visuelle
- Ne jamais center un paragraphe de texte

# Cours 10 - Psychologie des utilisateurs

## Safe exploration

Il s'agit de permettre à l'utilisateur d'explorer une nouvelle interface de manière sécurisée en offrant des options de retour en arrière ou de réinitialisation pour éviter toute perte de données.

Exemple : Une application mobile qui permet de supprimer une tâche ou une note, mais qui demande une confirmation avant de la supprimer définitivement.

## Instant gratification

Les interfaces doivent être conçues pour offrir une expérience utilisateur satisfaisante et rapide, en donnant une réponse immédiate à une action de l'utilisateur.

Exemple : Un bouton "Ajouter au panier" qui affiche immédiatement une notification de confirmation.

## Satisficing

Les utilisateurs ne cherchent pas toujours la solution optimale, mais plutôt une solution satisfaisante. Les interfaces doivent être conçues pour offrir des solutions satisfaisantes pour les tâches courantes.

Exemple : Un site de commerce électronique qui propose des produits similaires ou liés à un produit sélectionné pour faciliter la recherche de produits connexes.

## Changes in midstream

Les utilisateurs peuvent changer d'avis ou d'objectifs en cours de tâche. Les interfaces doivent être conçues pour permettre aux utilisateurs de changer de direction ou de tâche en cours de route.

Exemple : Un formulaire qui permet aux utilisateurs de modifier ou de corriger les informations saisies précédemment sans avoir à recommencer depuis le début.

## Deferred choices

Les utilisateurs peuvent ne pas être prêts à prendre une décision immédiate. Les interfaces doivent être conçues pour permettre aux utilisateurs de différer certaines décisions.

Exemple : Un site de réservation qui permet aux utilisateurs de sauvegarder une réservation en cours pour la finaliser plus tard.

## Streamlined repetition

Les utilisateurs peuvent avoir besoin de répéter une tâche plusieurs fois. Les interfaces doivent être conçues pour faciliter la répétition rapide et facile des tâches courantes.

Exemple : Un formulaire d'inscription qui permet de sauvegarder les informations pour une inscription ultérieure, sans avoir à tout saisir de nouveau.

## Loi de Miller (ou la loi magique de 7 +/- 2)

Stipule que la capacité de la mémoire de travail humaine est limitée à environ 7 éléments (plus ou moins 2).

Exemple : Les numéros de téléphone sont généralement composés de 7 chiffres (et parfois plus), ce qui est facilement mémorisable pour la plupart des gens.

## Loi de Postel (ou principe de tolérance)

Stipule qu'un programme informatique doit être tolérant aux erreurs ou aux variations dans les entrées. Les utilisateurs ne sont pas des machines, ils peuvent faire des erreurs. Peuvent devenir irrités quand on leur demande trop d'informations.

Exemple : 
- Un programme qui peut décoder des fichiers multimédias même si les fichiers sont légèrement corrompus ou si certaines données sont manquantes.
- Apple ID nous permet de se faire plusieurs choses (déverouiller le téléphone, faire des achats, etc.)

## Règle sommet-fin (peak-end rule)

Stipule que les utilisateurs se souviennent mieux des premières et des dernières interactions avec un système, tandis que les interactions au milieu sont souvent oubliées.

Diminuer l'intenstion des désagréments, les utilisateurs retiennent les mauvaises expériences plus que les bonnes.

Mettre un emphase pour rendre la fin de tâche la plus satisfaisante possible.

Exemple :
- Un parcours client en ligne bien conçu qui crée une expérience utilisateur positive dès le début et qui se termine par une confirmation ou un résumé clair de l'interaction, améliorant ainsi la mémorisation de l'expérience. 
- Mettre de l'humour sur les pages d'erreurs (404)

## Effet usabilité-esthétique

Se réfère au fait que les interfaces visuellement attrayantes sont perçues comme plus faciles à utiliser, même si leur efficacité réelle est la même que celle des interfaces moins attrayantes.

Exemple : Un site Web avec une mise en page esthétique et des couleurs harmonieuses qui attirent l'attention des visiteurs et leur donnent une impression positive.

## Loi de Tesler (ou loi de la conservation de la complexité)

Stipule que la complexité ne peut pas être éliminée, mais seulement déplacée ou cachée. Elle doit être assumée par le système ou son utilisateur. Essayer d'assumer le maximum pour réduire le fardeau sur l'utilisateur.

Exemple :
- Un logiciel qui propose des options avancées cachées dans des menus déroulants pour simplifier l'interface de base, tout en offrant des options supplémentaires pour les utilisateurs avancés.
- Les suggestions de messages prédéfinis sur Gmail.
- Utiliser la même adresse de shipping que celle de facturation.

## Modèle accrocheur (Hook Model)

Technique de conception d'interface utilisateur pour encourager l'utilisation continue d'un produit en créant une boucle de rétroaction (feedback loop) qui incite les utilisateurs à revenir (créer une habitude).

### Trigger (élément déclencheur)

Incite l'utilisateur à intéragir avec le produit.

- **Externe**: vient de l'environnement de l'utilisateur. (ex: courriel, message texte, notification)
- **Interne**: vient de l'utilisateur lui-même, souvent une émotion ou un besoin. (ex: ennui, solitude, recherche de valorisation)

Exemple : Un réseau social qui envoie des notifications pour signaler de nouvelles activités ou messages sur la plateforme pour inciter les utilisateurs à revenir régulièrement. 

### Action

L'action que l'utilisateur doit faire afin d'obtenir une récompense ou satisfaction qu'il anticipe.

Exemple: Cliquer sur une notification.

### Récompense

Élément qui procure une satisfaction à l'utilisateur après avoir accompli une action. Elle doit être **immédiate** et **variable** (imprévisible) pour maintenir l'intérêt de l'utilisateur.

- Trois natures:
	- Tribe (tribue): récompenses sociales basées sur la connexion et l'acceptation.
	- Hunt (chasse): recherche de ressources matérielles.
	- Self (soi): gratification personnelle sous forme de maîtrise ou de réalisation de soi.

Exemple : L'utilisateur lit le message et ressent une satisfaction sociale.

### Investissement

Encourage l'utilisateur à répéter l'action dans le futur. Cela peut inclure le temps, l'argent ou les données personnelles investis dans l'utilisation du produit ou service. Peut avoir l'effet d'entreproser de la valeur dans le produit.

Peut mener indirectement au prochain *trigger* externe (ou même interne).

Exemple :
- L'effet IKEA, le fait que le client ai construit lui-même le meuble le rend plus précieux à ses yeux.
- L'utilisateur répond au message et investit du temps et de l'énergie dans la conversation pour renforcer ses liens sociaux sur la plateforme.

# Cours 11 - Méthodologie d'évaluation


