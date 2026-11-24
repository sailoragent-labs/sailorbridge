[← SailorBridge](README.md)

# Comptes des moteurs et cadence

Vos agents utilisent les comptes des moteurs connectés sur vos machines. Vous pouvez voir quels comptes une équipe peut utiliser, le quota restant et quand le travail reprendra. Votre offre SailorBridge détermine combien d’agents peuvent fonctionner à la fois. L’accès aux modèles et le quota dépendent du fournisseur du moteur.

## Trouver ou ajouter un compte

1. Connectez-vous à Claude Code ou à Codex sur la machine où vous voulez le faire tourner. Exécutez `sail account list`. Une connexion par défaut est détectée automatiquement. Son nom se compose généralement du nom du moteur, suivi de `@` et du nom de la machine.
2. Pour ajouter une autre connexion, connectez-vous au moteur dans un répertoire de compte distinct. Exécutez `sail account add <name> <directory>` avec ce répertoire et un nom de 1 à 64 caractères, unique sur la machine, sans espaces ni barres obliques. Par exemple, si votre deuxième connexion se trouve à cet emplacement, exécutez `sail account add work "$HOME/codex-work"`. Le prochain relevé de quota la détectera sans redémarrage.
3. Ouvrez **Ressources**, puis **Comptes**. Sélectionnez le compte pour voir ses machines, son quota et les modèles disponibles. Les comptes signalés sous le même nom par le même moteur sur différentes machines figurent sur une seule ligne. Le répertoire de connexion, l’adresse e-mail et les identifiants restent sur la machine.

Codex utilise une connexion par abonnement. Claude Code utilise une connexion par abonnement ou une clé API. Pour Gemini CLI, Copilot CLI, OpenCode, Qwen Code et Pi, seuls l’enregistrement des comptes et les vérifications locales sont disponibles. Parmi ces cinq moteurs, Gemini CLI et OpenCode reconnaissent des répertoires nommés distincts.

## Utiliser un point de terminaison compatible avec Claude

Pour un fournisseur comme DeepSeek ou GLM, configurez un répertoire de compte Claude Code distinct sur votre machine. Dans son fichier `settings.json`, définissez l’URL de base du fournisseur dans `env.ANTHROPIC_BASE_URL` et son identifiant dans `env.ANTHROPIC_API_KEY` ou `env.ANTHROPIC_AUTH_TOKEN`. Dans le même objet, définissez `ANTHROPIC_MODEL` dans `env` avec le nom du modèle du fournisseur. Vous pouvez définir des correspondances distinctes pour les familles Opus, Sonnet et Haiku avec `ANTHROPIC_DEFAULT_OPUS_MODEL`, `ANTHROPIC_DEFAULT_SONNET_MODEL` et `ANTHROPIC_DEFAULT_HAIKU_MODEL`.

Exécutez-y `sail account add <name> <directory>` avec le nom et le chemin choisis. Le compte passe par Claude Code. Ouvrez **Modèles disponibles** pour voir les noms de modèles lus dans le répertoire. Les modèles du point de terminaison utilisent ces correspondances et n’ont pas de réglage d’effort. Les détails de la tâche indiquent le modèle effectivement utilisé.

## Configurer un compte GLM, DeepSeek ou Kimi à partir d’un modèle

`sail account create` écrit un fichier local de paramètres Claude Code contenant le point de terminaison du fournisseur, les modèles proposés pour les niveaux élevé, intermédiaire et bas, et une valeur fictive à remplacer par la clé. La commande ne demande, ne lit ni n’envoie votre clé, et n’enregistre pas le compte.

Pour configurer GLM, exécutez la commande suivante sur la machine où vous voulez utiliser le compte.

```sh
sail account create glm
```

La commande affiche trois lignes. Ici, `~` désigne votre répertoire personnel.

```text
Modèles proposés (Opus/Fable, Sonnet, Haiku/sous-agent) : glm-5.3, glm-5.2, glm-5.3-flash.
Trois identifiants de modèle distincts. Sonnet correspond au niveau intermédiaire proposé.
Dans ~/.sailorbridge/account-templates/glm/settings.json, remplacez la valeur fictive par votre clé API, puis exécutez sail account add <name> ~/.sailorbridge/account-templates/glm.
```

Le fichier `settings.json` généré contient ce modèle.

```json
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "REPLACE_WITH_YOUR_API_KEY",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "ANTHROPIC_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-5.2",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-5.3-flash",
    "ANTHROPIC_DEFAULT_FABLE_MODEL": "glm-5.3",
    "CLAUDE_CODE_SUBAGENT_MODEL": "glm-5.3-flash"
  }
}
```

Ouvrez le fichier dans un éditeur de texte tel que `nano`.

```sh
nano ~/.sailorbridge/account-templates/glm/settings.json
```

