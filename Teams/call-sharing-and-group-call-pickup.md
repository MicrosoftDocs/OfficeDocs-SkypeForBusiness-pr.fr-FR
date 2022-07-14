---
title: Partage d’appel et prise d’appel de groupe
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Le partage d’appels et la prise en charge des appels de groupe permettent aux utilisateurs de partager des appels entrants avec des collègues afin que les appels puissent être capturés lorsque l’utilisateur n’est pas disponible.
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789949"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Partage d’appel et prise d’appel de groupe dans Microsoft Teams

Les fonctionnalités de partage d’appels et de prise en charge des appels de groupe de Microsoft Teams permettent aux utilisateurs de partager leurs appels entrants avec des collègues afin que les collègues puissent répondre aux appels qui se produisent lorsque l’utilisateur n’est pas disponible.

La prise en charge des appels de groupe est moins perturbatrice pour les destinataires que les autres formes de partage d’appels (comme le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer la façon dont ils souhaitent être avertis d’un appel partagé entrant (par le biais d’une notification audio et visuelle, d’un visuel uniquement ou d’une bannière dans l’application Teams) et ils peuvent décider s’ils doivent y répondre.

Pour partager des appels avec d’autres personnes, un utilisateur crée un groupe d’appels et ajoute les utilisateurs avec lesquels il souhaite partager ses appels. Ensuite, ils choisissent un paramètre d’anneau ou de transfert simultané. Pour plus [d’informations, consultez transfert d’appel et sonnerie simultanée dans Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) . Notez que les appareils mobiles ne seront avertis que s’ils sont définis pour la bannière et la sonnerie.

> [!IMPORTANT]
> Les utilisateurs, le propriétaire du groupe d’appels et les membres du groupe d’appels doivent être en mode de déploiement Teams uniquement. Pour plus d’informations sur les modes de déploiement Teams, consultez [Comprendre Microsoft Teams et Skype Entreprise coexistence et interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licence requise

Une licence système Téléphonie Microsoft Teams doit être attribuée aux utilisateurs pour configurer et utiliser le partage d’appels et la prise d’appel de groupe. Pour plus d’informations sur le modèle de licence, consultez ce [que vous obtenez avec le système téléphonique](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="configure-group-call-pickup"></a>Configurer la prise d’appel de groupe

Pour configurer la prise d’appel de groupe, un utilisateur configure d’abord un groupe d’appels (ce n’est pas le même qu’un groupe de sécurité ou un groupe Microsoft 365), puis ajoute les utilisateurs avec lesquels il souhaite partager ses appels. Ensuite, ils choisissent un paramètre de sonnerie ou de transfert d’appel simultané. Pour plus d’informations et pour connaître les procédures pas à pas, consultez [transfert d’appel et sonnerie simultanée dans Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Les préférences de création et de notification des groupes d’appels sont des fonctionnalités pilotées par l’utilisateur ; les administrateurs n’ont pas à configurer ces fonctionnalités pour leurs utilisateurs. Les groupes d’appels ne peuvent pas être créés à partir de groupes de sécurité ou de groupes Microsoft 365 ; ils doivent être créés dans Teams.

Les administrateurs doivent activer les groupes d’appels via le paramètre **TeamsCallingPolicy AllowCallGroups** pour un utilisateur. Les administrateurs peuvent également l’activer via le portail Teams Administration.  En outre, l’utilisateur configuré peut également configurer ses groupes d’appels via le client directement. Administration ou les utilisateurs finaux ne peuvent pas bloquer la configuration les uns par les autres, mais teams Administration portail et le client Teams doivent afficher cette relation avec précision dans les deux endroits. 

Important : lorsque les administrateurs désactivent les groupes d’appels pour les utilisateurs (une fois qu’ils ont été activés et que les relations de groupe d’appels sont configurées), les administrateurs doivent nettoyer les relations de groupe d’appels pour les utilisateurs du Centre d’administration Teams afin d’éviter un routage d’appel incorrect. 

## <a name="limitations"></a>Limites

Chaque groupe d’appels configuré peut comporter un maximum de 25 utilisateurs ou 32 768 caractères. 

## <a name="more-information"></a>Plus d’informations

[Transfert d’appel et sonnerie simultanée dans Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
