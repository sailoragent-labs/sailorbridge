[← SailorBridge](README.md)

# Tâches

Une tâche est une exécution d’un flux. Chaque équipe dispose d’une file commune à ses machines. Vous pouvez donner une tâche à l’équipe dans la discussion, suivre son avancement par numéro et ouvrir sa livraison pour savoir ce qu’elle a produit et ce qui demande encore votre attention.

## Mettre le travail en file d’attente

Dans la discussion d’équipe, envoyez le nom d’un flux et une demande, par exemple `/agent Count the files at the top level of this project and report the count.` La tâche entre dans la file et une machine admissible la prend quand elle a de la place. Cette machine exécute la tâche dans sa propre copie de travail.

Si le **Leader** propose un travail dans la conversation, lisez la proposition et choisissez **Oui, Fais-le** pour l’ajouter à la file. Pour un plan en plusieurs tâches, lisez la liste avant de choisir **Tout mettre en attente**. **Modifier le plan** permet de décrire une modification. **Pas maintenant** garde le lot hors de la file. Après acceptation, chaque tâche reçoit son propre numéro. [Choisir un flux](flows-and-scheduled-events.md)

## Trouver une tâche et lire son état

Ouvrez le menu ⋯ dans la discussion d’équipe et choisissez **Liste des tâches**, ou choisissez **Voir le détail** sur la tâche dans la discussion. La liste affiche d’abord **Active**, puis mémorise votre dernier filtre dans ce navigateur. Choisissez **Toutes** pour inclure les tâches terminées. Recherchez par texte de la demande ou nom du flux, ou saisissez le numéro complet avec son dièse, comme `#6`, pour le trouver quels que soient les filtres.

| Ce que vous voyez | Ce que cela signifie |
| --- | --- |
| **Attente** | La tâche attend qu’une machine la prenne. La ligne en dessous indique pourquoi. Un numéro de tâche mentionné désigne un prérequis. |
| **Active** | Une machine a pris la tâche. Ouvrez-la pour voir l’étape actuelle et la machine. |
| **En attente du leader** ou **T’attend** | Le leader traite les questions auxquelles il peut répondre. S’il vous faut prendre une décision, choisissez **Répondre** et répondez dans la discussion. Le filtre **Vous** trouve les tâches qui vous attendent. |
| **Finie** | Le flux a livré son résultat. **Terminé, vérifications échouées** indique qu’une livraison existe avec une vérification en échec. Lisez la vérification avant d’utiliser le résultat. |
| **Inachevé** | Le flux s’est arrêté avant d’avoir tout livré. Voyez où il s’est arrêté et ce qui manque. Le travail déjà produit est conservé. |
| **Échec** | Une erreur a arrêté l’exécution. Ouvrez le rapport et **Note de la machine** pour en connaître la raison. |
| **Annulée** | La tâche a été arrêtée. Son entrée reste accessible dans la liste. |

**En pause** et **Quota** peuvent aussi expliquer pourquoi une tâche est inactive. Ouvrez **Pourquoi elle ne tourne pas** pour savoir ce qu’elle attend et quelle action vous pouvez éventuellement effectuer.

## Consulter la tâche, sa livraison et sa consommation

Sélectionnez la ligne numérotée. **Détails de la tâche** affiche l’état, **Exécution** et **Tours**. **Informations sur la tâche** indique la machine, qui a lancé la tâche et **Attente**. Développez **Étapes** pour voir l’étape exécutée, sa durée, le moteur et le modèle utilisés. Lorsqu’il est présent, **Problèmes de qualité** affiche les constats de l’auto-revue, de la revue indépendante et de son dernier tour.

