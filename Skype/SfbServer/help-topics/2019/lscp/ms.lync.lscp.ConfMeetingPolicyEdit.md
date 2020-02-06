---
title: Stratégie de conférence création d’un nouveau ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Une stratégie de conférence définit les fonctionnalités et les fonctions à la disposition des utilisateurs lors d’une conférence (également appelée « réunion »).
ms.openlocfilehash: df48a986e4f316cfc6250e5a7d016af4488dc483
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793412"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Stratégie de conférence : création d’une stratégie ou modification d’une création existante

Une stratégie de conférence définit les fonctionnalités et les fonctions à la disposition des utilisateurs lors d’une conférence (également appelée « réunion »).

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Scope** Identifie l’étendue de la stratégie de conférence que vous créez ou modifiez : global, site ou utilisateur.

- **Nom** Chaque stratégie de conférence nécessite un nom. Les stratégies de conférence globale et de site sont nommées par défaut et le nom ne peut pas être modifié. Pour les stratégies de conférences utilisateur, utilisez un nom descriptif qui identifie l’utilisateur ou le groupe d’utilisateurs.

    > [!NOTE]
    > Une fois que vous avez enregistré la stratégie de conférence, son nom ne peut plus être modifié.

- **Description** Ce champ est facultatif. Utilisez-la pour fournir des informations supplémentaires sur la stratégie de conférence.

- **Stratégie** de l’organisateur Les paramètres de cette section s’appliquent à l’utilisateur qui organise une conférence. Si un paramètre est sélectionné, l’utilisateur peut organiser une conférence ayant la caractéristique spécifiée. Si aucun paramètre n’est sélectionné, l’utilisateur ne peut pas organiser de conférence avec cette caractéristique. Ces paramètres ne permettent pas de déterminer le type d’accès de l’utilisateur à un participant à une autre conférence.

    Cliquez sur la flèche vers le haut ou la flèche vers le bas en regard de l’étiquette pour fermer ou ouvrir la section.

- **Taille maximale** de la réunion : nombre maximal d’utilisateurs autorisés à une conférence. Par défaut, la taille maximale de la réunion est de 250.

- **Autoriser les participants à inviter des utilisateurs anonymes** Activez cette case à cocher pour autoriser les utilisateurs à inviter des utilisateurs anonymes à des conférences. Les utilisateurs anonymes sont des utilisateurs qui ne disposent pas des informations d’identification dans les services de domaine Active Directory de votre organisation et qui, par conséquent, ne sont pas authentifiés.

- **Enregistrement** en Indiquez si les participants peuvent ou non enregistrer des conférences. Les **options ne sont** pas disponibles ou **autorisent l’enregistrement**.

- **Permettre aux participants fédérés et anonymes d’enregistrer** Activez cette case à cocher pour autoriser les participants externes et non authentifiés à enregistrer des conférences.

- **Audio/vidéo** Indiquez si les participants peuvent utiliser l’audio et la vidéo :

  - **Aucun** Sélectionnez cette option pour éviter l’utilisation de l’audio et de la vidéo.

  - **Activer l’audio IP** Sélectionnez cette option pour autoriser l’utilisation de l’audio, mais pas de vidéo.

  - **Activer les appels audio/vidéo IP** Sélectionnez cette option pour autoriser les éléments audio et vidéo.

- **Activer les conférences** rendez-vous RTC Si vous avez activé le son dans l' **audio/la vidéo**, activez cette case à cocher pour permettre aux utilisateurs de se connecter aux conférences à l’aide du réseau téléphonique public commuté (RTC).

- **Permettre aux participants anonymes d’appeler** Activez cette case à cocher si vous autorisez les utilisateurs à se connecter aux conférences et que vous souhaitez autoriser les utilisateurs non authentifiés à rejoindre une conférence à l’aide de la numérotation de l’appelant. Avec cette fonctionnalité, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour participer à la conférence.

- **Autorisez les participants non activés pour les appels vocaux d’entreprise** Si vous avez activé le son dans l' **audio/la vidéo**, activez cette case à cocher pour autoriser les utilisateurs qui ne sont pas autorisés à participer à une conférence à l’aide de la fonction d’appel sortant. Avec la fonction d’appel sortant, le serveur de conférence appelle le téléphone de l’utilisateur, puis il répond au téléphone pour participer à la Conférence.

