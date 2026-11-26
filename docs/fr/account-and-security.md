[← SailorBridge](README.md)

# Compte et sécurité

Votre **ID du capitaine** numérique est votre identifiant de connexion. Il reste associé à votre compte quand vous changez de pseudo, de mot de passe ou de navigateur. Associez une machine que vous contrôlez tant que vous pouvez vous connecter. Vous en aurez besoin si vous oubliez votre mot de passe.

## Créer votre compte

1. Ouvrez l’[application](https://app.sailorbridge.com) et choisissez **S'inscrire**. Saisissez le numéro de votre choix, de 3 à 11 chiffres. Si **Déjà réclamé** s’affiche, modifiez le numéro pour en vérifier un autre.
2. Vérifiez ce que la page affiche pour ce numéro. Les ID ordinaires de 6 à 8 chiffres et tous les ID de 9 à 11 chiffres sont gratuits. Les ID plus courts et les suites particulières de 8 chiffres maximum font l’objet d’un paiement unique. Pour un numéro payant, enregistrez le **Lien d'activation** lors du paiement afin de pouvoir terminer l’inscription sur un autre appareil. [Tarifs](https://www.sailorbridge.com/#pricing)
3. Définissez et confirmez votre mot de passe. Vous pouvez choisir un avatar prédéfini ou conserver votre initiale. Confirmez votre âge, acceptez les **Conditions d’utilisation**, puis choisissez **S'inscrire**. L’application vous connecte. [Associer votre première machine](machines.md)

## Se connecter et confirmer un nouveau navigateur

Saisissez votre **ID du capitaine**, choisissez **Suivant**, puis saisissez votre **Mot de passe** et choisissez **Connectez-vous**. Si vous avez associé une machine, SailorBridge demande automatiquement une confirmation sur un nouveau navigateur. Lorsque la validation en deux étapes est désactivée, le mot de passe suffit sur un navigateur reconnu. Sans machine associée ni validation en deux étapes, il suffit aussi sur un nouveau navigateur. La **Validation en deux étapes** est facultative. Une fois activée, elle exige une confirmation à chaque connexion, même sur un navigateur reconnu.

Dans **Confirmez que c’est vous**, utilisez l’une des méthodes proposées.

- Pour **Code de l’authentificateur**, saisissez le code actuel de votre application d’authentification.
- Pour **Code de la machine**, exécutez `sail confirm` dans un terminal sur une machine associée. Saisissez le code à huit caractères sur la page de connexion.
- Pour la **Confirmation par navigateur**, ouvrez un autre navigateur reconnu sur lequel vous êtes déjà connecté. Dans la demande de confirmation, touchez le nombre à deux chiffres affiché sur la page de connexion. Approuvez uniquement une connexion que vous avez lancée. Sinon, choisissez **Ce n’était pas moi**.

## Configurer votre profil et protéger vos connexions

Ouvrez **Moi**. Vous pouvez définir un **Surnom** et choisir un **Avatar** dans la galerie. **Langue** règle la langue d’affichage et celle des réponses à partir du prochain échange ou de la prochaine tâche. Dans **Style de réponse**, choisissez **Débutant** pour obtenir davantage d’explications ou **Expert** pour des réponses plus courtes.

Ouvrez **Sécurité**, puis **Validation en deux étapes**. Choisissez **Activer**, vérifiez votre mot de passe et scannez le code QR avec votre application d’authentification. Saisissez le code actuel et choisissez **Confirmer l’activation**. Pour désactiver cette protection, choisissez **Désactiver la validation en deux étapes**, puis fournissez votre mot de passe et un nouveau code.

Pour changer de mot de passe, renseignez **Mot de passe actuel**, **Nouveau mot de passe** et **Confirmer le nouveau mot de passe** dans **Sécurité**. Saisissez un code d’authentification si la validation en deux étapes est activée. Après la modification, ce navigateur est connecté et les autres sessions sont déconnectées.

<a name="vérifier-lactivité-et-les-clés-des-appareils"></a>

## Vérifier l’activité et les appareils

Ouvrez **Moi**, puis **Sécurité** et **Événements de sécurité récents**. La liste couvre les 90 derniers jours. Après une connexion réussie dans un nouveau navigateur, l’application vous demande si elle vient de vous. Choisissez **C’était moi** ou **Ce n’était pas moi**. Chaque navigateur conserve ses propres confirmations. Les échecs de connexion figurent dans la liste sans demande de confirmation.

Si vous voyez une connexion que vous n’avez pas effectuée, changez votre mot de passe. **Déconnecter les autres sessions** déconnecte vos autres navigateurs et applications tout en gardant cette session ouverte. Pour déconnecter une seule machine, retirez-la sous **Machines**. **Révoquer toutes les machines** déconnecte toutes les machines associées. Vous devrez les associer à nouveau pour qu’elles puissent travailler ou fournir un code de récupération. Vous pouvez aussi supprimer un événement de sécurité après confirmation. Les autres navigateurs continuent de recevoir leurs propres alertes jusqu’à ce que vous y confirmiez l’événement.

Dans **Sécurité**, ouvrez **Appareils** pour voir vos applications et vos machines associées. Sélectionnez un appareil, puis choisissez **Retirer** pour lui retirer la possibilité d’autoriser de nouvelles actions. L’application sera déconnectée ou la machine dissociée. Si l’appareil a disparu, choisissez **Perdu ou volé**. SailorBridge cessera aussi d’accepter les contenus déjà autorisés par cet appareil.

## Récupérer un mot de passe oublié

1. Dans un terminal sur une machine associée, exécutez `sail recover`. La commande affiche votre ID du capitaine et un code de récupération à huit caractères, à usage unique et valable 10 minutes. Un nouveau code sur la même machine remplace le premier.
2. Sur la page de connexion, choisissez **Mot de passe oublié ?**. Saisissez l’ID et le **Code de récupération** du terminal. Vérifiez le nom de la machine et sa date d’association avant de saisir votre nouveau mot de passe.
3. Suivez la procédure de récupération indiquée. L’ancienneté de la machine se calcule depuis sa dernière association ou réparation des identifiants.

| Machine utilisée pour récupérer le compte | Validation en deux étapes | Ce qui se passe |
| --- | --- | --- |
| Associée depuis moins de 72 heures | Quel que soit le réglage | Envoyez une demande de récupération avec un délai de 72 heures, même si vous avez un code d’authentification. |
| Associée depuis au moins 72 heures | Désactivée ou activée depuis moins de 72 heures | Réinitialisez immédiatement le mot de passe avec le code de récupération. La récupération désactive la validation en deux étapes si elle a été activée récemment. |
| Associée depuis au moins 72 heures | Activée depuis au moins 72 heures | Saisissez un code d’authentification pour réinitialiser immédiatement le mot de passe et conserver la validation en deux étapes. Sans ce code, envoyez une demande de récupération avec un délai de 72 heures. |

Si vous devez attendre, choisissez **Demander une récupération avec un délai de 72 heures** et suivez le délai affiché sur la page de récupération. Les appareils connectés reçoivent une notification. Vous pouvez choisir **Annuler cette récupération** sur l’un d’eux. Une connexion réussie annule aussi la demande. Après la réinitialisation, connectez-vous avec votre nouveau mot de passe. La récupération avec délai réinitialise la validation en deux étapes.

Après la récupération, vérifiez **Associée le** sous **Machines** et retirez toute machine que vous ne reconnaissez pas. Vous pouvez réactiver la validation en deux étapes dans **Sécurité**.

## Se déconnecter ou supprimer votre compte

Choisissez **Se déconnecter** dans **Moi** pour fermer la session de ce navigateur. Pour fermer votre compte, choisissez **Supprimer le compte**, vérifiez les équipes et machines concernées et confirmez avec votre mot de passe et, si la vérification est activée, un code d’authentification. La suppression déconnecte vos appareils, révoque vos machines et résilie votre abonnement. Connectez-vous dans les sept jours pour annuler la demande. La récupération du mot de passe est indisponible pendant ce délai, car les machines ont été révoquées. À l’expiration du délai, le compte est supprimé et son numéro reste retiré.

## En cas de problème

- Après cinq échecs de connexion en 15 minutes, le verrouillage par défaut dure 15 minutes. Attendez le délai affiché. Un code d’authentification est à usage unique. Si vous venez de l’utiliser, attendez le suivant.
- Si la confirmation du navigateur a expiré ou si vous avez touché le mauvais nombre, recommencez la connexion. Vous pouvez aussi choisir l’une des méthodes avec code proposées. Exécutez `sail confirm` pour un nouveau code de connexion et `sail recover` pour un nouveau code de récupération du mot de passe.
- Si une machine ne peut pas produire de code de récupération, essayez une autre machine associée à votre compte. Si aucune n’a d’identifiants valides, le compte est irrécupérable. Inscrivez-vous avec un nouvel ID.
