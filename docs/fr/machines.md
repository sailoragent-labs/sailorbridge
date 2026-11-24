[← SailorBridge](README.md)

# Machines

Une machine est un ordinateur que vous connectez à votre compte pour y faire tourner le leader d’une équipe ou y exécuter des tâches. Installez `sail` sur chaque machine et approuvez-la dans le navigateur. Son service en arrière-plan maintient la connexion après la fermeture du terminal.

## Installer et associer une machine

1. Utilisez une machine que vous contrôlez sous Linux x64 ou macOS sur arm64 ou x64. Installez Git. Pour les discussions et les tâches, installez Claude Code ou Codex et connectez-vous sur cette machine avec votre propre compte du moteur. Vous pouvez terminer l’association avant de vous connecter au moteur.
2. Dans l’application, ouvrez **Machines**, puis **Associer une nouvelle machine**. Copiez la commande d’installation affichée dans un terminal sur la machine à connecter. Vous pouvez l’exécuter depuis n’importe quel répertoire. Elle installe `sail`, démarre l’association et affiche un code à huit caractères valable 10 minutes.
3. Dans le navigateur, saisissez ce code dans **Code d'appariement** et choisissez **Associer**. Comparez le nom de la machine et le **Code de clé** à ceux du terminal. Lors de la première association, lisez l’avis avant de l’accepter. Les agents peuvent lire, modifier ou supprimer des fichiers, utiliser des identifiants et se connecter au réseau avec les droits de l’utilisateur du système qui exécute `sail`. Utilisez une machine ou un conteneur dédié si vous avez besoin d’isolation.
4. Choisissez **Approuver la machine**. Laissez la machine connectée pendant qu’elle récupère ses identifiants et démarre le service. Quand **Machines** affiche **En ligne** et que le terminal confirme la connexion, vous pouvez choisir **Configurer les Comptes** ou **Créer une Équipe**. [Créer une équipe](teams.md)

## Vérifier une connexion ou associer d’autres machines

Ouvrez une machine dans **Machines** pour voir son nom, sa plateforme et les champs **Dernière connexion**, **Associée le** et **Version du client**. Vous pouvez modifier son nom pour mieux distinguer les machines. Sur la machine même, exécutez `sail host status` pour vérifier l’association, la connexion et l’état du service, et trouver le journal local.

Pour utiliser un autre ordinateur, ouvrez à nouveau **Associer une nouvelle machine** et exécutez la commande affichée sur cet ordinateur. Une fois qu’il est en ligne, ajoutez-le à l’équipe et définissez-y son dossier de projet. Une machine peut servir plusieurs équipes. Chaque tâche s’exécute sur une machine admissible de son équipe. [Gérer les machines d’une équipe](teams.md)

## Mettre à jour ou réparer une installation

Les mises à jour automatiques sont activées par défaut. Après avoir vérifié une mise à jour, le service redémarre et reprend le travail local. Les étapes terminées sont conservées. Une étape locale interrompue peut être relancée. Pour une mise à jour manuelle, exécutez `sail upgrade` sur la machine. La commande indique si elle a installé une mise à jour, si la version était déjà à jour ou si une erreur s’est produite. Vérifiez la version installée avec `sail --version`.

Pour rétablir le service, exécutez `sail login`. À la même adresse, la commande réinstalle le service et le redémarre avec ses identifiants existants. Si ceux-ci sont refusés et que la machine est encore enregistrée, elle lance une association de réparation. Le navigateur affiche **Associer à nouveau une machine existante** et identifie la machine à remplacer. Vérifiez les détails et approuvez le nouveau code. La machine garde ses équipes. Pour la récupération du mot de passe, la date d’association repart de la réception des nouveaux identifiants.

## Retirer une machine ou désinstaller SailorBridge

Pour cesser d’utiliser une machine sur votre compte, ouvrez le menu de sa ligne dans **Machines**, choisissez **Supprimer** et confirmez. Ses identifiants sont révoqués. Elle quitte ses équipes et cesse de travailler à la réception de l’avis, immédiatement si elle est connectée ou à sa prochaine connexion. Ses copies de travail locales sont conservées. Pour l’utiliser de nouveau, exécutez-y `sail login`, approuvez la nouvelle association et ajoutez-la aux équipes qui en ont besoin.

Pour retirer l’installation de l’ordinateur, sauvegardez d’abord les travaux dont vous avez besoin dans ses copies de travail SailorBridge. Exécutez `sail uninstall` sur cette machine. La commande arrête le service et supprime `sail`, la définition du service, l’entrée ajoutée au chemin du shell par l’installateur et tout le répertoire `~/.sailorbridge/`. Cela comprend les identifiants, les enregistrements de comptes, les journaux, l’historique local des discussions, les copies de travail et la copie de sauvegarde de `sail`. Vos répertoires de projets et de connexion aux moteurs sont conservés. Pour réinstaller, utilisez la commande de **Associer une nouvelle machine**.

## En cas de problème

- Si l’association signale que Git manque, installez Git et exécutez `sail login` pour poursuivre. Si vous devez vous connecter au moteur, exécutez séparément `claude login` ou `codex login` avant de commencer une discussion ou une tâche.
- Si le code expire, exécutez `sail login` pour en obtenir un nouveau. Si le nom de la machine ou le **Code de clé** diffère, choisissez **Annuler l'association** et vérifiez le terminal de la machine voulue. Si l’approbation a abouti mais que la machine ne s’est pas connectée après 10 minutes, exécutez `sail host status`, puis `sail login` pour la reconnecter.
- Si une machine se déconnecte de façon inattendue, vérifiez le réseau et le service avec `sail host status`. Le délai par défaut pour passer hors ligne est de 90 secondes. La notification ne s’affiche qu’après 10 minutes hors ligne et disparaît au retour de la machine.
- Si une mise à jour échoue, ouvrez la machine pour lire la raison et exécutez la commande de réparation affichée avec le compte utilisateur qui a installé `sail`. Si la sauvegarde locale est inutilisable, utilisez la commande d’installation de la page d’association.
- Si la machine signale un changement d’identité du serveur, elle refuse la connexion. Exécutez `sail host status --trust` sur la machine pour examiner l’empreinte enregistrée. Si le changement était prévu, exécutez `sail login`, vérifiez la nouvelle empreinte dans le terminal et approuvez une nouvelle association.
- Si `sail login` affiche `origin_mismatch`, suivez la procédure de désinstallation ci-dessus avant de changer d’adresse. Copiez ensuite la commande d’installation de la page **Machines** de l’application voulue. Des identifiants locaux d’association illisibles exigent aussi une désinstallation suivie d’une nouvelle association.
- Si `sail uninstall` indique que le service n’a pas pu confirmer le retrait, les fichiers locaux ont été supprimés. Ouvrez **Machines** et retirez-y l’entrée.
