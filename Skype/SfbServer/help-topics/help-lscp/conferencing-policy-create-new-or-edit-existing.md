---
title: Stratégie de conférence créer ou modifier une existant
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: Une stratégie de conférence définit les fonctionnalités et les fonctions à la disposition des utilisateurs lors d’une conférence (également appelée « réunion »).
ms.openlocfilehash: 6dbdb4a300e899e5172785cc08b081852a2c9742
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23262350"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Stratégie de conférence : création d’une stratégie ou modification d’une création existante

Une stratégie de conférence définit les fonctionnalités et les fonctions à la disposition des utilisateurs lors d’une conférence (également appelée « réunion »).

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Étendue** Identifie l’étendue de la stratégie de conférence que vous créez ou modifiez : globale, site ou utilisateur.

- **Nom** Chaque stratégie de conférence requiert un nom. Stratégies de conférence globaux et de site sont nommées par défaut, et le nom ne peut pas être modifié. Des stratégies de conférence utilisateur, utilisez un nom descriptif qui identifie l’utilisateur ou un groupe d’utilisateurs.

    > [!NOTE]
    > Une fois que vous avez enregistré la stratégie de conférence, son nom ne peut plus être modifié.

- **Description** Ce champ est facultatif. Utilisez-le pour fournir plus d’informations sur la stratégie de conférence.

- **Stratégie de l’organisateur** Les paramètres de cette section s’appliquent à l’utilisateur qui organise une conférence. Si un paramètre est sélectionné, l’utilisateur peut organiser une conférence ayant la caractéristique spécifiée. Si un paramètre n’est pas sélectionné, l’utilisateur ne peut pas organiser une conférence avec cette caractéristique. Ces paramètres ne déterminent pas ce que l’utilisateur a accès en tant que participant dans les conférences.

    Cliquez sur la flèche vers le haut ou la flèche vers le bas en regard de l’étiquette pour fermer ou ouvrir la section.

- **Taille de la réunion au maximum** le nombre maximal d’utilisateurs qui sont autorisés à une conférence. Par défaut, la taille maximale de la réunion est de 250.

- **Autoriser les participants à inviter des utilisateurs anonymes** Activez cette case à cocher Autoriser les utilisateurs à inviter des utilisateurs anonymes aux conférences. Les utilisateurs anonymes sont des utilisateurs qui n’ont pas d’informations d’identification dans des Services votre organisation de domaine Active Directory et qui, par conséquent, ne sont pas authentifiés.

- **Enregistrement** Spécifier si les participants peuvent enregistrer les conférences. Les options sont **None** ou **Activer l’enregistrement**.

- **Autoriser fédérés et les participants anonymes à enregistrer** Activez cette case à cocher pour autoriser les participants externes et non authentifiés aux conférences d’enregistrement.

- **Audio/vidéo** Spécifier si les participants peuvent utiliser les paramètres audio / vidéo :

  - **Aucun** Sélectionnez cette option pour empêcher l’utilisation des fonctionnalités audio et vidéo.

  - **Audio sur IP activer** Sélectionnez cette option pour permettre l’utilisation de l’audio mais pas de la vidéo.

  - **Enable IP audio/vidéo** Sélectionnez cette option pour autoriser les fonctionnalités audio et vidéo.

- **Conférence rendez-vous PSTN activer** Si vous avez activé audio dans **Audio/vidéo**, activez cette case à cocher pour permettre aux utilisateurs de joindre des conférences à l’aide du réseau téléphonique commuté (RTC).

- **Autoriser les participants anonymes pour les appels sortants** Activez cette case à cocher si vous permettez aux utilisateurs de joindre des conférences et que vous souhaitez autoriser les utilisateurs (anonymes) non authentifiés à participer à une conférence à l’aide de diffuser un appel. Avec cette fonctionnalité, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour participer à la conférence.

- **Autoriser les participants non activés pour Enterprise Voice pour les appels sortants** Si vous avez activé audio dans **Audio/vidéo**, activez cette case à cocher pour autoriser les utilisateurs qui ne sont pas activés pour Enterprise Voice pour participer à une conférence à l’aide d’appel sortant. Avec les appels sortants lorsque la conférence server téléphones l’utilisateur, puis l’utilisateur répond à rejoindre la conférence.

