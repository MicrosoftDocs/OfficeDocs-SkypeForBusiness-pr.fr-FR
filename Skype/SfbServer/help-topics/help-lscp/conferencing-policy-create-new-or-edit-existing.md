---
title: 'Stratégie de conférence : création d’une stratégie ou modification d’une stratégie existante'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: Une stratégie de conférence définit les fonctionnalités dont disposent les utilisateurs pendant une conférence (également appelée réunion).
ms.openlocfilehash: be0e6ee522d3bff98ab87cc8bbab7057499b0ede
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775204"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Stratégie de conférence : création d’une stratégie ou modification d’une stratégie existante

Une stratégie de conférence définit les fonctionnalités dont disposent les utilisateurs pendant une conférence (également appelée réunion).

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les champs de la page.

- **Étendue** Identifie l’étendue de la stratégie de conférence que vous créez ou modifiez : globale, site ou utilisateur.

- **Nom** Chaque stratégie de conférence nécessite un nom. Les stratégies de conférence globale et de site sont nommées par défaut et le nom ne peut pas être modifié. Pour les stratégies de conférence utilisateur, utilisez un nom descriptif qui identifie l’utilisateur ou le groupe d’utilisateurs.

    > [!NOTE]
    > Une fois que vous avez enregistrez la stratégie de conférence, le nom ne peut pas être modifié.

- **Description** Ce champ est facultatif. Utilisez-le pour fournir des détails supplémentaires sur la stratégie de conférence.

- **Stratégie de l’organisateur** Les paramètres de cette section s’appliquent à l’utilisateur qui organise une conférence. Si un paramètre est sélectionné, l’utilisateur peut organiser une conférence qui a la caractéristique spécifiée. Si un paramètre n’est pas sélectionné, l’utilisateur ne peut pas organiser une conférence avec cette caractéristique. Ces paramètres ne déterminent pas ce à quoi l’utilisateur a accès en tant que participant à d’autres conférences.

    Cliquez sur la flèche vers le haut ou vers le bas à côté de l’étiquette pour fermer ou ouvrir la section.

- **Taille maximale de la** réunion : nombre maximal d’utilisateurs autorisés à une conférence. Par défaut, la taille maximale de conférence est de 250.

- **Autoriser les participants à inviter des utilisateurs anonymes** Cochez cette case pour autoriser les utilisateurs à inviter des utilisateurs anonymes à des conférences. Les utilisateurs anonymes sont des utilisateurs qui n’ont pas d’informations d’identification dans les services de domaine Active Directory de votre organisation et qui, par conséquent, ne sont pas authentifiés.

- **Enregistrement** Spécifiez si les participants peuvent ou non enregistrer des conférences. Les options sont **Aucun ou** **Activer l’enregistrement.**

- **Autoriser les participants fédérés et anonymes à enregistrer** Cochez cette case pour autoriser les participants externes et non authentifiés à enregistrer des conférences.

- **Audio/vidéo** Spécifiez si les participants peuvent utiliser l’audio et la vidéo :

  - **Aucun** Sélectionnez cette option pour empêcher l’utilisation de l’audio et de la vidéo.

  - **Activer l’audio IP** Sélectionnez cette option pour autoriser l’utilisation de l’audio, mais pas de la vidéo.

  - **Activer l’audio/la vidéo IP** Sélectionnez cette option pour autoriser l’audio et la vidéo.

- **Activer la conférence d’accès PSTN** Si vous avez activé l’audio en **audio/vidéo,** activez cette case à cocher pour autoriser les utilisateurs à se rendre aux conférences à l’aide du réseau téléphonique commuté (PSTN).

- **Autoriser les participants anonymes à composer un numéro** Cochez cette case si vous autorisez les utilisateurs à participer à des conférences et que vous souhaitez autoriser les utilisateurs non authentifiés (anonymes) à participer à une conférence à l’aide d’un appel sortant. Avec cette fonctionnalité, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour participer à la conférence.

- **Autoriser les participants non activés pour Voix Entreprise appels sortants** Si vous avez activé l’audio dans **audio/vidéo,** activez cette case à cocher pour autoriser les utilisateurs qui ne sont pas activés pour Voix Entreprise à participer à une conférence à l’aide d’un appel sortant. Avec la numérotation sortante, le serveur de conférence appelle l’utilisateur, puis il répond au téléphone pour participer à la conférence.

