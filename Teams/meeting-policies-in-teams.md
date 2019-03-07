---
title: Gérer les stratégies de réunion
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 03/01/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
description: Apprenez à gérer les paramètres de stratégie dans les équipes de réunion.
ms.openlocfilehash: a7b7cc9d6aa0ba10583f872d8c542152f908b551
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462651"
---
# <a name="manage-meeting-policies-in-teams"></a>Gérer les stratégies de la réunion dans les équipes

::: zone target="docs"
Stratégies de réunion sont utilisés pour contrôler les fonctionnalités qui sont disponibles pour les participants à des réunions sont planifiées par les utilisateurs de votre organisation. Une fois que vous créez une stratégie et apportez vos modifications, vous pouvez ensuite assigner utilise pour la stratégie. 

Par défaut, une stratégie nommée Global (valeur par défaut à l’échelle de l’organisation) est créée. Tous les utilisateurs de votre organisation recevront cette stratégie de réunion par défaut. Apporter des modifications à cette stratégie ou créer un ou plusieurs des stratégies personnalisées et leur affecter des utilisateurs. Lorsque vous créez une stratégie personnalisée, autoriser ou empêcher certaines fonctionnalités disponibles pour vos utilisateurs et puis l’affecter à un ou plusieurs utilisateurs qui possèdent les paramètres qui leur sont appliquées. 

## <a name="change-or-create-a-meeting-policy"></a>Modifier ou créer une stratégie de réunion

Pour modifier ou créer une stratégie de réunion, accédez au **Centre d’administration de Microsoft équipes** > **réunions** > **stratégies de la réunion**. Sélectionnez une stratégie dans la liste, ou sélectionnez **nouvelle stratégie**. Choisir les paramètres, puis cliquez sur **Enregistrer**.

Par exemple, vous disposez d’un ensemble d’utilisateurs et que vous souhaitez limiter la quantité de bande passante qui nécessite leur réunion. Vous créez une nouvelle stratégie personnalisée appelée « Bande passante limitée » et désactiver les paramètres suivants :

Sous **Audio & vidéo**:
- Désactiver le nuage d’enregistrement
- Désactiver la vidéo IP Autoriser

Sous **partage de contenu**:
- Désactiver le mode de partage d’écran
- Désactiver le tableau blanc
- Désactiver les notes partagées

Ensuite, attribuez la stratégie aux utilisateurs.

> [!NOTE] 
> Un utilisateur peut être affecté à une stratégie de réunion qu’un seul à la fois. 

## <a name="assign-a-meeting-policy-to-a-user"></a>Affecter une stratégie de réunion à un utilisateur

Pour affecter une stratégie, accédez au **Centre d’administration de Microsoft équipes** > **les utilisateurs**. 
 
Si vous appliquez la stratégie à un utilisateur, sélectionnez le nom complet de l’utilisateur. En regard de **stratégies attribuées**, sélectionnez **Modifier**. Ensuite, dans le volet **Modifier les stratégies d’utilisateur** , sous **stratégie de réunion**, sélectionnez la stratégie de réunion dans la liste déroulante et sélectionnez **Enregistrer**. Vous pouvez également modifier les paramètres de la liste des utilisateurs. Pour ce faire, sélectionnez l’utilisateur en cliquant à gauche du nom complet de l’utilisateur. Sélectionnez **Modifier les paramètres**. Puis, dans le volet **Modifier les paramètres** , sous **stratégie de réunion**, sélectionnez la stratégie dans la liste déroulante, puis sélectionnez **Enregistrer**. 
 
Si vous appliquez une stratégie à plusieurs utilisateurs, sélectionnez chacune des utilisateurs en cliquant sur à gauche du nom d’utilisateur, puis cliquez sur **Modifier les paramètres**. Dans le volet **Modifier les paramètres** , sous **stratégie de réunion**, sélectionnez la stratégie dans la liste déroulante, puis sélectionnez **Enregistrer**.
 
Vous pouvez également le faire en accédant au **Centre d’administration de Microsoft équipes** > **réunions** >  **stratégies de la réunion**. Sélectionnez la stratégie, puis sélectionnez **Gérer les utilisateurs**. Dans le volet **Gérer les utilisateurs** , recherchez l’utilisateur par un nom complet ou l’utilisateur. Sélectionnez le nom et sélectionnez **Ajouter**. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

