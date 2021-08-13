---
title: 'Teams : Gérer les notifications d’appel'
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
ms.openlocfilehash: 8326a9eb1f7a6ad9fb13c622c4f03d0f9af40af8
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233039"
---
# <a name="manage-call-notifications"></a>Gérer les notifications d’appels

Cet article décrit comment gérer les notifications d’appel pour vos utilisateurs. Vous pouvez configurer des points de terminaison d’appel sur un Teams Exchange et un système de branche privé (PBX) ou un contrôleur de session en bordure (SBC) tiers.  Cette configuration est utile, par exemple, si vous voulez envoyer un appel vers les téléphones portables et de bureau d’un utilisateur en même temps.   

Dans le diagramme suivant, l’utilisateur Irena a deux points de terminaison :

- Point de terminaison Teams point de terminaison
- Un téléphone SIP connecté à un SBC tiers

Lorsqu’un appel arrive, le SBC dut du début à la fin de l’appel entre Système téléphonique routage direct et le SBC tiers.


![Diagramme montrant des points de terminaison Teams dues](media/direct-routing-call-notification-1.png)

Si l’appel est accepté sur la fork 2 (par le SBC tiers), Teams génère une notification « Appel manqué ».  

Vous pouvez empêcher la notification « Appel manqué » en configurant le SBC de manière à envoyer une annulation dans la fork 1 comme suit :

RAISON : SIP; cause=200;texte"Appel effectué ailleurs » 

L’appel n’est pas enregistré dans les enregistrements des détails d’Téléphone Microsoft système en tant qu’appel réussi. L’appel sera inscrit comme une « tentative » avec le code SIP final « 487 », le sous-code Microsoft final « 540200 » et la phrase du code SIP final « Appel effectué ailleurs ».  (Pour afficher les enregistrements des détails des appels, sélectionnez Utilisation PSTN, Teams d’administration, les rapports d’analyse et de rapport d’utilisation, et sélectionnez Utilisation PSTN.)


Le diagramme ci-dessous illustre le flux SIP de la fork 1, explique le flux d’appels et la RAISON attendue dans le message Annuler. 

![Diagram shows forked Teams endpoints](media/direct-routing-call-notification-2.png)
