[← SailorBridge](README.md)

# Commandes

Dans la discussion d’équipe, adressez une demande au **Leader** ou démarrez un flux. Utilisez `sail` dans un terminal pour gérer la machine où il est installé, consulter le travail de l’équipe ou exécuter une commande sur une autre machine de la même équipe.

## Choisir une commande dans la discussion d’équipe

Ouvrez la **Discussion** de votre équipe et tapez `/`. Le menu liste quatre raccourcis, les flux activés de l’équipe, puis `/clear`. Sélectionnez un élément, ajoutez votre demande dans votre langue et envoyez-la. Les noms de commandes restent en anglais. La sélection de `/clear` prend effet immédiatement.

| Quoi taper | Ce qui se passe |
| --- | --- |
| `/job #12 What is this waiting for?` | Le **Leader** reçoit la tâche 12 et votre question. |
| `/event #6 Move this to weekdays.` | Le **Leader** reçoit l’événement planifié 6 et la modification demandée. |
| `/memory #3 When does this apply?` | Le **Leader** reçoit l’entrée de mémoire 3 et votre question. |
| `/do Check the current branch.` | Le **Leader** accomplit le travail pendant cet échange et donne le résultat, y compris ce qu’il n’a pas pu faire. |
| `/clear` | Masque les messages précédents de la discussion d’équipe et démarre une nouvelle conversation. |

Utilisez le numéro de la liste correspondante dans votre équipe. Les tâches, événements et entrées de mémoire ont chacun leurs propres numéros. **Aller au Chat** sur une page de détails insère le bon raccourci et le numéro. Pour nommer une machine, tapez `@` et sélectionnez-la dans la liste de l’équipe.

## Lancer un flux par son nom

| Commande | Ce que vous obtenez |
| --- | --- |
| `/ask` | Une question à la fois, puis un récapitulatif des exigences dans la discussion. |
| `/plan` | Une tâche de planification. Lisez le plan et décidez si les tâches proposées doivent entrer en file. |
| `/agent` | Un exécutant accomplit le travail et transmet le résultat. |
| `/write-review` | Un rédacteur effectue le travail, exécute les vérifications et le révise selon les réglages de revue du flux. |
| `/memory-tidy` | Une tâche qui vérifie, fusionne ou retire les entrées de la mémoire d’équipe. |
| `/docs-tidy` | Une tâche qui vérifie les documents du projet et signale les points qui demandent votre jugement. |
| `/code-sweep` | Une inspection en lecture seule avec des tâches de nettoyage numérotées que vous pouvez choisir de lancer. |
| `/write-flow` | Décrivez une tâche réutilisable. Quand la tâche réussit, le nouveau flux est enregistré dans cette équipe. |
| `/edit-flow` | Donnez le nom du flux et le changement. Une modification réussie remplace un flux personnalisé. Modifier un flux intégré en crée un personnalisé sous un autre nom. |

Par exemple, envoyez `/agent Count the top-level files in this project.` Envoyer vous-même un flux en arrière-plan autorise la tâche. Le **Leader** rédige la consigne à partir de la conversation. Si **Démarrer directement** est activé, vos mots entrent directement en file. Ouvrez **Voir le détail** sur la ligne de la tâche dans la discussion pour la suivre. Quand le **Leader** propose un flux en arrière-plan dans la conversation, lisez la carte et choisissez **Oui, Fais-le** pour le lancer. [Flux et événements planifiés](flows-and-scheduled-events.md)

## Associer, vérifier ou retirer une machine

