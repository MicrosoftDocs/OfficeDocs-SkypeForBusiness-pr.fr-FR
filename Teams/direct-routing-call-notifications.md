---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notification d’appel de routage direct
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341804"
---
# <a name="manage-call-notifications"></a>Gérer les notifications d’appels

Cet article décrit comment gérer les notifications d’appel pour vos utilisateurs. Vous pouvez configurer des points de terminaison d’appel vers les deux équipes et vers un système de contrôle de succursale privée ou un contrôleur de bordure de session (SBC) tiers.  Cette fonction est utile, par exemple, si vous voulez envoyer un appel vers les téléphones mobiles et de bureau d’un utilisateur en même temps.   

Dans le diagramme suivant, l’utilisateur Irena possède deux points de terminaison :

- Un point de terminaison d’équipes
- Téléphone SIP connecté à une SBC tierce

Lorsqu’un appel arrive, le SBC dévie l’appel entre le routage direct du système téléphonique et le SBC tiers.


![Diagramme montrant les points de terminaison d’équipes branches](media/direct-routing-call-notification-1.png)

Si l’appel est accepté sur la fourche 2 (par la SBC tierce), teams générera une notification d’appel manqué.  

Vous pouvez empêcher la notification d’appel manqué en configurant l’SBC pour qu’il envoie une annulation sur Fork 1 comme suit :

RAISON : SIP ; cause = 200 ; texte "appel terminé ailleurs" 

Notez que l’appel n’est pas enregistré dans les enregistrements des détails des appels du système Microsoft Phone en tant qu’appel réussi. L’appel sera enregistré en tant que « tentative » avec le code SIP final « 487 », le sous-code final de Microsoft « 540200 » et l’expression de code SIP finale».  (Pour consulter les enregistrements des détails des appels, accédez au portail d’administration Teams, aux analyses et aux rapports, rapports d’utilisation et sélectionnez utilisation PSTN.)


Le diagramme ci-dessous illustre l’échelle SIP pour la fourche 1, décrit le flux d’appels et la raison attendue du message d’annulation. 

![Diagramme montrant les points de terminaison d’équipes branches](media/direct-routing-call-notification-2.png)
