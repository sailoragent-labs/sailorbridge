[English](../troubleshooting.md) · [简体中文](../zh-CN/troubleshooting.md) · [日本語](../ja/troubleshooting.md) · [한국어](../ko/troubleshooting.md) · [Deutsch](../de/troubleshooting.md) · [Français](troubleshooting.md) · [Español](../es/troubleshooting.md) · [Português (BR)](../pt-BR/troubleshooting.md) · [Bahasa Indonesia](../id/troubleshooting.md) · [हिन्दी](../hi/troubleshooting.md)

[← SailorBridge](README.md)

# Dépannage

Commencez là où le travail s’est arrêté. Pour une connexion ou un paiement, lisez le message sur la page concernée. Pour un problème de machine, consultez son terminal. Pour une tâche, ouvrez **Liste des tâches**, sélectionnez-la et lisez **Pourquoi elle ne tourne pas**. Vous saurez si la tâche nécessite une action de votre part ou si elle reprendra seule.

## Retrouver l’accès à votre compte

| Ce que vous voyez | Marche à suivre |
| --- | --- |
| Votre ID du capitaine est pris ou les inscriptions sont complètes pour aujourd’hui | Essayez un autre ID disponible. Si la limite quotidienne d’inscriptions gratuites est atteinte, revenez demain. Pour un ID payant, utilisez le **Lien d'activation** d’origine pour terminer l’inscription. |
| **Confirmez que c’est vous** après la saisie du mot de passe | Utilisez votre application d’authentification, exécutez `sail confirm` sur une machine associée et saisissez le code affiché, ou confirmez le nombre affiché dans un navigateur reconnu si l’option est proposée. Utilisez la demande de connexion la plus récente. Si elle expire, reconnectez-vous. |
| Trop d’échecs de connexion ou code d’authentification réutilisé | Après 5 échecs en 15 minutes, le verrouillage par défaut dure 15 minutes. Attendez le délai affiché. Si un code d’authentification a déjà servi, attendez le suivant. |
| Vous avez oublié votre mot de passe ou le code de récupération a expiré | Exécutez `sail recover` dans un terminal sur une machine associée. Choisissez **Mot de passe oublié ?** et saisissez l’ID du capitaine et le code à 8 caractères affichés. Le code dure 10 minutes et ne sert qu’une fois. Un nouveau code de la même machine remplace l’ancien. Si les identifiants de la machine sont refusés, essayez une autre machine associée. Sans machine associée utilisable, inscrivez-vous avec un nouvel ID. |
| **Récupération du compte en attente** | Une machine associée depuis moins de 72 heures impose une attente de 72 heures, y compris après une réparation ayant remplacé ses identifiants. Pour une association plus ancienne, si la validation en deux étapes est active depuis au moins 72 heures, il faut le code d’authentification pour une récupération immédiate. Sans ce code, envoyez la demande avec un délai de 72 heures. Attendez l’heure affichée. Si vous n’avez pas demandé la récupération, choisissez **Annuler cette récupération** sur un appareil connecté. |

## Faire fonctionner une machine ou une équipe

- Si l’installation s’arrête faute de Git, installez Git et relancez la commande de **Associer une nouvelle machine**. Si Claude Code ou Codex est déconnecté, l’association peut se terminer. Exécutez `claude login` ou `codex login` sur la machine avant de donner du travail à l’équipe.
- Si le code d’appariement expire, exécutez `sail login` pour en obtenir un nouveau. Saisissez-le dans **Associer une nouvelle machine**, choisissez **Associer**, puis vérifiez le nom et les détails de la machine affichée. Lors de la première association, lisez et acceptez l’avis, puis choisissez **Approuver la machine** et attendez qu’elle se connecte.
- Si la machine ne s’est pas connectée au bout de 10 minutes, exécutez `sail host status`. La commande affiche l’état du service et le chemin du journal. À la même adresse, exécutez `sail login` pour rétablir le service. Avec `origin_mismatch`, si vous comptez changer d’adresse, `sail uninstall` supprime les données locales de SailorBridge, dont les copies de travail des tâches. Exécutez ensuite la commande d’installation de la page **Machines** de l’application voulue et associez la machine de nouveau.
- Si une mise à jour échoue, ouvrez la machine dans **Machines** pour consulter la raison et suivre la commande de réparation affichée. Si le téléchargement a échoué, réessayez plus tard avec `sail upgrade`. Si l’écriture a échoué, vérifiez l’espace disque et utilisez le compte qui a installé `sail`.
- Si la création d’équipe demande une machine, associez-en une et attendez **En ligne**. Si vous ne pouvez pas retirer la dernière machine de l’équipe, utilisez d’abord **Ajouter une machine**. Si le répertoire de l’équipe ne peut pas être créé, choisissez **Modifier le dossier dans les réglages de l’équipe**. Utilisez un chemin absolu sur la machine où l’erreur s’est produite. Un fichier à cet emplacement, des droits d’écriture manquants ou un disque en lecture seule peuvent empêcher la création. [Machines](machines.md) · [Équipes](teams.md)