| Commande de terminal | Quand l’utiliser |
| --- | --- |
| `sail login` | La commande d’installation l’exécute pour vous. Relancez-la pour obtenir un nouveau code d’appariement ou rétablir le service à la même adresse avec les identifiants existants. |
| `sail host status` | Vérifiez l’association, la connexion, le service, la version et l’emplacement du journal. Ajoutez `--trust` pour voir l’empreinte enregistrée de la clé du serveur. |
| `sail --version` | Affiche la version installée. |
| `sail upgrade` | Cherche immédiatement une mise à jour. Le résultat indique si une nouvelle version a été installée, si la version était déjà à jour ou si la mise à jour a échoué. |
| `sail host service status` | Vérifiez le service en arrière-plan. Utilisez `sail host service install`, `sail host service restart` ou `sail host service stop` pour l’installer, le redémarrer ou l’arrêter. |
| `sail host run` | Exécutez le service de la machine au premier plan quand aucune autre instance ne tourne. |
| `sail confirm` | Dans **Confirmez que c’est vous**, obtenez un code de connexion à usage unique depuis le terminal d’une machine associée. |
| `sail recover` | Dans **Mot de passe oublié ?**, obtenez votre ID du capitaine et un code de récupération du mot de passe à usage unique depuis le terminal d’une machine associée. |
| `sail uninstall` | Supprimez SailorBridge et ses données locales, dont ses copies de travail et journaux. Vos répertoires de projets et connexions aux moteurs sont conservés. |

