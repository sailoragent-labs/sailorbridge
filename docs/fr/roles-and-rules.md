[← SailorBridge](README.md)

# Rôles et règles

Chaque équipe a un **Leader**. Vous lui parlez dans la discussion d’équipe. Il répond aux questions, exécute des commandes courtes et confie le travail plus long à un flux. Un exécutant exécute une étape de ce flux sur une machine de l’équipe. Le dépôt du projet contient les consignes permanentes destinées au moteur. Aucun éditeur de rôles ni bibliothèque de règles n’est disponible.

## Confier le travail à l’équipe

Ouvrez la **Discussion** de votre équipe. Demandez « Sur quelle branche sommes-nous ? » Le **Leader** peut vérifier le répertoire de l’équipe et vous répondre dans la discussion. Pour une vérification rapide sur une autre machine de l’équipe, tapez `@`, sélectionnez la machine et dites quoi vérifier. Vous recevez un résumé du résultat.

Pour un travail à livrer et à faire relire, envoyez par exemple « Mettez à jour les instructions de configuration et faites-les relire. » Quand le **Leader** propose un flux en arrière-plan, lisez la tâche sur la carte. Choisissez **Oui, Fais-le** pour la mettre en file d’attente ou **Pas Comme Ça** pour expliquer ce qui doit changer. Ouvrez la **Liste des tâches** pour suivre les étapes des exécutants. Si un exécutant a besoin d’une décision, le **Leader** consulte ce que l’équipe sait déjà et vous interroge dans la discussion s’il lui faut votre réponse.

## Donner une consigne permanente au moteur

Placez les consignes communes au projet dans le fichier `AGENTS.md` du dépôt pour Codex ou dans `CLAUDE.md` pour Claude Code. Indiquez par exemple quelle commande exécuter avant de livrer une modification. Le moteur lit son fichier de consignes quand il travaille dans ce dépôt. Vous pouvez aussi demander à l’équipe dans la discussion de garder un fait en mémoire d’une tâche à l’autre. [Mémoire d’équipe](team-memory.md)

## Reprendre une conversation après une pause

Envoyez le prochain message dans la même discussion d’équipe. Le **Leader** peut ouvrir une nouvelle session du moteur après une longue pause, un changement de moteur ou un passage à une autre machine. Il reprend le résumé enregistré par l’équipe, les messages récents, la mémoire d’équipe et les tâches inachevées. Si vous voyez **Organisation de la conversation…**, vous pouvez quand même envoyer votre message. Le **Leader** répond après avoir terminé le résumé.

## En cas de problème

- S’il manque un détail ancien, indiquez le numéro de tâche, la décision ou le fichier concerné dans votre prochain message. Une nouvelle session reçoit les 20 derniers messages et un résumé s’il existe.
- Si une consigne erronée d’une ancienne conversation continue de s’appliquer, choisissez **Vider la discussion**, vérifiez le nom de l’équipe et confirmez. Vos messages précédents disparaissent de la discussion et la prochaine session démarre sans l’ancien résumé. Si la consigne provient d’un fichier du dépôt ou de la mémoire d’équipe, corrigez-la à cet endroit.
- Si le **Leader** manque de temps, reformulez la demande en petites étapes ou envoyez le travail plus long sous forme de tâche. [Commandes](commands.md)