Remplacez `REPLACE_WITH_YOUR_API_KEY` par votre propre clé GLM, gardez les guillemets et enregistrez le fichier. Enregistrez le répertoire sous le nom de votre choix. Cet exemple utilise `glm`. Le nom doit être unique sur cette machine et compter de 1 à 64 caractères, sans caractères d’espacement ni `/`.

```sh
sail account add glm ~/.sailorbridge/account-templates/glm
sail account list
```

Cherchez `glm` dans la liste du terminal. Une fois que la machine signale le compte, ouvrez **Ressources** puis **Comptes** dans l’application. Sélectionnez `glm` pour voir ses **Modèles disponibles**.

Pour DeepSeek ou Kimi, commencez par la commande de votre fournisseur. Ouvrez le fichier `settings.json` au chemin affiché et remplacez la valeur fictive par la clé de votre fournisseur. Utilisez la commande `sail account add` affichée avec le nom de votre choix, puis vérifiez `sail account list`.

| Commande de génération du modèle | Point de terminaison dans le fichier | Modèles proposés à l’écran |
| --- | --- | --- |
| `sail account create deepseek` | `https://api.deepseek.com/anthropic` | Le niveau élevé utilise `deepseek-v4-pro`. Les niveaux intermédiaire et bas partagent `deepseek-flash`. |
| `sail account create kimi` | `https://api.kimi.com/coding/` | Utilisez une clé Kimi Coding Plan. Les trois niveaux utilisent `k3.1-pro[1m]`. |

MiniMax exige `--region international` ou `--region china`. GLM, DeepSeek et Kimi refusent `--region`.

## Consulter le quota et en garder une partie pour vous

Ouvrez le compte dans **Comptes**. Consultez ensemble **Quota**, **Réinitialisation** et **Relevé**. Un relevé d’abonnement peut afficher une fenêtre de cinq heures, une fenêtre hebdomadaire ou une allocation hebdomadaire pour un modèle précis. Codex indique son quota hebdomadaire standard. Lire le quota ne consomme aucun jeton de modèle. Si un nouveau relevé échoue, un relevé réussi datant d’au plus une heure peut encore s’afficher, marqué comme ancien. Si le relevé manque, une raison est indiquée et le compte peut tout de même rester admissible au travail.

- **Utilisable** contrôle les nouvelles affectations à ce compte dans toutes vos équipes. Si vous désactivez l’option, le travail déjà lancé peut se terminer.
- **Seuil de réserve** réserve un pourcentage à votre propre usage. Réglez-le de 0 % à 100 % par pas de 5. S’il reste au plus ce pourcentage dans une fenêtre de plus d’un jour, les exécutants et le **Leader** cessent d’utiliser ce compte. Les fenêtres courtes utilisent la totalité de leur allocation.
- Pour un compte suivi par dépense, réglez **Plafond mensuel** sur le maximum que cette machine peut dépenser au cours d’un mois calendaire. Cela s’applique par exemple à DeepSeek. GLM fournit son propre relevé de quota. Une fois le plafond atteint, les nouveaux travaux attendent jusqu’à minuit UTC le premier jour du mois suivant, sauf si vous relevez le plafond. Une étape déjà en cours peut se terminer au-delà du plafond. Si vous enregistrez le même compte sur plusieurs machines, chacune mesure ses propres dépenses. Si **Coût indisponible** apparaît, vous voyez le nombre de jetons et le plafond ne peut pas s’appliquer.
- Les **Crédits de réinitialisation** apparaissent quand Claude ou Codex en signale. Ouvrez un crédit, vérifiez ce qu’il réinitialise et quand il expire, puis choisissez **Utiliser** et confirmez. **Utiliser un crédit** dans la liste des comptes utilise le crédit admissible qui expire en premier. La machine qui détient le compte exécute la réinitialisation. Vérifiez le résultat avant d’utiliser un autre crédit.

## Choisir les comptes et modèles d’une équipe

Ouvrez **Liste des comptes** dans le menu de la discussion d’équipe. Les comptes des machines de l’équipe sont inclus par défaut. Réglez **Rôle** sur **Les deux**, **Écriture seule** ou **Revue seule** pour choisir les étapes que le compte peut exécuter. Avec **Leader seul**, réservez-le à la discussion de cette équipe. **Retirer de l’équipe** et **Ajouter un compte à l’équipe** changent sa disponibilité pour cette équipe.

Dans **Détails de l'équipe**, ouvrez les réglages de distribution. Sous **Modèle du leader**, choisissez un compte utilisable sur une machine de l’équipe, puis un modèle détecté pour ce compte et un niveau d’effort s’il est proposé. Choisir le compte sur une autre machine y déplace le **Leader** pour le prochain message. Si le compte choisi ne peut pas s’exécuter, la réponse indique le moteur et le modèle utilisés en remplacement.