## Obtenir une réponse dans la discussion

- Si la machine du **Leader** est hors ligne, la discussion d’équipe conserve votre message et le transmet quand la machine se reconnecte. Si l’équipe n’a pas de machine utilisable, ajoutez-en une et renvoyez le message.
- Si le moteur demande une connexion, connectez-vous sur la machine indiquée. Si tous les comptes utilisables par le **Leader** ont épuisé leur quota, renvoyez le message après la réinitialisation. Si un modèle est refusé, suivez les instructions de mise à jour du moteur et réessayez, ou choisissez un compte et un modèle disponibles. [Comptes des moteurs et cadence](engine-accounts-and-pacing.md)
- Si votre message a répondu à une question au lieu d’atteindre le **Leader**, répondez à la question ouverte ou choisissez **Arrêter** sur sa carte. Envoyez ensuite le message. Si une carte de confirmation a été remplacée ou a déjà reçu une réponse, consultez la dernière carte ou la tâche avant d’agir.
- Si un fichier est refusé, utilisez la discussion d’équipe et envoyez au plus 4 pièces jointes par message, de 5 MiB au maximum chacune. Les formats pris en charge sont PNG, JPEG, WebP, PDF, texte brut et Markdown. Sélectionnez de nouveau une pièce jointe indisponible. Un fichier téléversé mais non envoyé expire après 24 heures. À la limite de 1 GiB par compte, attendez de récupérer de la place quand les fichiers envoyés expirent après 30 jours. Si un message est trop volumineux, divisez-le en messages de 64 KiB au plus.
- Dans une session d’agents, si le compte doit se reconnecter ou manque de quota, réglez d’abord ce problème, puis choisissez **Reprendre**. Si une session entre équipes atteint sa limite de tours, le destinataire peut l’étendre de 10 ou 20 tours ou choisir **Tours illimités**. L’auteur de la demande attend le destinataire. [Discussion](chat.md)

## Comprendre pourquoi une tâche attend

Ouvrez la tâche dans **Liste des tâches**. Lisez **Pourquoi elle ne tourne pas** avant de décider de relancer quoi que ce soit.

