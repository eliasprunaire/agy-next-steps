# Suivi de trajectoire (`follow-ups`)

## Quand afficher le bloc

À la fin de chaque réponse substantielle, ajoute un bloc court proposant les suites les plus pertinentes pour continuer le travail.

N'affiche pas ce bloc :
- après une réponse triviale en une ou deux phrases ;
- lorsque tu attends déjà une décision bloquante ou un GO explicite de l'utilisateur.

## Format imposé (compatible IDE et CLI)

Utilise impérativement une vraie liste Markdown à puces après une ligne de séparation `---` (jamais de lignes `1:` / `2:` brutes que CommonMark fusionne en un seul paragraphe dans l'IDE, et jamais une liste numérotée `1.` / `2.` / `0.` qui renumérote `0` en `4`) :

---

**Suites possibles :**
- **1 (Recommandé)** : <prompt autonome à l'impératif avec cible exacte et résultat attendu> *(Pourquoi : <raison courte en max 12 mots>)*
- **2** : <prompt autonome de vérification, test ou alternative concrète>
- **3** : <prompt autonome de suite logique, revue ou capitalisation>
- **0** : Autre sujet (ignorer ces suggestions)

## Qualité des propositions

- Adapte le nombre d'options au contexte réel : **1 à 3 options utiles** (inutile d'en inventer une 3e artificielle si seules 1 ou 2 ont du sens), toujours suivies de `- **0** : Autre sujet (ignorer ces suggestions)`.
- Place toujours en **position 1** l'unique suite la plus pertinente dans la situation actuelle de la session, marquée `(Recommandé)` et suivie d'une justification très courte (`*(Pourquoi : ...)*`, 12 mots maximum). Les options 2 et 3 ne portent pas ce marqueur.
- Rédige chaque option comme un **prompt complet, autonome et directement exécutable** sur une seule ligne (verbe à l'impératif, cible précise : chemin de fichier, commande, dépôt ou skill réellement disponible).
- N'invente jamais un nom de skill, de commande ou de fichier non vérifié.

## Interprétation des réponses courtes et multi-sélection

- **Choix unique** (`1`, `2`, `3`) : exécute directement le prompt de l'option correspondante.
- **Multi-sélection** (`1+2`, `1, 3`, `1 2 3`, `1 et 2`, `1 puis 3`) : exécute les options sélectionnées **dans l'ordre indiqué**, en les combinant proprement dans le même tour.
- **Choix avec précision** (ex. `1+2 sans toucher aux tests`, `2 uniquement sur auth.ts`) : exécute les options choisies en appliquant la contrainte ajoutée.
- **Annulation** (`0` ou nouveau sujet) : ignore les suggestions et traite le nouveau message sans commentaire.
- **Sécurité** : si une ou plusieurs options choisies impliquent une action destructive, irréversible, hors dépôt local, en production ou touchant des secrets, demande un GO explicite avant d'exécuter cette partie.