À la fin de la tâche, ouvrez **Rapport de livraison**. Lisez **Modifications**, **Vérifications**, **Avis de relecture**, **Non contrôlé** et **À vous de décider**. Une vérification en échec s’affiche d’abord quand une tâche terminée en a une. Si la tâche a produit des commits, regardez où ils ont été enregistrés. Si la machine n’a pas pu les pousser, le rapport donne la branche locale, le commit, la raison et une commande à exécuter. Une tâche qui ne demande qu’un rapport peut livrer sa réponse sans commit.

Ouvrez **Utilisation** et développez **Par tour** pour voir les nombres de jetons et les modèles effectivement utilisés. La consommation est enregistrée par fournisseur, compte et modèle. Les totaux de la livraison couvrent la dernière prise en charge de la tâche par une machine. Le temps d’attente est enregistré séparément du temps d’exécution.

## Mettre en pause, modifier, arrêter ou reprendre une tâche

- Pour une tâche en file, choisissez **Mettre en pause** pour empêcher les machines de la prendre, puis **Reprendre** quand elle peut repartir. Choisissez **Démarrer maintenant** pour la placer en tête de file. Si une place est occupée, vous pouvez continuer d’attendre ou arrêter explicitement une tâche en cours pour la libérer.
- Pour modifier une tâche ouverte, choisissez **Aller au Chat** depuis la tâche. Son numéro est renseigné. Ajoutez vos nouvelles exigences et envoyez le message. Si le leader propose une modification, choisissez **Oui, Modifier**. Dans la file, la consigne révisée remplace l’ancienne. Si la tâche était en cours, la tentative s’arrête et la tâche revient en file avec le même numéro.
- Pour terminer une tâche, choisissez **Arrêter** et confirmez. Une tâche que vous arrêtez explicitement a besoin de votre instruction pour reprendre. Pour une tâche terminée avec un point de reprise enregistré et du travail utilisable, ouvrez ⋯ et choisissez **Continuer**. Elle garde le même numéro et utilise la copie de travail conservée ou la branche poussée. Si vous changez les exigences avant la reprise, elle repart du début.
- Choisissez **Refaire** pour mettre en file une nouvelle tâche avec le flux, la consigne, le dépôt et les options d’origine. Elle reçoit un nouveau numéro et vous pouvez toujours consulter l’ancienne. Utilisez cette commande si **Continuer** est indisponible. **Supprimer** supprime définitivement l’enregistrement d’une tâche terminée après confirmation.

## En cas de problème

- Si la distribution est suspendue pour toute l’équipe, choisissez **Reprendre la distribution** pour permettre aux machines de prendre de nouvelles tâches. Si l’équipe ou le compte a atteint sa limite de simultanéité, la tâche démarre quand une place se libère. [Réglages de distribution de l’équipe](teams.md)
- Si une tâche attend votre réponse, vous pouvez répondre même après les cinq premières minutes. Au bout de cinq minutes, la machine libère la place. Après votre réponse, la même machine reprend dès qu’elle est libre.
- Si une tâche a besoin d’un rédacteur ou d’un relecteur, choisissez **Aller aux comptes**. Une seule machine doit disposer des comptes pour l’ensemble de la tâche. Si toutes les machines candidates ont refusé, la tâche échoue et ses notes donnent leurs raisons. Si l’attente est due au quota ou à la cadence, vérifiez l’estimation. Le travail reprend quand le quota ou la capacité le permet. [Comptes des moteurs et cadence](engine-accounts-and-pacing.md)
- Si une machine perd la connexion, elle peut reprendre lorsqu’elle se reconnecte. Après 30 minutes sans renouveler sa prise en charge, une autre machine de l’équipe peut reprendre la tâche depuis le début. Trois pertes de connexion pour la même tâche la terminent avec **Échec**. Vérifiez la machine avant de poursuivre ou de relancer. [Vérifier la machine](machines.md)
- Après une défaillance récupérable du système, une tâche peut reprendre automatiquement jusqu’à 10 fois au total. Si elle reste arrêtée, lisez son dernier rapport, corrigez la cause et utilisez **Continuer** si cette commande est proposée.