Pour les connexions aux moteurs, `sail account list` indique ce que la machine reconnaît. Utilisez `sail account add <name> <directory>` pour enregistrer un répertoire de connexion, `sail account remove <name>` pour retirer un enregistrement ou ignorer une connexion par défaut et `sail account restore <provider>` pour reconnaître de nouveau une connexion par défaut ignorée. Pour un point de terminaison compatible, `sail account create <provider>` écrit un modèle de paramètres dans `~/.sailorbridge/`, que `sail uninstall` supprime. [Configurer un compte GLM, DeepSeek ou Kimi à partir d’un modèle](engine-accounts-and-pacing.md#configurer-un-compte-glm-deepseek-ou-kimi-à-partir-dun-modèle)

## Utiliser les éléments numérotés de l’équipe

Dans un terminal sur une machine associée, exécutez les commandes suivantes dans le répertoire de projet configuré pour l’équipe. Utilisez les numéros de votre équipe. Par exemple, la tâche affichée comme `#12` dans la discussion s’écrit `12` dans une commande de terminal.

| Action | Commandes à exécuter dans votre terminal |
| --- | --- |
| Trouver une tâche | `sail job list` liste les tâches ouvertes. Ajoutez `--all` pour inclure les tâches terminées. `sail job get 12` affiche la tâche 12. Ajoutez `--json` pour tous les détails. |
| Arrêter ou supprimer une tâche | `sail job stop 12` arrête la tâche. `sail job delete 12` supprime l’enregistrement d’une tâche terminée. |
| Trouver un événement | `sail event list` liste les événements activés qui doivent encore s’exécuter. Ajoutez `--all` pour inclure les événements désactivés ou terminés. `sail event get 6` affiche le message et l’horaire. |
| Supprimer un événement | `sail event delete 6` supprime l’événement planifié. |
| Supprimer une entrée de mémoire | `sail memory delete 3` supprime définitivement une entrée. Pour supprimer une entrée verrouillée, utilisez **Mémoire d’équipe** dans l’application. |

Les commandes ci-dessous nécessitent une session active du **Leader** ou une tâche. Depuis votre terminal, elles renvoient `local_team_context_missing` même dans le répertoire de l’équipe. Demandez ce dont vous avez besoin au **Leader** dans la discussion d’équipe. Pour agir vous-même sur un élément existant, ouvrez **Liste des tâches**, **Événements planifiés** ou **Mémoire d’équipe** dans l’application. Les exécutants ont accès aux tâches et aux événements en lecture seule.

| Qui l’exécute | Action et commandes |
| --- | --- |
| **Leader** | `sail job create <flow> "<task>"` met un flux en arrière-plan en file. `sail job edit 12 "<revised task>"` modifie une tâche ouverte. `sail job retry 12` reprend le travail admissible sous le même numéro. |
| **Leader** | `sail event create "Check the queue" --weekdays 09:00` planifie un message de discussion d’équipe dans le fuseau horaire de la machine. Les autres horaires utilisent `--once`, `--daily` ou `--every`. Utilisez `--tz` pour préciser un fuseau. `sail event edit 6 --disable` met l’événement en pause. |
| **Leader** ou exécutant | `sail memory list` liste les entrées. `sail memory titles` liste les titres. `sail memory search "release checklist"` renvoie jusqu’à 10 résultats. `sail memory get 3` lit l’entrée. |
| **Leader** ou exécutant | `sail memory create "<title>" "<body>"` enregistre un fait ou propose une correction sous le même titre. `sail memory edit 3 "<body>"` modifie une entrée. `sail memory conflicts` liste les conflits non résolus. |
| **Leader** | `sail memory resolve <id> --value "<correct text>"` résout un conflit à partir de son ID. Une entrée verrouillée nécessite votre décision dans **Mémoire d’équipe**. |
| **Leader** ou exécutant | `sail memory list --tidy` liste les candidats et leurs versions. `sail memory review 3 --rev <version>` marque une entrée à conserver. `sail memory merge` accepte plusieurs arguments `--entry <id>:<version>`, ainsi que `--title` et `--body`. Parmi les tâches d’exécutants, seul `/memory-tidy` peut supprimer des entrées. |

Si une commande signale une décision en attente, vérifiez la valeur actuelle dans la réponse avant de considérer que le changement a pris effet.

## Exécuter une commande localement ou sur une autre machine de l’équipe

Pour une commande locale, `sail run git status` envoie le résultat à votre terminal. Pour une commande longue et non interactive, ajoutez `--fold` avant la commande. Vous recevez le résultat, les dernières lignes de sortie et le chemin du journal complet. Pour une fenêtre tmux locale, `sail tmux read <window>` affiche son texte. `sail tmux send <window> "<text>"` remplit la saisie. Envoyez `sail tmux send <window> --key Enter` pour valider la saisie.

Pour exécuter une commande sur une autre machine qui vous appartient dans la même équipe, partez du répertoire de l’équipe et remplacez `build-machine` par le nom de la machine cible. Par exemple, `sail exec build-machine git status --short` s’exécute dans le répertoire de cette équipe sur la cible. Le code de sortie et les 40 dernières lignes des sorties combinées, jusqu’à 16 KiB, reviennent dans votre terminal. Utilisez `--json` avant le nom de la machine pour obtenir un résultat JSON unique.

Le délai par défaut est de 5 minutes. Pour le changer, placez `--timeout` et un nombre positif de secondes avant le nom de la machine. Une machine émettrice peut attendre le résultat de 8 commandes au maximum. Ctrl-C arrête l’attente dans votre terminal. La commande distante peut continuer.

## En cas de problème

- Si une commande de discussion est inconnue, tapez `/` et choisissez un flux activé. Si une ancienne carte de confirmation renvoie à un flux désactivé, réactivez-le dans **Flux de l’équipe** ou choisissez un flux disponible et envoyez une nouvelle demande.
- Si un raccourci numéroté est introuvable, ouvrez **Liste des tâches**, **Événements planifiés** ou **Mémoire d’équipe** pour cette équipe. Vérifiez le numéro et incluez `#` dans la discussion.
- Si `sail exec` ne peut pas identifier l’équipe, passez à l’un des répertoires d’équipe indiqués. Si la cible est hors ligne ou ne prend plus de travail, réessayez une fois qu’elle est en ligne et accepte du travail. Une cible en ligne a jusqu’à 10 minutes pour prendre une commande en file. Si elle passe hors ligne avant de la prendre, la commande attend 60 secondes sa reconnexion. Si la cible disparaît après le démarrage, vérifiez ce que la commande a fait avant de la relancer.
