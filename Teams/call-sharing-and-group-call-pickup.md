---
title: Partage d’appel et prise d’appel de groupe
ms.author: serdars
author: SerdarSoysal
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
description: Le partage d’appel et le regroupement d’appels de groupe permet aux utilisateurs de partager des appels entrants avec des collègues afin de pouvoir capturer les appels en cas d’indisponibilité de l’utilisateur.
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620719"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Partage d’appel et prise d’appel de groupe dans Microsoft Teams

Les fonctionnalités de partage d’appel et d’appel de groupe de Microsoft Teams viennent laisser les utilisateurs partager leurs appels entrants avec des collègues afin que leurs collègues peuvent répondre à des appels qui se produisent alors que l’utilisateur n’est pas disponible.

Le regroupement d’appels est moins perturbateur pour les destinataires que d’autres formes de partage d’appel (telles que le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer la façon dont ils souhaitent être informés d’un appel partagé entrant (via une notification audio et visuelle, une bannière uniquement visuelle ou une bannière dans l’application Teams) et ils peuvent décider d’y répondre ou non.

Pour partager des appels avec d’autres personnes, un utilisateur crée un groupe d’appels et ajoute les utilisateurs avec qui il souhaite partager ses appels. Ils choisissent ensuite un paramètre de sonnerie ou de avance simultanée. Pour [plus d’informations, voir](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) Le forwarding d’appel et la sonnerie simultanée dans Teams. Notez que les appareils mobiles seront avertis uniquement s’ils sont réglés pour la bannière et la sonnerie.

> [!IMPORTANT]
> Les utilisateurs, le propriétaire du groupe d’appels et les membres du groupe d’appels doivent être en mode de déploiement de Teams uniquement. Pour plus d’informations sur les modes de déploiement de Teams, voir Comprendre [la coexistence](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et l’interopérabilité de Microsoft Teams et de Skype Entreprise

## <a name="license-required"></a>Licence requise

Les utilisateurs doivent être Voix Entreprise pour configurer et utiliser le partage d’appels et le regroupement d’appels. Pour plus d’informations sur le modèle de licence, consultez [la description du service Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="configure-group-call-pickup"></a>Configurer le regroupement d’appels de groupe

Pour configurer le regroupement d’appels de groupe, un utilisateur configure d’abord un groupe d’appels (ce groupe n’est pas identique à un groupe de sécurité ou à un groupe Microsoft 365), puis ajoute les utilisateurs avec qui ils souhaitent partager leurs appels. Ils choisissent ensuite un paramètre de sonnerie simultanée ou de avance d’appel. Pour plus d’informations et des procédures pas à pas, voir Le forwarding d’appel et [la sonnerie simultanée dans Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

Les préférences de création et de notification des groupes d’appels sont des fonctionnalités pilotées par l’utilisateur. administrateurs n’ont pas à configurer ces fonctionnalités pour leurs utilisateurs. Les groupes d’appels ne peuvent pas être créés à partir de groupes de sécurité ou de groupes Microsoft 365. ils doivent être créés dans Teams.

Les administrateurs doivent activer les groupes d’appels via le paramètre **TeamsCallingPolicy AllowCallGroups** d’un utilisateur. Les administrateurs peuvent également l’activer via le portail d’administration Teams.  En outre, l’utilisateur configuré peut également configurer ses groupes d’appels via le client directement. Les administrateurs ou les utilisateurs finaux ne peuvent pas bloquer la configuration l’un par l’autre, mais le portail d’administration teams et le client Teams doivent montrer cette relation avec précision aux deux endroits. 

Important : lorsque les administrateurs désactiver les groupes d’appels pour les utilisateurs (après l’avoir été désactivé et les relations de groupe d’appels sont configurées), les administrateurs doivent nettoyer les relations de groupe d’appels pour les utilisateurs dans le Centre d’administration Teams pour éviter un routage d’appel incorrect. 

## <a name="limitations"></a>Limitations

Un client peut contenir un maximum de 32 768 groupes d’appels. Chaque groupe d’appels peut avoir un maximum de 25 utilisateurs. 

## <a name="more-information"></a>Plus d’informations

[Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