- **Autoriser plusieurs flux vidéo** Si vous avez activé la vidéo en **audio/vidéo,** activez cette case à cocher pour permettre aux utilisateurs d’organiser des conférences avec la vidéo de la vue Galerie. Lorsque cette case à cocher est sélectionnée, ce paramètre permet aux utilisateurs d’organiser des conférences qui envoient plusieurs flux vidéo. Lorsque cette case à cocher n’est pas sélectionnée, les utilisateurs peuvent uniquement organiser des conférences qui envoient un flux vidéo unique.

    > [!NOTE]
    > Cette option détermine le type de flux vidéo pris en charge par la conférence. Il ne détermine pas si les participants peuvent recevoir plusieurs flux vidéo. L’option Activer **la participation des participants à** plusieurs flux vidéo détermine si les participants peuvent recevoir plusieurs flux vidéo.

- **Collaboration de données** Spécifiez si la conférence autorise ou non la collaboration de données. Les options sont **Aucune ou** Activer la collaboration **de données.**

    Les paramètres suivants s’appliquent à la collaboration de données :

  - **Autoriser les participants fédérés et anonymes à télécharger du contenu** Si vous autorisez la collaboration de données, cochez cette case pour autoriser les utilisateurs externes et non authentifiés à télécharger du contenu, tel que des diapositives ou des présentations, à partir d’une conférence.

  - **Autoriser les participants à transférer des fichiers** Si vous autorisez la collaboration de données, cochez cette case pour autoriser les transferts de fichiers à tous les participants pendant une conférence.

  - **Activer les annotations** Si vous autorisez la collaboration de données, cochez cette case pour permettre aux participants d’effectuer des annotations à l’écran sur le contenu partagé pendant la conférence.

  - **Activer PowerPoint annotations** Si vous autorisez l’annotation, cochez cette case pour permettre aux participants d’effectuer des annotations dans PowerPoint diapositives partagées pendant la conférence.

  - **Activer les sondages** Si vous autorisez la collaboration de données, cochez cette case pour autoriser les participants à organiser un sondage pendant une conférence.

- **Partage d’application** Spécifiez si la conférence autorise ou non le partage d’application. Les options sont **Désactiver le partage d’application ou** Activer le partage **d’application.**

    Les paramètres suivants s’appliquent au partage d’application :

  - **Autoriser les participants à prendre le contrôle** Si vous autorisez le partage d’application, cochez cette case pour permettre aux participants de prendre le contrôle des applications ou des bureaux partagés pendant la conférence.

  - **Autoriser les participants fédérés et anonymes à prendre le contrôle** Si vous autorisez le partage d’application, cochez cette case pour autoriser les participants externes et non authentifiés à prendre le contrôle des applications ou des bureaux partagés pendant la conférence.

- **Stratégie de participant** Les paramètres de cette section s’appliquent aux utilisateurs en tant que participants à une conférence ou à une session à deux participants. Étant donné que les paramètres suivants sont des paramètres par utilisateur, un utilisateur d’une conférence ou d’une session à deux personnes peut avoir des fonctionnalités différentes de celles d’un autre utilisateur de la même conférence ou d’une même session à deux personnes.

    Cliquez sur la flèche vers le haut ou vers le bas à côté de l’étiquette pour fermer ou ouvrir la section.

- Sélectionnez **Activer le partage d’application** et de bureau pour permettre aux utilisateurs de partager des applications ou leur bureau tout en participant à une conférence ou à une session à deux participants. Sélectionnez **Désactiver le partage d’application** et de bureau pour empêcher les utilisateurs de partager des applications ou leur bureau lors de la participation à une conférence ou à une session à deux participants.

- **Activer le transfert de fichiers d’égal à égal** Cochez cette case pour autoriser les transferts de fichiers de personne à personne (c’est-à-dire, les transferts de fichiers qui n’impliquent pas tous les participants) au cours d’une conférence ou d’une session à deux personnes.

- **Activer l’enregistrement d’égal à égal** Cochez cette case pour autoriser les utilisateurs à enregistrer des sessions à deux.

- **Permettre aux participants de participer avec plusieurs flux vidéo** Cochez cette case pour autoriser les participants à recevoir la vidéo de la vue Galerie dans les conférences qui l’autorisent. Si cette option n’est pas sélectionnée, les participants ne peuvent recevoir qu’un seul flux vidéo indépendamment de ce que la conférence autorise.

    > [!NOTE]
    > La **vidéo Autoriser plusieurs flux vidéo** détermine si une conférence autorise plusieurs flux vidéo.

Pour plus d’informations sur les fonctionnalités de conférence, voir [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de conférence, voir [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) dans la documentation des opérations.