> [!NOTE] 
> Impossible de supprimer une stratégie si les utilisateurs sont qui lui est affectés. Vous devez d’abord attribuer une stratégie différente à tous les utilisateurs concernés, et vous pouvez supprimer la stratégie d’origine.
 
 
## <a name="user-policy-settings"></a>Paramètres de stratégie utilisateur

Lorsque vous sélectionnez une stratégie existante dans la page de **stratégies de réunion** ou sélectionnez **nouvelle stratégie** pour ajouter une nouvelle stratégie, vous pouvez configurer les paramètres suivants.

### <a name="new-meeting-policy-name-and-description"></a>Nouvelle réunion stratégie nom et description
   - **Nom** C’est le nom de la stratégie qui apparaîtra dans la page de **stratégies de la réunion** . Il ne peut pas contenir de caractères spéciaux ou plus de 64 caractères. Notez que vous ne pouvez pas modifier le nom d’une stratégie existante.
   - **Description** Vous pouvez placer dans une description conviviale de la stratégie que vous créez. Cela sera utile si vous souhaitez affecter une stratégie à un groupe d’utilisateurs.
::: zone-end 

<a name="bkgeneral"> </a>
### <a name="general"></a>Général
   - **Autoriser la conférence maintenant** Activer cette fonctionnalité permet la fonctionnalité Conférence maintenant être accessibles aux utilisateurs qui participer à des réunions.
   - **Autoriser le complément Outlook** Activer cette fonctionnalité permet aux utilisateurs affectés à la stratégie de disposer le complément Outlook disponible lorsqu’ils planifient des réunions.
   - **Planifier des réunions canal autoriser** Activer cette fonctionnalité permet de planifier des réunions de canal.
   - **Autoriser la planification de réunions privées** Activer cette fonctionnalité permet aux utilisateurs qui participer à une réunion pour organiser des réunions privées.

<a name="bkaudioandvideo"> </a>

### <a name="audio--video"></a>Audio & vidéo
   - **Transcription autoriser** Si vous activez ce, la transcription de la réunion sera disponible pour les utilisateurs.
   - **Enregistrement du nuage autoriser** Activer cette fonctionnalité permettra d’enregistrements à enregistrer dans le nuage.
   - **IP Autoriser la vidéo** Activer cette fonctionnalité permettra de vidéos IP au cours des réunions.
   - **Media vitesse (Kbits/s)** Vous pouvez définir la vitesse de transmission pour les réunions. La valeur par défaut est 50 Mo.

<a name="bkcontentsharing"> </a>

### <a name="content-sharing"></a>Partage de contenu
   - **Mode de partage d’écran** Vous pouvez sélectionner le mode de partage d’écran. Il s’agit de la taille de l’écran qui sera utilisé lors d’une réunion utilisables par un utilisateur affecté à la stratégie.
   - **Autoriser un participant à faire ou demander le contrôle** Cela permet à tous les participants à une réunion et demander le contrôle du partage d’écran.
   - **Autoriser un participant externe à faire ou demander le contrôle** Cela permet à un participant externe (quelqu'un ne fait pas partie de votre visant) et demander le contrôle d’une réunion lorsque l’écran est partagé.
   - **Partage PowerPoint autoriser** Si vous activez ce, les utilisateurs qui planifient des réunions peuvent partager des diapositives PowerPoint pendant une réunion.
   - **Tableau blanc autoriser** Si vous activez ce, le tableau blanc sera disponible pour les participants pendant une réunion.
   - **Autoriser les notes partagées** Si vous activez ce, notes partagées sera disponibles pour les participants pendant une réunion.

<a name="bkparticipantsandguests"> </a>

### <a name="participants--guests"></a>Invités & des participants
   - **Autoriser les utilisateurs anonymes pour démarrer les réunions** Si ce paramètre est désactivé, seule une personne qui a été authentifié à la réunion avec une application d’équipes permettre démarrer la réunion. S’il est activé, tout le monde peut démarrer la réunion.
   - **Accepter automatiquement les utilisateurs** Si vous désactivez cette option, participants à la réunion seront à gauche dans la salle d’attente jusqu'à ce qu’un utilisateur démarre la réunion. S’il est activé, les participants à la réunion est autorisée à participer à la réunion automatiquement.

[Article complet](meeting-policies-in-teams.md)

### <a name="related-topics"></a>Rubriques connexes
[Stratégies de messagerie dans les équipes](messaging-policies-in-teams.md)