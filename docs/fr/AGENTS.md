[English](../../AGENTS.md) · [简体中文](../zh-CN/AGENTS.md) · [日本語](../ja/AGENTS.md) · [한국어](../ko/AGENTS.md) · [Deutsch](../de/AGENTS.md) · [Français](AGENTS.md) · [Español](../es/AGENTS.md) · [Português (BR)](../pt-BR/AGENTS.md) · [Bahasa Indonesia](../id/AGENTS.md) · [हिन्दी](../hi/AGENTS.md)

# Guide de configuration de SailorBridge

## 1. Préparer la machine

Utilisez une machine que vous contrôlez, sous Linux x64 ou macOS sur arm64 ou x64. Installez Git ainsi que Claude Code ou Codex. Connectez-vous au moteur avec votre propre compte et choisissez le répertoire du projet de l’équipe.

**Vérification** — `git --version` et, selon le moteur, `claude --version` ou `codex --version` affichent chacun une version. Si le moteur est installé mais déconnecté, exécutez `claude login` ou `codex login` sur cette machine. Vous pouvez déjà associer la machine. Connectez-vous au moteur avant la première discussion ou tâche.

## 2. S’inscrire dans le navigateur

Ouvrez l’[application](https://app.sailorbridge.com) et choisissez **S'inscrire**. Pour ce guide, saisissez un ID du capitaine numérique disponible et indiqué comme gratuit, définissez un mot de passe, confirmez votre âge et acceptez les conditions d’utilisation.

**Vérification** — L’application s’ouvre et vous pouvez accéder à **Machines**.

## 3. Exécuter la commande d’installation

Dans **Machines**, ouvrez **Associer une nouvelle machine**. Copiez l’unique commande d’installation affichée et exécutez-la sur la machine de l’étape 1. Elle installe `sail` et lance automatiquement l’association.

**Vérification** — Le terminal affiche un code d’appariement de huit caractères et le temps restant. Si le code expire, exécutez `sail login` pour en obtenir un nouveau.

- **Machine déjà associée à cette adresse ?** Exécutez `sail host status`. Si elle est connectée, passez à l’étape 5. Pour rétablir le service à la même adresse, exécutez `sail login`. Le service redémarre avec ses identifiants existants.
- **Adresse incorrecte (`origin_mismatch`) ?** Pour changer d’adresse, exécutez `sail uninstall`, puis copiez et exécutez la commande d’installation depuis la page Machines de l’application voulue. La désinstallation supprime les données locales de SailorBridge, y compris ses copies de travail.

## 4. Approuver la machine

Saisissez le code d’appariement sur la page d’association du navigateur et choisissez **Associer**. Comparez le nom de la machine et le **Code de clé** avec ceux du terminal. Lors de la première association, lisez et acceptez l’avis sur les droits de l’utilisateur qui exécute `sail`, puis choisissez **Approuver la machine**.

**Vérification** — Attendez que l’état **En ligne** apparaisse sous **Machines**. Le terminal confirme lui aussi que la machine est associée et en ligne.

## 5. Créer une équipe

Choisissez **Créer une Équipe**. Nommez l’équipe, sélectionnez la machine en ligne et indiquez le chemin absolu sur cette machine sous **Répertoire du projet**. Si le répertoire n’existe pas, SailorBridge le crée à la première utilisation. Sous **Destination**, gardez **Auto-fusion** pour fusionner les modifications dans la branche principale distante, ou choisissez **Branche** pour pousser chaque tâche sur sa propre branche en vue d’une revue. Créez l’équipe.

**Vérification** — Dans la nouvelle équipe, la machine sélectionnée apparaît **En ligne**.

## 6. Envoyer le premier message

Ouvrez la **Discussion** de l’équipe et demandez « Dans quel répertoire du projet travaillons-nous ? »

**Vérification** — Le **Leader** répond dans la même discussion.

## 7. Terminer la première tâche

Dans la discussion d’équipe, envoyez `/agent Compte les fichiers à la racine du projet et donne-moi leur nombre.` Ouvrez **⋯ → Liste des tâches** pour suivre la tâche.

**Vérification** — La tâche affiche l’état **Finie**. Ouvrez le **Rapport de livraison** et vérifiez le nombre de fichiers.