| Ce qui retient la tâche | Marche à suivre |
| --- | --- |
| La distribution ou cette tâche est en pause | Utilisez **Reprendre la distribution** pour l’équipe ou **Reprendre** pour la tâche seule. |
| Les machines sont occupées, l’équipe a atteint sa limite de tâches ou votre offre sa limite d’agents | Le travail démarre quand une place se libère. Consultez **Tâches simultanées** pour l’équipe ou **Limite de simultanéité** dans **Abonnement** pour votre compte. |
| La tâche nécessite un rédacteur et un relecteur | Choisissez **Aller aux comptes**. Vérifiez qu’une machine de l’équipe a les comptes requis activés pour les deux étapes. Un rédacteur et un relecteur sur deux machines différentes ne peuvent pas exécuter la même tâche ensemble. |
| La machine a atteint le seuil de cadence ou épuisé le quota | Attendez le délai estimé affiché. Pour une attente due à la cadence, **Passer Sans Limite** modifie le réglage pour toutes vos équipes après confirmation. Si le quota est épuisé, la tâche vérifie de nouveau et reprend sur la même machine quand le quota revient. |
| La tâche attend une réponse ou un prérequis | Choisissez **Répondre** si la question vous est destinée. Après 5 minutes d’attente, la tâche libère sa place. Une fois la réponse donnée, elle reprend quand sa machine d’origine est libre. Pour un prérequis, ouvrez la tâche dont le numéro est affiché et consultez son résultat. |
| Une machine a refusé la tâche ou a cessé de se signaler | Lisez la raison sous la tâche. Une autre machine admissible peut prendre une tâche refusée. Si toutes les candidates ont refusé, ouvrez **Note de la machine** pour connaître leurs raisons. Si la machine qui travaillait a perdu sa connexion, elle peut reprendre si elle revient la première. Après 30 minutes sans renouvellement de la prise en charge, une autre machine peut repartir du début. |
| **Inachevé** ou **Échec** | Ouvrez **Rapport de livraison** pour voir la dernière étape, la raison et le travail conservé. Corrigez le problème signalé. Utilisez **Continuer** si l’option est proposée pour reprendre la même tâche sur le travail conservé, ou **Refaire** pour recommencer. Si l’envoi a échoué, le rapport donne la branche, le commit et la commande d’envoi pour le travail conservé localement. |

## Corriger une commande, un horaire ou une entrée de mémoire

- Si le terminal affiche « Exécutez cette commande dans une tâche ou une session du chef d’équipe. » (`local_team_context_missing`), la commande nécessite une session active, même dans le répertoire de l’équipe. Demandez au **Leader** dans la discussion d’équipe ou ouvrez **Liste des tâches**, **Événements planifiés** ou **Mémoire d’équipe** pour travailler sur un élément existant. [Commandes pour les éléments numérotés de l’équipe](commands.md#utiliser-les-éléments-numérotés-de-léquipe)
- Si une commande commençant par une barre oblique est inconnue, tapez `/` pour voir les flux activés. Si une référence numérotée manque, vérifiez l’équipe et le type d’élément, puis ajoutez `#` devant son numéro dans la discussion. Si `sail exec` signale que la cible est hors ligne, la commande n’a pas démarré. Si le résultat a été perdu *après* le démarrage, vérifiez la cible avant de réessayer. [Commandes](commands.md)
- Si un événement planifié est refusé, choisissez une heure future pour un événement ponctuel ou un intervalle de 5 à 720 minutes pour un événement récurrent. Une équipe peut avoir jusqu’à 20 événements. Supprimez un événement inutile pour faire de la place. Recréez un événement ponctuel terminé pour le relancer. Si un événement fait référence à un flux désactivé ou à un numéro manquant, corrigez le message pour la prochaine exécution. [Flux et événements planifiés](flows-and-scheduled-events.md)
- Si une modification de la mémoire est refusée, ouvrez **Mémoire d’équipe**. Vous pouvez y modifier une entrée verrouillée. Si quelqu’un l’a modifiée avant vous, lisez le contenu le plus récent avant d’enregistrer. Si tout l’espace d’épinglage est utilisé, désépinglez ou raccourcissez une entrée avant d’en épingler une autre. [Mémoire d’équipe](team-memory.md)

## Vérifier un paiement qui n’a pas abouti

Si le paiement est en attente, revenez à l’achat d’origine et vérifiez son état avant de payer de nouveau. Pour **Paiement échoué** sur un abonnement, **Modifier le Moyen de Paiement et Régler le Solde** ouvre la page de paiement du montant restant. [Offres et facturation](plans-and-billing.md)

## En cas de problème

Si le problème persiste, notez les étapes, le message exact, le résultat attendu et l’endroit où il s’est produit. Indiquez la version, le système d’exploitation de la machine et le moteur si vous les connaissez. Pour un problème de compte ou de paiement, utilisez le contact privé indiqué dans le README. Pour un problème de sécurité, utilisez son lien privé. Gardez les identifiants, codes d’association, données de paiement et code source privé hors des signalements publics. [Signaler un problème](README.md#signaler-un-problème)
