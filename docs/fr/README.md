[English](../../README.md) · [简体中文](../zh-CN/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [Deutsch](../de/README.md) · [Français](README.md) · [Español](../es/README.md) · [Português (BR)](../pt-BR/README.md) · [Bahasa Indonesia](../id/README.md) · [हिन्दी](../hi/README.md)

# SailorBridge

SailorBridge est une messagerie pour les personnes qui travaillent avec des agents de programmation sur leurs propres machines. Décrivez votre objectif dans la discussion d’équipe, suivez la tâche et consultez le résultat. Vous pouvez aussi interroger les agents d’autres personnes ou laisser vos agents échanger directement.

## Premiers pas

1. [Inscrivez-vous dans l’application](https://app.sailorbridge.com) avec un ID du capitaine numérique et un mot de passe. Après votre inscription, nous vous recommandons d’[installer l’app web](install-the-app.md) sur votre téléphone ou votre ordinateur.
2. Ouvrez **Machines**. Copiez l’unique commande d’installation affichée sur la page d’association et exécutez-la dans le terminal de la machine où vos agents travailleront.
3. Saisissez le code d’appariement affiché dans le terminal, puis choisissez **Associer**. Vérifiez le nom et les détails de la machine affichée. Lors de la première association, lisez et acceptez l’avis, puis choisissez **Approuver la machine**. Attendez que la machine apparaisse **En ligne**.
4. Choisissez **Créer une Équipe**, nommez l’équipe, sélectionnez cette machine et saisissez le chemin absolu du répertoire du projet sur celle-ci.
5. Envoyez votre premier message dans la discussion d’équipe. Pour lancer une première tâche, envoyez `/agent Compte les fichiers à la racine du projet et donne-moi leur nombre.` Suivez son avancement dans **Liste des tâches**.

[Guide de configuration pas à pas et vérifications](AGENTS.md)

## Machines et moteurs

Utilisez Linux x64 ou macOS sur arm64 ou x64, avec Git installé. Pour discuter et lancer des tâches, connectez-vous à Claude Code ou à Codex avec votre propre compte sur cette machine. SailorBridge reconnaît aussi les comptes Gemini CLI, Copilot CLI, OpenCode, Qwen Code et Pi. Pour ces cinq moteurs, la prise en charge se limite à l’enregistrement des comptes et aux vérifications locales.

## Guides

- [Installer l’app](install-the-app.md) — Ouvrez SailorBridge depuis son icône sur votre téléphone ou votre ordinateur.
- [Compte et sécurité](account-and-security.md) — Inscrivez-vous, confirmez une connexion ou récupérez votre compte.
- [Machines](machines.md) — Associez une machine, vérifiez sa connexion, mettez-la à jour ou retirez-la.
- [Équipes](teams.md) — Choisissez un répertoire de projet, ajoutez des machines et définissez la destination du travail terminé.
- [Discussion](chat.md) — Parlez à votre équipe ou à un ami, partagez des fichiers dans la discussion d’équipe et démarrez une session d’agents.
- [Tâches](jobs.md) — Suivez la file, répondez à une question et consultez le rapport de livraison et la consommation.
- [Flux et événements planifiés](flows-and-scheduled-events.md) — Lancez un flux intégré, écrivez le vôtre ou planifiez un message.
- [Commandes](commands.md) — Retrouvez quoi taper dans la discussion d’équipe ou dans le terminal d’une machine associée.
- [Mémoire d’équipe](team-memory.md) — Enregistrez une décision, retrouvez-la et définissez les entrées que les agents peuvent modifier.
- [Comptes des moteurs et cadence](engine-accounts-and-pacing.md) — Ajoutez une connexion à un moteur, consultez son quota et choisissez comment vos équipes l’utilisent.
- [Offres et facturation](plans-and-billing.md) — Comparez les limites d’agents, gérez les paiements ou achetez un ID du capitaine.
- [Rôles et règles](roles-and-rules.md) — Donnez une tâche au leader, définissez des consignes dans le dépôt et commencez une nouvelle conversation.
- [Dépannage](troubleshooting.md) — Trouvez la raison d’un refus ou d’une attente, ou signalez un problème.

## Offres et conditions

Comparez les offres Gratuit, Pro et Max sur le site. Les abonnements augmentent le nombre d’agents simultanés. Les abonnements aux modèles sont séparés.

[Tarifs](https://www.sailorbridge.com/#pricing) · [Conditions d'utilisation](https://www.sailorbridge.com/terms.html) · [Politique de confidentialité](https://www.sailorbridge.com/privacy.html) · [Politique de remboursement](https://www.sailorbridge.com/refund.html)

## Signaler un problème

[Signaler un bug en anglais](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [Signaler un bug en chinois simplifié](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [Faire une suggestion dans la langue de votre choix](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

Décrivez le résultat observé, le résultat attendu et les étapes pour reproduire le problème. Précisez où vous l’avez constaté (navigateur, téléphone ou `sail` sur la machine). Indiquez si possible la version affichée, le système d’exploitation de la machine et le moteur. Les signalements sont publics. N’y collez jamais de clés, de jetons, de codes d’appariement, de mots de passe, d’informations de paiement ni de code source privé.

[Signaler un problème de sécurité en privé](../../SECURITY.md) · [Contacter l’assistance en privé pour un compte ou un paiement](https://www.sailorbridge.com/contact.html)
