[← SailorBridge](README.md)

# Équipes

Une équipe donne à un projet sa propre discussion avec le **Leader**, sa file de tâches, sa mémoire d’équipe et une ou plusieurs machines. Vous pouvez posséder plusieurs équipes et utiliser une machine dans plusieurs d’entre elles. Vous seul pouvez consulter et modifier les paramètres de votre équipe.

## Créer une équipe pour votre projet

1. Associez la machine qui fera tourner le leader. Quand elle affiche **En ligne**, choisissez **Créer une Équipe** sur la page d’association. Vous pouvez aussi ouvrir **Équipes** et choisir **Créer une équipe**. [Associer une machine](machines.md)
2. Saisissez un **Nom de l’équipe** et sélectionnez la machine. Vous pouvez choisir un **Avatar** ainsi qu’un compte, un modèle et un niveau d’effort pour le leader parmi les options de cette machine, ou garder les valeurs par défaut.
3. Sous **Répertoire du projet**, saisissez le chemin absolu sur la machine sélectionnée, en commençant par `/`. Si vous travaillez déjà dans un dépôt, utilisez son répertoire local. Pour travailler dans un dépôt distant existant, clonez-le d’abord sur cette machine et configurez-y ses identifiants Git. SailorBridge détecte la branche principale du dépôt.
4. Choisissez une **Destination**, puis **Créer une équipe**. L’équipe affiche maintenant la machine. Ouvrez la **Discussion** pour parler au leader. [Utiliser la discussion d’équipe](chat.md)

À la première utilisation du chemin, l’équipe ouvre le dossier existant ou le crée. Pour un simple dossier contenant des fichiers, elle initialise Git et prend un instantané initial. Si le dossier contient directement plusieurs dépôts Git, dites au leader duquel il s’agit. Chaque tâche travaille dans un seul dépôt. Le travail qui concerne plusieurs dépôts est réparti en tâches séparées.

## Choisir la destination des modifications

Ouvrez votre équipe dans **Équipes** pour accéder à **Détails de l'équipe**. Modifiez-y **Répertoire du projet** ou **Destination**. Les modifications s’appliquent à partir de la prochaine tâche prise par une machine.

| Destination | Où trouver les commits d’une tâche |
| --- | --- |
| **Auto-fusion** (par défaut) | La machine tente de pousser vers la branche principale distante, puis avance sa branche principale locale en fast-forward. Consultez la livraison si la branche principale a avancé ou que le dépôt distant exige une revue. Si une branche de tâche est indiquée, fusionnez-la sur le dépôt distant. |
| **Branche** | Chaque tâche pousse sa propre branche `sb/<job>`, que vous pouvez relire et fusionner. Les autres tâches partent de la branche principale du projet. |

Chaque machine utilise le dépôt distant et les identifiants Git propres au dépôt. Avant de démarrer une tâche, elle récupère la branche principale distante et avance sa copie locale en fast-forward si possible. Si un envoi échoue, ouvrez le **Rapport de livraison** de la tâche pour connaître la raison, la branche locale, le commit et la commande d’envoi. [Trouver la livraison d’une tâche](jobs.md)

## Ajouter, déplacer ou retirer une machine

Dans **Détails de l'équipe**, ouvrez **Liste des machines** et utilisez le bouton plus pour **Ajouter une machine**. Sélectionnez une machine associée, puis choisissez **Identique au dossier de l’équipe** ou saisissez son propre chemin absolu dans **Dossier du projet**. Vous pourrez modifier ce chemin par la suite. Une machine admissible qui a de la place peut maintenant prendre une tâche dans la même file.

Pour retirer une machine de l’équipe, sélectionnez-la et confirmez **Retirer de l’équipe**. Elle cesse de prendre de nouvelles tâches dans cette file. Si vous retirez de l’équipe la machine marquée **Le leader s’exécute ici** ou cessez de l’utiliser, la machine restante qui a rejoint l’équipe en premier reprend le rôle de leader. Vous ne pouvez pas retirer la dernière machine de l’équipe. Ajoutez d’abord sa remplaçante.

## Régler la prise en charge des tâches

Revenez dans **Détails de l'équipe** pour modifier la façon dont l’équipe travaille.

- Dans **Paramètres des tâches**, **Distribution** contrôle les nouvelles tâches. Choisissez **En pause** pour retenir les tâches en file pendant que les tâches actives se poursuivent. Choisissez **Normale** pour permettre aux machines de reprendre les tâches en file d’attente.
- **Tâches simultanées** est réglé par défaut sur **Illimité**, ce qui applique la limite de simultanéité du compte. Choisissez **Fixer un nombre** pour limiter les tâches actives de cette équipe. Une limite abaissée prend effet au fur et à mesure que les tâches actives se terminent.
- Sous **Modèle du leader**, sélectionnez le compte, puis le modèle et, s’il est proposé, le niveau d’effort. Les comptes sont affichés avec leur machine. Sélectionner un compte sur une autre machine de l’équipe y déplace le leader pour le prochain message. Il reprend le même résumé de conversation et la même mémoire d’équipe. Les tâches en cours restent sur leur machine.
- Pour les exécutants, choisissez un modèle et, s’il est proposé, un effort préférés pour chaque niveau de difficulté et fournisseur. **Rétablir la valeur par défaut** rétablit la valeur par défaut de l’équipe pour ce choix. Dans **Liste des comptes**, vous pouvez réserver un compte à la rédaction, à la revue ou au leader. [Comptes des moteurs et cadence](engine-accounts-and-pacing.md)

## Dissoudre une équipe

Ouvrez **Détails de l'équipe**, choisissez **Dissoudre l’équipe**, vérifiez combien de sessions d’agents prendront fin, puis saisissez le nom de l’équipe pour confirmer. La dissolution est définitive. Elle annule les tâches ouvertes, supprime les événements planifiés et retire l’équipe de votre liste et des accès à la discussion. Ses demandes de session d’agents en attente et ses sessions actives prennent fin. Chaque participant conserve son historique de session. Les machines restent associées à votre compte.

## En cas de problème

- Si aucune machine n’est disponible, choisissez **Associer une machine** lors de la création d’une équipe, ou **Associer une nouvelle machine** lors de l’ajout d’une machine. Si la machine a été retirée, associez-la de nouveau avant de l’ajouter.
- Si une tâche ou une discussion indique que le répertoire ne peut pas être créé, vérifiez le chemin sur la machine qui a tenté de l’utiliser. Un fichier à cet emplacement, l’absence de droits d’écriture ou un disque en lecture seule peuvent empêcher la création. Choisissez **Modifier le dossier dans les réglages de l’équipe** et saisissez un répertoire accessible en écriture sur cette machine.
- Si le compte ou le modèle du leader n’est plus disponible pendant la création, faites un nouveau choix dans la liste actualisée. Si des tâches restent en file après la création, lisez **Pourquoi elle ne tourne pas** dans les détails de la tâche pour savoir si la distribution, une limite ou un compte bloque son exécution.
