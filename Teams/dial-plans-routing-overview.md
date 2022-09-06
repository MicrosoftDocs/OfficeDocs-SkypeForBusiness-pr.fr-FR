---
title: Plans de numérotation et routage
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Plans de numérotation et routage dans Microsoft Teams
ms.openlocfilehash: 89332b5e5756bc33c92a67b641bab85b826bfe70
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606783"
---
# <a name="overview"></a>Vue d’ensemble

Les articles de cette section décrivent les plans de numérotation et le routage des appels dans Microsoft Teams. 

- [Qu’est-ce que les plans de numérotation ?](what-are-dial-plans.md)
- [Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)
- [Acheminer les appels aux engourdissements non attribués](routing-calls-to-unassigned-numbers.md)

Les articles de cette section s’appliquent à toutes les options de connexion au réseau téléphonique commuté (RTC) : forfait d’appels, connexion d’opérateur, Fournisseur de connectivité mobile (préversion publique) et routage direct. Pour plus d’informations sur toutes les options de connectivité RTC, consultez [les options de connectivité RTC](pstn-connectivity.md).

Si vous choisissez Forfait d’appels, Opérateur Connect ou Fournisseur de connectivité mobile, la plupart du routage des appels est géré par Microsoft ou votre fournisseur. Toutefois, le routage direct nécessite des étapes supplémentaires pour configurer le routage des appels. 

Pour le routage direct, vous devez configurer le routage des appels en spécifiant les itinéraires vocaux et en attribuant des stratégies de routage vocal aux utilisateurs. Vous pouvez configurer des plans de numérotation pour la traduction de numéros au niveau du tronçon pour garantir l’interopérabilité avec les contrôleurs de frontière de session (SBC). Pour plus d’informations, consultez [Configurer le routage vocal pour le routage direct](direct-routing-voice-routing.md), [Gérer les stratégies de routage vocal](manage-voice-routing-policies.md) et [Traduire les numéros de téléphone](direct-routing-translate-numbers.md).

N’oubliez pas que vous pouvez affecter une stratégie de routage vocal en ligne de routage direct aux utilisateurs du plan d’appel et de l’opérateur Connect. Vous souhaiterez peut-être effectuer cette opération, par exemple, pour permettre aux utilisateurs de se connecter directement à un centre d’appels. Vous pouvez configurer une jonction de routage direct vers le centre d’appels.

Si un utilisateur dispose d’une licence de plan d’appel, par exemple, les appels sortants de cet utilisateur sont automatiquement routés via l’infrastructure RTC du plan d’appels Microsoft. Si vous configurez et affectez une stratégie de routage vocal en ligne de routage direct à l’utilisateur, les appels sortants de l’utilisateur sont vérifiés pour déterminer si le numéro composé correspond à un modèle de nombre défini dans la stratégie de routage vocal en ligne. S’il existe une correspondance, l’appel est routée via la jonction de routage direct. En l’absence de correspondance, l’appel est routé via l’infrastructure RTC du plan d’appel.

Pour plus d’informations, consultez les [considérations relatives à la stratégie de routage vocal de routage direct](direct-routing-voice-routing.md#voice-routing-policy-considerations).