- **Autoriser plusieurs flux vidéo** Si vous avez activé la vidéo dans un **fichier audio/vidéo**, activez cette case à cocher pour permettre aux utilisateurs d’organiser des conférences avec la vidéo d’affichage Galerie. Lorsque cette case est cochée, ce paramètre permet aux utilisateurs d’organiser des conférences qui envoient plusieurs flux vidéo. Si cette case à cocher est désactivée, les utilisateurs peuvent uniquement organiser des conférences qui envoient un flux vidéo unique.

    > [!NOTE]
    > Cette option détermine le type de flux vidéo pris en charge par la conférence. Il ne détermine pas si les participants peuvent recevoir plusieurs flux vidéo. L’option **Autoriser les participants à rejoindre plusieurs flux de données vidéo** détermine si les participants peuvent recevoir plusieurs flux vidéo.

- **Collaboration** sur les données Indiquez si la Conférence autorise la collaboration sur les données. Les options ne sont **aucune** ou **autorisent la collaboration**sur les données.

    Les paramètres ci-dessous concernent la collaboration de données :

  - **Autoriser les participants fédérés et anonymes à télécharger du contenu** Si vous autorisez la collaboration sur les données, activez cette case à cocher pour autoriser les utilisateurs externes et non authentifiés à télécharger du contenu, tel que des diapositives ou des documents, à partir d’une conférence.

  - **Autoriser les participants à transférer des fichiers** Si vous autorisez la collaboration sur les données, activez cette case à cocher pour autoriser les transferts de fichiers à tous les participants d’une conférence.

  - **Activer les annotations** Si vous autorisez la collaboration sur les données, activez cette case à cocher pour autoriser les participants à effectuer des annotations à l’écran sur le contenu partagé lors de la Conférence.

  - **Activer les annotations PowerPoint** Si vous autorisez les annotations, activez cette case à cocher pour autoriser les participants à faire des annotations dans les diapositives PowerPoint partagées lors de la Conférence.

  - **Activer les sondages** Si vous autorisez la collaboration sur les données, activez cette case à cocher pour autoriser les participants à organiser un sondage au cours d’une conférence.

- **Partage d’application** Indiquez si la Conférence autorise le partage d’application. Les options sont **désactiver le partage d’application** ou **activer le partage d’application**.

    Les paramètres ci-dessous concernent le partage d’application :

  - **Autoriser les participants à prendre le contrôle** Si vous autorisez le partage d’application, activez cette case à cocher pour autoriser les participants à prendre le contrôle d’applications ou de bureaux partagés pendant la Conférence.

  - **Autoriser les participants fédérés et anonymes à prendre le contrôle** Si vous autorisez le partage d’application, activez cette case à cocher pour autoriser les participants externes et non authentifiés à prendre le contrôle d’applications ou de bureaux partagés pendant la Conférence.

- **Stratégie de participant** Les paramètres de cette section s’appliquent aux utilisateurs en tant que participants d’une conférence ou d’une session à deux parties. Dans la mesure où les paramètres suivants sont définis par l’utilisateur, un utilisateur dans une conférence ou une session à deux parties peuvent avoir différentes fonctionnalités qu’un autre utilisateur au sein de la même conférence ou d’une même session à deux.

    Cliquez sur la flèche vers le haut ou la flèche vers le bas en regard de l’étiquette pour fermer ou ouvrir la section.

- Sélectionnez **Activer le partage d’application et de Bureau** pour autoriser les utilisateurs à partager les applications et leur Bureau lorsqu’ils participent à une conférence ou à une session à deux participants. Sélectionnez **Désactiver le partage d’application et de Bureau** pour empêcher les utilisateurs de partager les applications et leur Bureau lorsqu’ils participent à une conférence ou à une session à deux participants.

- **Activer le transfert de fichiers d’égal à égal** Activez cette case à cocher pour autoriser le transfert de fichiers de personne à personne (c’est-à-dire les transferts de fichiers qui n’impliquent pas tous les participants) pendant une conférence ou une session à deux.

- **Activer l’enregistrement d’égal à égal** Activez cette case à cocher pour autoriser les utilisateurs à enregistrer des sessions à deux parties.

- **Permettre aux participants de s’affilier à plusieurs flux vidéo** Activez cette case à cocher pour autoriser les participants à recevoir la vidéo d’affichage Galerie en conférences qui les autorisent. Si cette option n’est pas sélectionnée, les participants ne peuvent recevoir qu’un seul flux vidéo, quelle que soit la Conférence autorise.

    > [!NOTE]
    > L’option **Autoriser plusieurs flux de données vidéo** détermine si une conférence autorise plusieurs flux vidéo.

Pour plus d’informations sur les fonctionnalités et les fonctions de conférence, reportez-vous à la rubrique [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) de la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de conférence, reportez-vous à la rubrique [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) de la documentation des opérations.


