---
title: 'Lync Server 2013 : Conditions prérequises et rôles de configuration d’annonce'
TOCTitle: Conditions prérequises et rôles de configuration d’annonce
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398658(v=OCS.15)
ms:contentKeyID: 49297921
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conditions prérequises et rôles de configuration d’annonce dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-25_

L’application d’annonce est une fonctionnalité de gestion des appels Voix Entreprise. Cette rubrique décrit les composants à installer pour pouvoir la configurer et les rôles à attribuer pour réaliser des tâches de configuration.

Cette section présuppose que vous avez lu la documentation de planification relative à l’application d’annonce (reportez-vous à [Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

## Conditions préalables de configuration d’annonce

L’application d’annonce requiert les composants suivants :

  - service d’application

  - application Response Group

  - Magasin de fichiers, pour conserver les fichiers audio

Tous ces composants sont installés par défaut lorsque vous déployez Voix Entreprise.

## Rôles de configuration d’annonce

Vous pouvez utiliser les outils administratifs suivants pour configurer les annonces :

  - Panneau de configuration Lync Server

  - Lync Server Management Shell

La configuration de l’application d’annonce nécessite l’un des rôles d’administrateur suivants :

  - **CsVoiceAdministrator**   Ce rôle permet à l’administrateur de créer, configurer et gérer les paramètres et stratégies de voix, notamment les paramètres d’annonce.

  - **CsServerAdministrator**   Ce rôle permet à l’administrateur de créer et de surveiller les serveurs et les services, d’identifier et de résoudre leurs problèmes, et de configurer tous les paramètres d’annonce.

  - **CsAdministrator**   Ce rôle d’administrateur permet d’exécuter toutes les tâches administratives et de modifier tous les paramètres.

  - **CsViewOnlyAdministrator**   Ce rôle d’administrateur permet de visualiser le déploiement pour surveiller son état.

> [!NOTE]  
> Pour plus d’informations sur les droits utilisateur d’administration, reportez-vous à <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a> dans la documentation de planification.

## Voir aussi

#### Concepts

[Déploiement de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Autres ressources

[Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

