[← SailorBridge](README.md)

# Flux et événements planifiés

Un flux donne à votre équipe une méthode réutilisable pour accomplir une tâche. Il a un nom que vous pouvez taper dans la discussion, ainsi que des étapes et des options enregistrées pour cette équipe. Un événement planifié envoie un message à la discussion d’équipe à l’heure de votre choix. Le message peut poser une question au leader ou lancer un flux.

## Trouver et lancer un flux

Dans la discussion d’équipe, tapez `/` pour voir les flux activés et leur description. Choisissez un flux, ajoutez votre demande, puis envoyez-la. Par exemple, `/ask What should the export include?` ouvre une conversation sur cette exigence. Un flux interactif pose des questions dans la discussion. Un flux en arrière-plan apparaît dans **Liste des tâches**.

Quand vous envoyez une commande de flux en arrière-plan, le **Leader** s’appuie normalement sur la conversation pour rédiger la consigne et mettre la tâche en file. Si **Démarrer directement** est activé pour ce flux, votre texte sert de consigne et la tâche entre immédiatement en file. Cette option est désactivée par défaut pour les flux intégrés en arrière-plan. Quand le leader propose une tâche de lui-même, choisissez **Oui, Fais-le** pour la lancer.

| Flux intégré | Quand l’utiliser et résultat obtenu |
| --- | --- |
| `/ask` | Précisez une décision. Répondez à une question à la fois pour obtenir un récapitulatif des exigences. |
| `/plan` | Planifiez un travail en plusieurs tâches. Lisez le plan et le lot proposé, puis choisissez **Tout mettre en attente**, **Modifier le plan** ou **Pas maintenant**. Le plan est lui-même une tâche que vous pouvez suivre. |
| `/agent` | Confiez un travail répétitif ou long à un exécutant. Un exécutant l’exécute et transmet le résultat sans tour de revue. |
| `/write-review` | Confiez une mise en œuvre à l’équipe et indiquez comment la vérifier. Un rédacteur fait le travail, les vérifications s’exécutent et le rédacteur et le relecteur examinent le résultat. |
| `/memory-tidy` | Passez en revue la mémoire d’équipe, supprimez les entrées devenues inutiles et fusionnez les doublons. La livraison liste les actions et les suggestions qui attendent votre décision. L’équipe peut aussi le faire automatiquement quand des entrées en ont besoin, au plus une fois en 24 heures. |
| `/docs-tidy` | Revérifiez la documentation concernée par les changements, ainsi qu’une partie du reste à chaque passage par roulement. La livraison distingue les corrections mécaniques des questions qui vous sont destinées. |
| `/code-sweep` | Examinez le code pour repérer les améliorations possibles. Lisez les propositions numérotées dans la livraison et indiquez au leader lesquelles appliquer. L’examen se fait en lecture seule. |
| `/write-flow` et `/edit-flow` | Décrivez une tâche reproductible pour créer un flux ou expliquez comment modifier un flux existant. Le résultat est enregistré pour votre équipe. |

## Choisir qui rédige et qui relit

Ouvrez ⋯ dans la discussion d’équipe, choisissez **Flux de l’équipe** et ouvrez `/write-review`. La page affiche les étapes et les options des prochaines tâches de cette équipe.

| Option | Utilisation |
| --- | --- |
| **Qui écrit** | Gardez **Automatique** pour sélectionner un fournisseur selon la difficulté ou sélectionnez un moteur pour les étapes de rédaction. |
| **Qui révise** | Gardez **Automatique** pour chercher un relecteur indépendant d’une autre famille de modèles, ou sélectionnez un moteur pour la revue. Le rédacteur assure sa propre auto-revue. Les réglages de modèles de l’équipe déterminent les modèles utilisés. |
| **Passes d’auto-révision** | Choisissez de 0 à 10, avec 3 par défaut. À chaque tour, le rédacteur contrôle son travail, corrige les problèmes repérés et recommence jusqu’à ce qu’un passage ne trouve plus rien ou que la limite soit atteinte. Réglez sur 0 pour passer l’auto-revue. |
| **Combien de tours au maximum** | Choisissez de 0 à 10, avec 6 par défaut. Réglez sur 0 pour le mode Solo, qui saute la revue indépendante et conserve votre réglage d’auto-revue. |

Un constat P1 demande une nouvelle revue de l’ensemble du changement. Les constats moins graves demandent une revue des corrections. À partir du troisième tour, en l’absence de P1, le rédacteur peut terminer les dernières corrections et livrer sans autre revue. Si des P1 subsistent à la limite de tours, ouvrez **Rapport de livraison** pour voir les constats qui ont arrêté la tâche.

