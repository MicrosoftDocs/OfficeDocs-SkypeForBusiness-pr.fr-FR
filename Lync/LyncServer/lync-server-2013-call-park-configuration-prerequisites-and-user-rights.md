---
title: "Lync Server 2013 : Cond. Préreq. pr conf. parcage d’appel et droits ut."
TOCTitle: Conditions prérequises pour la configuration du parcage d’appel et des droits utilisateur
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425730(v=OCS.15)
ms:contentKeyID: 49296611
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conditions prérequises pour la configuration du parcage d’appel et des droits utilisateur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-10_

Le parcage d’appel est une fonctionnalité de gestion des appels installée par défaut lorsque vous déployez Voix Entreprise. Cette rubrique présente la configuration requise pour le parcage d’appel ainsi que les droits d’utilisateur nécessaires pour effectuer les tâches de configuration.

> [!IMPORTANT]  
> Les fichiers d’attente musicale personnalisée pour le application de parcage d’appel ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et ils seront perdus si les fichiers téléchargés dans le pool sont endommagés ou effacés. Conservez toujours une copie de sauvegarde des fichiers d’attente musicale personnalisée que vous avez téléchargés pour le parcage d’appel.

Cette section suppose que vous ayez lu la documentation de planification du parcage d’appel (reportez-vous à [Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

## parcage d’appelComposants requis pour la configuration

parcage d’appel requiert les composants suivants :

  - service d’application

  - application de parcage d’appel

Ces composants sont installés automatiquement lors du déploiement de Voix Entreprise.

Si vous voulez que les appelants entendent de la musique lors du parcage des appels, un fichier d’attente musicale est également requis. Un fichier d’attente musicale par défaut est également installé automatiquement lors du déploiement de Voix Entreprise. Vous pouvez le remplacer par un fichier d’attente musicale de votre choix. La fonction de parcage d’appel stocke le fichier audio dans le magasin de fichiers.

## Droits d’utilisateur nécessaires à la configuration du parcage d’appel

Vous pouvez utiliser les outils d’administration suivants pour configurer parcage d’appel :

  - Panneau de configuration Lync Server

  - Lync Server Management Shell

Les outils suivants permettent de configurer la table d’orbite du parcage d’appel ainsi que les autres paramètres utilisés par parcage d’appel.

Selon la tâche de configuration de parcage d’appel l’un des rôles d’administration suivants est requis :

  - **CsVoiceAdministrator** : ce rôle d’administrateur peut créer, configurer et gérer l’ensemble des stratégies et paramètres de voix.

  - **CsUserAdministrator :** ce rôle d’administrateur peut activer le parcage d’appel dans une stratégie de voix. Il dispose aussi d’un accès en lecture seule à toutes les configurations de voix.

  - **CsServerAdministrator** : ce rôle d’administrateur peut gérer et surveiller les serveurs et les services, identifier leurs problèmes et les résoudre.

  - **CsAdministrator** : ce rôle d’administrateur peut exécuter toutes les tâches des rôles CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.

> [!NOTE]  
> Pour plus d’informations sur les droits d’administration, reportez-vous à <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a> dans la documentation de planification.

## Voir aussi

#### Concepts

[Déploiement de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Autres ressources

[Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

