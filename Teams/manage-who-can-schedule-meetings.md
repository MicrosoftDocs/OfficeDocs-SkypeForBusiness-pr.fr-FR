---
title: Gérer qui peut démarrer des réunions instantanées et planifier des réunions
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Découvrez comment utiliser les paramètres de stratégie de réunion Teams pour contrôler qui peut démarrer des réunions instantanées et planifier des réunions.
ms.openlocfilehash: 6736ecd20ef4b0e9eb082e83bd8212597da5f7ab
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466288"
---
# <a name="manage-who-can-start-instant-meetings-and-schedule-meetings"></a>Gérer qui peut démarrer des réunions instantanées et planifier des réunions

En tant qu’administrateur, vous pouvez limiter les utilisateurs qui peuvent démarrer des réunions instantanées et planifier des réunions dans Teams. Cela peut être particulièrement utile pour des raisons de confidentialité et de sécurité, où vous ne souhaitez pas que des utilisateurs particuliers configurent des réunions.

Les paramètres de stratégie de réunion sont activés par défaut. Ces paramètres se trouvent dans le Centre d’administration Teams sous **Stratégies de réunions** > .

- **Se réunir maintenant dans les canaux** : contrôle si un utilisateur peut démarrer une réunion instantanée dans un canal.
- **Planification des réunions** de canal : détermine si un utilisateur peut planifier une réunion dans un canal.
- **Planification de réunion privée** : détermine si un utilisateur peut planifier une réunion privée dans Teams. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.
- **Complément Outlook** : contrôle si un utilisateur peut planifier une réunion privée à partir d’Outlook. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.
- **Réunion maintenant dans des réunions privées** : contrôle si un utilisateur peut démarrer une réunion privée instantanée.

> [!NOTE]
> Si la réunion a été envoyée par un délégué, qui a reçu l’autorisation d’envoyer des invitations à la réunion pour le compte d’une autre personne, telle qu’un responsable, le paramètre de stratégie de réunion est appliqué à la personne qui a accordé l’autorisation (le responsable).

## <a name="channel-meetings"></a>Réunions de canal

Si vous avez des exigences de conformité qui imposent uniquement à des personnes spécifiques de démarrer des réunions de canal instantané et de planifier des réunions de canal, vous pouvez créer ou mettre à jour votre stratégie de réunion pour restreindre ces paramètres. Vous pouvez ensuite créer une stratégie distincte attribuée aux utilisateurs que vous souhaitez démarrer des réunions de canal instantanées et planifier des réunions de canal.

1. Dans le Centre d’administration Teams, accédez aux **stratégies** **réunions** >  et choisissez la stratégie à mettre à jour. Pour créer une stratégie, cliquez sur **Ajouter**.
1. Sous **Général**, basculez les éléments suivants :
    1. Si vous souhaitez restreindre qui peut démarrer des réunions instantanées dans un canal, **basculez La réunion maintenant dans les canaux** sur **Désactivé**.
    1. Si vous souhaitez restreindre les personnes autorisées à planifier des réunions dans un canal, basculez la **planification des réunions de canal** sur **Désactivé**.
1. **Appuyez sur Enregistrer** en bas de la page.

## <a name="private-meetings"></a>Réunions privées

Si vous avez des exigences de conformité qui imposent uniquement à des personnes spécifiques de démarrer des réunions privées instantanées et de planifier des réunions privées, vous pouvez créer ou mettre à jour vos stratégies de réunion pour restreindre ces paramètres. Vous pouvez ensuite créer une stratégie distincte attribuée aux utilisateurs que vous souhaitez démarrer des réunions instantanées et planifier des réunions privées.

1. Dans le Centre d’administration Teams, accédez aux **stratégies** **réunions** >  et choisissez la stratégie à mettre à jour. Pour créer une stratégie, cliquez sur **Ajouter**.
1. Sous **Général**, basculez les éléments suivants :
    1. Si vous souhaitez restreindre qui peut démarrer des réunions privées instantanées, **basculez La réunion maintenant dans les réunions privées** sur **Désactivé**.
    1. Si vous souhaitez limiter les personnes autorisées à planifier des réunions privées dans un canal, basculez la **planification des réunions privées** et le **complément Outlook sur** **Désactivé**.
1. **Appuyez sur Enregistrer** en bas de la page.

## <a name="turning-off-meeting-policy-settings"></a>Désactivation des paramètres de stratégie de réunion

Une fois ces paramètres de stratégie de réunion désactivés, tout utilisateur affecté à la stratégie ne pourra pas démarrer ou planifier des réunions de ce type. Les liens de participation à la réunion et les ID de conférence de toutes les réunions existantes de ce type que l’utilisateur avait précédemment démarrées ou planifiées ne fonctionneront pas. (Les conversations, fichiers, tableaux blancs, enregistrements, transcriptions et autres contenus liés à la réunion sont conservés et les utilisateurs peuvent toujours y accéder.)

Si un paramètre de stratégie de réunion est désactivé puis réactivé pour un utilisateur, toutes les réunions planifiées précédemment organisées par l’utilisateur deviennent actives et les personnes peuvent les rejoindre à l’aide du lien de participation à la réunion ou par téléphone.

## <a name="related-topics"></a>Rubriques connexes

[Modifier la date d’expiration de la réunion - Contrôles de l’utilisateur final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Limites et spécifications de Microsoft Teams](/microsoftteams/limits-specifications-teams)