Pour fusionner du code, la vérification applicable complète doit réussir sur le commit final. Si aucune vérification ne s’applique à un changement portant uniquement sur la documentation, un relecteur indépendant doit accepter la justification. En mode Solo, un changement sans vérification à exécuter reste **Inachevé**. [Lire les vérifications et la livraison d’une tâche](jobs.md)

## Écrire ou modifier un flux d’équipe

1. Dans la discussion d’équipe, envoyez `/write-flow` suivi des étapes, des critères d’achèvement, de la marche à suivre si une étape échoue et de la livraison attendue. Par exemple, `/write-flow List Markdown files changed since the last commit. Report their paths. If none changed, say so.`
2. Si le rédacteur a besoin d’une décision, répondez à sa question dans la discussion. Une fois le flux écrit et vérifié, la discussion affiche le nom sous lequel il a été enregistré. Choisissez **Voir le flux** pour lire sa description, ses étapes et ses options. Son nom est maintenant disponible dans le menu `/`.
3. Pour modifier le flux, choisissez **Modifier dans le chat** ou envoyez `/edit-flow <name> <change>`. Indiquez ce qui doit changer et ce qui doit rester. Modifier un flux personnalisé remplace la version de l’équipe. Modifier un flux intégré crée un flux personnalisé sous un autre nom. Consultez la livraison pour connaître les valeurs effectives des options et les éventuelles règles d’étape supprimées.

Vous pouvez aussi modifier les options d’un flux sur sa page de détails. S’il suit des consignes enregistrées, vous pouvez les y modifier pour la prochaine exécution. Désactivez **Activé** pour retirer le flux du menu de l’équipe pour les nouvelles exécutions. Les tâches en file et en cours peuvent se terminer. Les deux commandes d’écriture de flux restent disponibles.

## Planifier un message

1. Dans le menu ⋯ de l’équipe, ouvrez **Événements planifiés** et utilisez le bouton plus pour **Ajouter un événement**. Sous **Votre consigne**, saisissez le message à envoyer, jusqu’à 16 KiB. Par exemple, `/docs-tidy Check the project documentation.`
2. Sélectionnez **Fréquence**. Choisissez **Une fois** pour une date et une heure locales futures, **Chaque jour** pour une heure chaque jour ou **Jours ouvrés** pour le lundi au vendredi. Avec **Toutes les quelques minutes**, réglez **Intervalle (minutes)** de 5 à 720. Utilisez **De** et **À** pour limiter l’exécution à une partie de la journée.
3. Vérifiez **Fuseau horaire**, réglé au départ sur celui de votre navigateur, puis enregistrez. La liste affiche la première ligne du message et la prochaine heure d’exécution. Créer l’événement autorise le message. À l’heure prévue, il apparaît dans la discussion sous votre nom, avec la mention **Planifié**. Chaque déclenchement utilise un tour complet du leader.

Les heures suivent le fuseau horaire choisi. Si un changement d’heure fait sauter une heure planifiée, l’événement utilise la prochaine heure valide. Si l’horloge répète cette heure, il utilise la première occurrence. Un événement à intervalle avec une plage horaire ignore les occurrences hors de cette plage.

Ouvrez l’événement pour modifier son message ou son horaire. L’enregistrement recalcule la prochaine exécution. Désactivez l’événement pour arrêter les futurs messages, puis réactivez-le quand vous voulez qu’il reprenne. Il reprend à partir de cette réactivation. Après une interruption du service de planification, seule la dernière occurrence manquée est envoyée. Cherchez un événement par son texte ou son numéro exact, par exemple `#6`. Utilisez **Terminé** pour retrouver un événement ponctuel terminé.

## En cas de problème

- Si la discussion ne reconnaît pas un flux, tapez `/` pour voir les noms activés pour cette équipe. Réactivez le flux dans **Flux de l’équipe** si nécessaire. Si un plan ne peut pas mettre son lot en file parce que `/write-review` est désactivé, activez-le avant de soumettre à nouveau le travail.
- Une équipe peut avoir 30 flux personnalisés. À la limite, supprimez un flux personnalisé devenu inutile avant d’en créer un autre. Si le nom est déjà utilisé, modifiez ce flux ou choisissez un nouveau nom. Si la modification indique qu’une règle d’étape supprimée est trop longue pour la livraison, raccourcissez ou déplacez la règle sur la page du flux et réessayez.
- Une équipe peut avoir jusqu’à 20 événements planifiés. À la limite, supprimez-en un avant d’en ajouter un autre. Si un événement ponctuel a déjà été exécuté, créez-en un nouveau pour le répéter. Utilisez une heure future et un intervalle dans la plage indiquée.
- Si un message planifié désigne un flux manquant ou désactivé ou un élément numéroté introuvable, cette occurrence est passée. Corrigez le message ou activez le flux avant la prochaine occurrence. Si un flux interactif planifié signale qu’un autre est déjà en cours, il attend un déclenchement ultérieur.
