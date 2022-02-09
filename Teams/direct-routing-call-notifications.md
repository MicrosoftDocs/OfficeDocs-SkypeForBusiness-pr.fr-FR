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
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notification d’appel de routage direct
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4af5d65a3d92fbe104b7c998cd8045b6fb52c653
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457184"
---
# <a name="manage-call-notifications"></a>Gérer les notifications d’appels

Cet article décrit comment gérer les notifications d’appel pour vos utilisateurs du routage direct. Vous pouvez configurer les points de terminaison d’appel sur un Teams Exchange et un système de branche privé (PBX) ou un contrôleur de session en bordure (SBC) tiers. Cette configuration est utile, par exemple, si vous voulez envoyer un appel vers les téléphones portables et de bureau d’un utilisateur en même temps.   

Dans le diagramme suivant, l’utilisateur Irena a deux points de terminaison :

- Un point Teams de terminaison
- Un téléphone SIP connecté à un SBC tiers

Lorsqu’un appel arrive, le SBC dus au routage direct et au SBC tiers.


![Diagramme montrant des points de Teams point de terminaison](media/direct-routing-call-notification-1.png)

Si l’appel est accepté sur la fork 2 (par le SBC tiers), Teams génère une notification « Appel manqué ».  

Vous pouvez empêcher la notification « Appel manqué » en configurant le SBC de manière à envoyer une annulation dans la fork 1 comme suit :

RAISON : SIP; cause=200;texte"Appel effectué ailleurs » 

L’appel n’est pas enregistré dans les enregistrements des détails des Teams Système téléphonique’un appel réussi. L’appel sera inscrit comme une « tentative » avec le code SIP final « 487 », le sous-code Microsoft final « 540200 » et la phrase du code SIP final « Appel effectué ailleurs ».  (Pour afficher les enregistrements des détails des appels,  ->  sélectionnez Teams d’administration > Rapports d’analyse et de **reportsusage**, puis sélectionnez **Utilisation PSTN**.)


Le diagramme ci-dessous illustre le flux SIP de la fork 1, explique le flux d’appels et la raison attendue dans le message Annuler. 

![Le diagramme affiche des points de Teams point de terminaison dus.](media/direct-routing-call-notification-2.png)