- **Autoriser plusieurs flux vidéo** Si vous avez activé la vidéo dans **Audio/vidéo**, activez cette case à cocher pour permettre aux utilisateurs d’organiser des conférences avec vidéo de la vue Galerie. Lorsque cette case à cocher est activée, ce paramètre permet aux utilisateurs d’organiser des conférences qui envoient plusieurs flux vidéo. Lorsque cette case à cocher n’est pas sélectionnée, les utilisateurs peuvent uniquement organiser des conférences qui envoient un flux vidéo.

    > [!NOTE]
    > Cette option détermine le type de flux vidéo pris en charge par la conférence. Il ne détermine pas si les participants peuvent recevoir plusieurs flux vidéo. L’option **Autoriser les participants à rejoindre plusieurs flux de données vidéo** détermine si les participants peuvent recevoir plusieurs flux vidéo.

- **Collaboration de données** Spécifiez si la conférence permet de collaboration de données. Les options sont **None** ou **Activer la collaboration de données**.

    Les paramètres ci-dessous concernent la collaboration de données :

  - **Autoriser fédérés et des participants anonymes à télécharger du contenu** Si vous autorisez la collaboration de données, activez cette case à cocher pour permettre aux utilisateurs externes et non authentifiés à télécharger du contenu, tels que des diapositives ou des documents, d’une conférence.

  - **Autoriser les participants à transférer des fichiers** Si vous autorisez la collaboration de données, activez cette case à cocher pour autoriser les transferts de fichiers vers tous les participants pendant une conférence.

  - **Activer les annotations** Si vous autorisez la collaboration de données, activez cette case à cocher pour autoriser les participants à effectuer à l’écran annotations sur le contenu partagé au cours de la conférence.

  - **Annotations PowerPoint activer** Si vous autorisez les annotations, activez cette case à cocher pour autoriser les participants à effectuer des annotations dans les diapositives PowerPoint partagées au cours de la conférence.

  - **Activer les sondages** Si vous autorisez la collaboration de données, activez cette case à cocher pour autoriser les participants à effectuer un sondage pendant une conférence.

- **Partage d’application** Spécifiez si la conférence permet le partage d’application. Les options sont **désactiver le partage d’application** ou **Activer le partage d’application**.

    Les paramètres ci-dessous concernent le partage d’application :

  - **Autoriser les participants à prendre le contrôle** Si vous autorisez le partage d’application, activez cette case à cocher pour autoriser les participants à prendre le contrôle des applications ou bureaux partagés au cours de la conférence.

  - **Autoriser fédérés et des participants anonymes à prendre le contrôle** Si vous autorisez le partage d’application, activez cette case à cocher pour autoriser les participants externes et non authentifiés à prendre le contrôle des applications ou bureaux partagés au cours de la conférence.

- **Stratégie de participant** Les paramètres de cette section s’appliquent aux utilisateurs en tant que participants dans une conférence ou une session à deux participants. Les paramètres suivants sont les paramètres par utilisateur, un utilisateur dans une conférence ou une session à deux participants peut avoir différentes fonctionnalités à un autre utilisateur dans la même conférence ou d’une session à deux participants.

    Cliquez sur la flèche vers le haut ou la flèche vers le bas en regard de l’étiquette pour fermer ou ouvrir la section.

- Sélectionnez **Activer le partage d’application et de Bureau** pour autoriser les utilisateurs à partager les applications et leur Bureau lorsqu’ils participent à une conférence ou à une session à deux participants. Sélectionnez **Désactiver le partage d’application et de Bureau** pour empêcher les utilisateurs de partager les applications et leur Bureau lorsqu’ils participent à une conférence ou à une session à deux participants.

- **Activer le transfert de fichiers d’égal à égal** Activez cette case à cocher pour autoriser les transferts de fichiers (c'est-à-dire, les transferts de fichiers qui n’impliquent pas tous les participants) pendant une conférence ou une session à deux participants.

- **Activer l’enregistrement d’égal à égal** Activez cette case à cocher Autoriser les utilisateurs à enregistrer les sessions impliquant deux parties.

- **Activer des personnes à participer à plusieurs flux vidéo** Activez cette case à cocher pour autoriser les participants recevoir la vidéo de la vue Galerie dans les conférences qui lui. Si cette option n’est pas sélectionnée, les participants peuvent recevoir uniquement un seul flux vidéo quel que soit ce qui permet la conférence.

    > [!NOTE]
    > L’option **Autoriser plusieurs flux de données vidéo** détermine si une conférence autorise plusieurs flux vidéo.

Pour plus d’informations sur les fonctionnalités de conférence et les fonctionnalités, voir [Vue d’ensemble de la conférence](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de conférence, voir [Stratégies de conférence](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) dans la documentation des opérations.


