---
title: Partage d’appel et prise d’appel de groupe dans Microsoft Teams
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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Appeler le partage et de groupe ou d’appel permettre aux utilisateurs de partager les appels entrants avec vos collègues afin que les appels peuvent être capturés lorsque l’utilisateur n’est pas disponible.
ms.openlocfilehash: e822d06e48f3d7df548f0fd0d04645e7e9328598
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993580"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Partage d’appel et prise d’appel de groupe dans Microsoft Teams

L’appel de partage et le groupe d’appel pickup fonctionnalités de partage permettent aux utilisateurs de Microsoft Teams appels leur entrants avec vos collègues afin que les collègues peuvent répondre aux appels qui se produisent lorsque l’utilisateur n’est pas disponible.

Groupe ou d’appel est moins gênants aux destinataires que les autres types d’appel de partage (comme le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer qu’ils veulent être averti d’un appel entrant partagé (via la notification audio et vidéo, visual uniquement, ou des bannières dans l’application équipes), et ils peuvent décider s’il faut répondre à l’appel.

Pour partager des appels avec d’autres personnes, un utilisateur crée un groupe d’appel et ajoute les utilisateurs qu’ils souhaitent partager leurs appels avec. Puis ils choisir une sonnerie simultanée ou transférer le paramètre. Pour plus d’informations, voir [l’appel de sonnerie simultanée et de transfert dans les équipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .

> [!IMPORTANT]
> Les utilisateurs, le propriétaire du groupe appel et membres du groupe d’appel doivent être en mode de déploiement équipes uniquement. Pour plus d’informations sur les modes de déploiement d’équipes, voir [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Les utilisateurs doivent être Enterprise Voice est activé pour configurer et utiliser le partage d’appel et de groupe ou d’appel. Pour plus d’informations sur le modèle de licence, voir [Gestion des licences Office 365 pour les équipes Microsoft](office-365-licensing.md).

## <a name="configure-group-call-pickup"></a>Configurer le groupe ou d’appel

Pour configurer le groupe ou d’appel, un utilisateur configure d’abord un groupe d’appel (il n’est pas le même en tant qu’un groupe de sécurité ou un groupe d’Office 365), puis ajoute les utilisateurs qu’ils souhaitent partager leurs appels avec. Ensuite, ils choisir une sonnerie simultanée ou paramètres de transfert d’appel. Pour plus d’informations et procédures pas à pas, voir [appel sonnerie simultanée et de transfert dans les équipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Appels création d’un groupe et notification préférences sont effectuées par les utilisateurs des fonctionnalités ; les administrateurs inutile de configurer ces fonctionnalités pour les utilisateurs. Groupes d’appel ne peut pas être créés à partir des groupes de sécurité ou Office 365 ; ils doivent être créés dans les équipes.

Administrateurs doivent activer les groupes d’appel via le paramètre **TeamsCallingPolicy AllowCallGroups** pour un utilisateur. Les administrateurs peuvent contrôler uniquement si cet utilisateur peut configurer des groupes d’appel. Une fois que le bit est défini sur true, administrateurs ne peuvent pas empêcher les utilisateurs de configuration et en ajoutant les utilisateurs de groupe d’appel de leur choix.

## <a name="limitations"></a>Limitations

Un client peut contenir un maximum de groupes d’appel 32 768. Il peut y avoir un maximum de 5 utilisateurs de chaque groupe d’appel. 

## <a name="more-information"></a>Plus d’informations

[Transfert d’appel et la sonnerie simultanée dans les équipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)