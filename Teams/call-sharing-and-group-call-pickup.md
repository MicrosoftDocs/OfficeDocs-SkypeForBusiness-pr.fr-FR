---
title: Partage d’appel et prise d’appel de groupe
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Les appels de partage et de groupe permettent aux utilisateurs de partager des appels entrants avec des collègues, de sorte que les appels puissent être capturés quand l’utilisateur n’est pas disponible.
ms.openlocfilehash: 97810336b55d6582a93eca04b832f2807073004a
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690810"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Partage d’appel et prise d’appel de groupe dans Microsoft Teams

Les fonctionnalités de partage d’appel et de cueillette de groupe de Microsoft teams permettent aux utilisateurs de partager leurs appels entrants avec leurs collègues pour permettre aux collègues de répondre aux appels qui se produisent alors que l’utilisateur n’est pas disponible.

Le regroupement des appels de groupe est moins gênant pour les destinataires que les autres formes de partage d’appel (par exemple, le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer le mode de notification d’un appel partagé entrant (par le biais d’une notification audio et visuelle, d’un élément visuel uniquement ou d’une bannière dans l’application Teams), et ils peuvent

Pour partager les appels, un utilisateur crée un groupe d’appels et ajoute les utilisateurs avec lesquels vous souhaitez partager leurs appels. Ils choisissent alors un paramètre de sonnerie ou de transfert simultané. Pour [en savoir plus, voir transfert d’appel et sonnerie simultanée dans teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .

> [!IMPORTANT]
> Les utilisateurs, le propriétaire du groupe d’appels et les membres du groupe d’appels doivent être en mode déploiement d’équipes uniquement. Pour plus d’informations sur les modes de déploiement d’équipes, voir comprendre les modes de déploiement de [Microsoft Teams, ainsi que la coexistence et l’interopérabilité de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Les utilisateurs doivent être compatibles voix entreprise pour configurer et utiliser le partage d’appel et le regroupement d’appels de groupe. Pour plus d’informations sur le modèle de gestion des licences, voir [Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="configure-group-call-pickup"></a>Configurer le prélèvement d’appels de groupe

Pour configurer la fonction de cueillette d’appel de groupe, un utilisateur configure d’abord un groupe d’appels (ce qui n’est pas le même qu’un groupe de sécurité ou un groupe Microsoft 365), puis ajoute les utilisateurs avec lesquels vous souhaitez partager leurs appels. Elle choisit ensuite un paramètre de sonnerie simultanée ou de transfert d’appel. Pour plus d’informations et pour obtenir des procédures pas à pas, voir [transfert d’appel et sonnerie simultanée dans teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Les préférences de création et de notification de groupe d’appels sont des fonctionnalités définies par l’utilisateur. les administrateurs n’ont pas besoin de configurer ces fonctionnalités pour leurs utilisateurs. Les groupes d’appels ne peuvent pas être créés à partir de groupes de sécurité ou de groupes Microsoft 365 ; ils doivent être créés dans Teams.

Les administrateurs doivent activer les groupes d’appels via le paramètre **TeamsCallingPolicy AllowCallGroups** pour un utilisateur. Les administrateurs peuvent également l’activer via le portail d’administration Teams.  Par ailleurs, l’utilisateur configuré peut également configurer directement ses groupes d’appels via le client. Les utilisateurs d’un administrateur ou d’un utilisateur final ne peuvent pas bloquer la configuration entre eux, mais le portail d’administration teams et le client teams doivent afficher cette relation avec précision dans les deux emplacements. 

Important : lorsque les administrateurs désactivent les groupes d’appels pour les utilisateurs (une fois qu’il est activé et que les relations du groupe d’appels sont configurées), les administrateurs doivent nettoyer les relations du groupe d’appels pour les utilisateurs dans le centre d’administration teams pour éviter un routage incorrect. 

## <a name="limitations"></a>Conditions

Un locataire peut contenir un maximum de groupes d’appels 32 768. Chaque groupe d’appels peut comporter un maximum de 25 utilisateurs. 

## <a name="more-information"></a>Plus d’informations

[Transfert d’appel et sonnerie simultanée dans teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
