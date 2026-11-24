[← SailorBridge](README.md)

# Mémoire d’équipe

La mémoire d’équipe conserve les décisions, conventions et corrections que votre **Leader** et les exécutants peuvent réutiliser dans de futures tâches. Chaque entrée a un titre, un contenu, une source et un numéro comme `#6`. Elle appartient à une seule équipe. Les autres équipes et les amis ne peuvent pas la consulter.

## Enregistrer une information à conserver

Dans la discussion d’équipe, dites quoi retenir et dans quel cas l’utiliser. Par exemple « Retiens que les exemples d’installation vont dans le guide de configuration. Utilise-le quand tu modifies une commande d’installation. » Le **Leader** vous indique ce qu’il a enregistré. Dans la discussion d’équipe, ouvrez **Autres actions** et choisissez **Mémoire d’équipe** pour voir l’entrée. Ouvrez son titre pour lire le texte complet et savoir qui l’a modifié en dernier.

## Retrouver une entrée et l’utiliser dans la discussion

Ouvrez **Rechercher** dans **Mémoire d’équipe**. Saisissez des mots du titre ou du contenu. Tous doivent correspondre pour obtenir un résultat textuel. La première page peut aussi afficher jusqu’à trois entrées de sens proche. Les entrées épinglées s’affichent en tête de la liste ordinaire.

Si vous connaissez le numéro, recherchez `#6` pour obtenir uniquement l’entrée 6. Une recherche sur `6` trouve aussi des correspondances dans le texte. Ouvrez l’entrée et choisissez **Aller au Chat**. Le champ de saisie contient maintenant `/memory #6`. Ajoutez une question ou une correction et envoyez-la.

## Modifier, épingler, verrouiller ou supprimer une entrée

- Ouvrez l’entrée, modifiez **Contenu** et choisissez **Enregistrer**. **History** affiche les 10 dernières versions. Consultez **Observed** et **Expires** pour les faits susceptibles de changer. Une entrée portant la mention **Expired** reste lisible. Vérifiez que son contenu s’applique encore.
- Activez **Épinglée** pour ajouter une consigne aux informations transmises au **Leader** et aux exécutants. L’entrée affiche l’espace occupé par les éléments épinglés de l’équipe. Leurs titres et contenus peuvent occuper jusqu’à 8 KiB au total.
- Activez **Verrouillée** si vous voulez être la seule personne à pouvoir modifier ou supprimer l’entrée. Le seul fait de l’épingler laisse les agents la modifier. Vous pouvez modifier une entrée verrouillée sur le Web.
- Choisissez **Supprimer** et confirmez pour supprimer définitivement une entrée. Son numéro ne sera pas réutilisé.

## Faire le tri dans les entrées de l’équipe

Envoyez `/memory-tidy` dans la discussion d’équipe. La tâche vérifie les entrées, marque celles à conserver, fusionne les entrées apparentées et supprime celles qui ne serviront plus. Ouvrez son **Rapport de livraison** pour savoir ce qui a été fait et ce qui attend votre décision. Les entrées verrouillées restent en place si la tâche propose de les supprimer ou de les fusionner.

Lorsqu’il y a des entrées à vérifier, le tri automatique s’exécute au plus une fois par équipe sur une période glissante de 24 heures. Pour le lancer uniquement à la demande ou selon un horaire, ouvrez **Flux de l’équipe**, sélectionnez `memory-tidy` et désactivez **Rangement automatique**.

## En cas de problème

- Un épinglage qui dépasserait 8 KiB est refusé. Désépinglez une autre entrée ou raccourcissez le texte épinglé, puis réessayez.
- Si quelqu’un a modifié l’entrée pendant que vous y travailliez, le dernier contenu s’affiche. Lisez-le avant d’appliquer à nouveau votre correction.
- Si deux mises à jour portent le même titre, une correction du même auteur peut s’appliquer directement. Sinon, un niveau de confirmation supérieur ou, à niveau égal, une observation plus récente peut départager les mises à jour. Si une décision est nécessaire, l’entrée affiche **Conflit non résolu** et conserve le texte actuel. Ouvrez-la, vérifiez le fait et enregistrez la formulation correcte. Une entrée verrouillée nécessite votre décision.
- Si le **Leader** signale qu’une entrée n’a pas été enregistrée, répétez ce qu’il doit retenir. Si un agent a essuyé un refus parce que l’entrée est verrouillée, modifiez-la vous-même dans **Mémoire d’équipe**.
