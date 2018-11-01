---
title: "Droits d’ut. requis et élém. prérequis pour conf. de la prise d’appel de gr."
TOCtitle: "Droits d’ut. requis et élém. prérequis pour conf. de la prise d’appel de gr."
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945641(v=OCS.15)
ms:contentKeyID: 53095454
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Droits d’utilisateur requis et éléments prérequis pour la configuration de la prise d’appel de groupe

 

_**Dernière rubrique modifiée :** 2013-01-30_

La prise d’appel de groupe est une fonctionnalité de gestion des appels installée par défaut lorsque vous déployez Voix Entreprise. Cette rubrique présente la configuration requise pour la prise d’appel de groupe ainsi que les droits d’utilisateur nécessaires pour effectuer les tâches de configuration.

Cette section part du principe que vous avez lu la documentation de planification relative à la prise d’appel de groupe (voir [Planification de la prise d’appel de groupe dans Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

## Éléments requis pour la configuration de la prise d’appel de groupe

La prise d’appel de groupe requiert les composants suivants :

  - service d’application

  - application de parcage d’appel

Ces composants sont installés automatiquement lors du déploiement de Voix Entreprise.

## Droits d’utilisateur requis pour la configuration de la prise d’appel de groupe

Vous devez utiliser les outils d’administration suivants pour configurer la prise d’appel de groupe :

  - Lync Server Management Shell

  - Outil de Kit de ressources SEFAUtil

Utilisez Lync Server Management Shell pour créer et gérer les groupes de prise d’appel dans la table d’orbites de parcage d’appel. Utilisez l’outil de Kit de ressources SEFAUtil pour assigner un groupe de prise d’appel et activer la fonctionnalité de prise d’appel de groupe pour des utilisateurs ou pour désactiver la fonctionnalité de prise d’appel de groupe pour des utilisateurs.

Selon la tâche de configuration de prise d’appel de groupe, l’un des rôles d’administration suivants est requis :

  - **CsVoiceAdministrator** : ce rôle d’administrateur peut créer, configurer et gérer l’ensemble des stratégies et paramètres de voix.

  - **CsUserAdministrator:** ce rôle d’administrateur peut activer la prise d’appel de groupe pour des utilisateurs. Il dispose aussi d’un accès en lecture seule à toutes les configurations de voix.

  - **CsServerAdministrator** : ce rôle d’administrateur peut gérer, surveiller et dépanner les serveurs et les services.

  - **CsAdministrator** : ce rôle d’administrateur peut exécuter toutes les tâches des rôles CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.

> [!NOTE]  
> Pour plus d’informations sur les droits d’administration, voir <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a> dans la documentation de planification.

## Voir aussi

#### Concepts

[Déploiement de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Autres ressources

[Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