Pour les exécutants, définissez le modèle et l’effort souhaités pour chaque niveau de difficulté et chaque moteur dans les réglages de modèles de l’équipe. Les options de rédaction et de revue du flux déterminent le moteur. En revue automatique, le relecteur évite si possible la famille de modèles réellement utilisée par le rédacteur. Si le flux demande un moteur pour lequel l’équipe n’a pas de compte dans ce rôle, la tâche peut utiliser la sélection automatique pour cette exécution. Les détails de la tâche expliquent le changement.

Une tâche a besoin d’une seule machine capable d’exécuter toutes ses étapes. Sur cette machine, chaque étape utilise un compte activé et autorisé pour son moteur et son rôle. Parmi les comptes admissibles, une connexion en attente de renouvellement passe en premier. Viennent ensuite les comptes dont le quota se réinitialise dans un délai d’un jour, en commençant par la réinitialisation la plus proche. Pour les réinitialisations plus tardives, la sélection tient compte du quota utilisable, de la capacité de l’offre et du temps restant. Les comptes sans relevé passent en dernier. Une revue des seuls changements depuis la revue précédente, ou une première revue d’au plus 120 lignes modifiées, favorise une offre plus petite ayant de la marge.

## Régler la cadence des nouveaux travaux

Ouvrez **Ressources**, puis **Mode de Cadence**. Le réglage par défaut, **Selon le Quota**, étale le travail sur la fenêtre de quota. Un compte dépasse la cadence prévue quand le pourcentage consommé dépasse de plus de 100/7 points de pourcentage (environ 14,3) le pourcentage de temps écoulé et qu’il reste plus d’un septième de la fenêtre. Si tous les comptes admissibles dépassent cette cadence, la machine attend avant de prendre une nouvelle tâche. Une tâche en cours peut continuer. La discussion avec le **Leader** peut aussi continuer.

Choisissez **Sans Limite** pour permettre à toutes vos équipes de prendre de nouvelles tâches sans attendre à cause de ce seuil de cadence. Les réserves des comptes et les fenêtres épuisées continuent de s’appliquer. Si un compte est sélectionné pour le **Leader** dans l’une de vos équipes et qu’il reste moins de 10 % dans une fenêtre couvrant tout le compte, les exécutants le réservent à la discussion. Vous pouvez revenir à **Selon le Quota** sur la même page.

## En cas de problème

- Si le fichier modèle existe déjà, la commande refuse de le remplacer et affiche son chemin. Modifiez ce fichier et enregistrez son répertoire.
- Si la commande refuse un répertoire, vérifiez le chemin affiché. Le répertoire doit appartenir à votre utilisateur et avoir le mode `0700` afin que vous seul puissiez y accéder. Corrigez le propriétaire et les droits, puis relancez la commande de création.
- `sail uninstall` supprime `~/.sailorbridge/`, dont ces fichiers de paramètres. Conservez donc une copie de votre clé ailleurs.
- Si l’enregistrement échoue, suivez la commande de connexion affichée par le terminal pour le répertoire fourni. Celui-ci doit désigner un seul moteur. Utilisez `sail account list` pour vérifier le nom. Pour retirer un enregistrement ou ignorer une connexion par défaut, exécutez `sail account remove <name>`. Les identifiants locaux sont conservés. Pour reconnaître de nouveau une connexion par défaut, exécutez `sail account restore claude` ou `sail account restore codex`, ou ouvrez **Connexions ignorées** sur la machine et choisissez **Restaurer**.
- Pour **Session expirée**, reconnectez-vous sur la machine indiquée. Pour **Session à renouveler**, la machine tente de renouveler la connexion. Pour **Réseau indisponible**, vérifiez la connexion de la machine. Si le fournisseur limite les requêtes ou est indisponible, une nouvelle tentative est faite après un délai. Si le compte indique **Modèles Pas Encore Lus** dans le sélecteur de modèles, attendez un relevé ou choisissez un compte avec un modèle détecté.
- Si une équipe refuse de retirer le compte de son **Leader**, sélectionnez d’abord un autre compte dans **Modèle du leader**. Si une tâche manque d’un rédacteur ou d’un relecteur, choisissez **Aller aux comptes** dans ses détails et activez le rôle manquant sur une machine qui peut exécuter toute la tâche.
- Ouvrez **Liste des tâches** et lisez **Pourquoi elle ne tourne pas**. Une attente liée à la cadence indique une estimation. Vous pouvez attendre ou confirmer **Passer Sans Limite** pour toutes les équipes. Une tâche dont les comptes utilisables sont à court de quota attend sur la même machine et vérifie à nouveau à l’heure affichée. Elle reprend automatiquement une fois le compte reconnecté ou le quota rétabli.
