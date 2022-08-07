---
title: Gérer les notifications d’appel pour le routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notification d’appel de routage direct
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268429"
---
# <a name="manage-call-notifications"></a>Gérer les notifications d’appels

Cet article explique comment gérer les notifications d’appel pour vos utilisateurs de routage direct. Vous pouvez configurer des points de terminaison d’appel à la fois pour Teams et pour un contrôleur SBC (Private Branch Exchange) ou SBC (Session Border Controller) tiers. Cette configuration est utile, par exemple, si vous souhaitez envoyer un appel aux téléphones mobiles et de bureau d’un utilisateur en même temps.   

Dans le diagramme suivant, l’utilisateur Irena a deux points de terminaison :

- Un point de terminaison Teams
- Un téléphone SIP connecté à un SBC tiers

Lorsqu’un appel arrive, le SBC duplique l’appel entre le routage direct et le SBC tiers.


![Diagramme montrant les points de terminaison Teams dupliqués.](media/direct-routing-call-notification-1.png)

Si l’appel est accepté sur fork 2 (par le SBC tiers), Teams génère une notification « Appel manqué ».  

Vous pouvez empêcher la notification « Appel manqué » en configurant le SBC pour envoyer une commande Cancel on Fork 1 comme suit :

RAISON : SIP; cause=200;text"Call completed elsewhere » 

L’appel ne sera pas inscrit dans les enregistrements détaillés de l’appel du système téléphonique Teams en tant qu’appel réussi. L’appel sera inscrit en tant que « Tentative » avec le code SIP final « 487 », le sous-code Microsoft final « 540200 » et l’expression de code SIP finale « Appel terminé ailleurs ».  (Pour afficher les enregistrements des détails de l’appel, accédez au centre Administration Teams -> **Rapports d’utilisation d’analytique et de rapports** -> , puis sélectionnez **Utilisation RTC**.)


Le diagramme ci-dessous illustre l’échelle SIP pour fork 1, explique le flux d’appel et la raison attendue dans le message Cancel. 

![Diagramme montrant les points de terminaison Teams dupliqués.](media/direct-routing-call-notification-2.png)
