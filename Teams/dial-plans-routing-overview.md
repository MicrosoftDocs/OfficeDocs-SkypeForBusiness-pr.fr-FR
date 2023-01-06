---
title: Plans de numérotation et routage Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Plans de numérotation et routage dans Microsoft Teams
ms.openlocfilehash: 1d8c4ed750369c6b5bf393ebceae850703f89395
ms.sourcegitcommit: 0a2476471713e1eba791060db2c8c888484033a7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69722114"
---
# <a name="microsoft-teams-dial-plans-and-routing"></a>Plans de numérotation et routage Microsoft Teams

Les articles de cette section décrivent les plans de numérotation et le routage des appels dans Microsoft Teams. 

- [Que sont les plans de numérotation](what-are-dial-plans.md)
- [Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)
- [Acheminer les appels vers des numéros non attribués](routing-calls-to-unassigned-numbers.md)

Les articles de cette section s’appliquent à toutes les options de connexion au réseau téléphonique commuté public (RTC) : forfait d’appels, connexion d’opérateur, téléphone mobile Teams et routage direct. Pour plus d’informations sur toutes les options de connectivité RTC, consultez [Options de connectivité RTC](pstn-connectivity.md).

Si vous choisissez Forfait d’appels, Connexion opérateur ou Téléphone mobile Teams, la plupart du routage des appels est géré par Microsoft ou votre fournisseur. Toutefois, le routage direct nécessite des étapes supplémentaires pour configurer le routage des appels. 

Pour le routage direct, vous devez configurer le routage des appels en spécifiant les itinéraires vocaux et en affectant des stratégies de routage vocal aux utilisateurs. Vous pouvez configurer des plans de numérotation pour la traduction de numéros au niveau de la jonction afin de garantir l’interopérabilité avec les contrôleurs de frontière de session (SBC). Pour plus d’informations, consultez [Configurer le routage vocal pour le routage direct](direct-routing-voice-routing.md), [Gérer les stratégies de routage vocal](manage-voice-routing-policies.md) et [Traduire des numéros de téléphone](direct-routing-translate-numbers.md).

N’oubliez pas que vous pouvez affecter une stratégie de routage vocal en ligne de routage direct aux utilisateurs du plan d’appel et de la connexion opérateur. Vous pouvez effectuer cette opération, par exemple, pour permettre aux utilisateurs de se connecter directement à un centre d’appels. Vous pouvez configurer une jonction de routage direct vers le centre d’appels.

Si un utilisateur dispose d’une licence de forfait d’appels, par exemple, les appels sortants de cet utilisateur sont automatiquement routés via l’infrastructure RTC du plan d’appels Microsoft. Si vous configurez et affectez une stratégie de routage vocal en ligne de routage direct à l’utilisateur, les appels sortants de l’utilisateur sont vérifiés pour déterminer si le numéro composé correspond à un modèle de numéro défini dans la stratégie de routage vocal en ligne. S’il existe une correspondance, l’appel est routé via la jonction de routage direct. S’il n’y a pas de correspondance, l’appel est routé via l’infrastructure PSTN du plan d’appels.

Pour plus d’informations, consultez [Considérations relatives à la stratégie de routage vocal de routage direct](direct-routing-voice-routing.md#voice-routing-policy-considerations).



