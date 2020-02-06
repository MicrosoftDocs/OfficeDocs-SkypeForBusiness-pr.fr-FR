---
title: Estimation de l’utilisation et du trafic vocaux pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Vous pouvez utiliser la métrique suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.
ms.openlocfilehash: f324a3030a8265288a30062fdfc1040a1aea8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816063"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Estimation de l’utilisation et du trafic vocaux pour Skype entreprise Server
 
Vous pouvez utiliser la métrique suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.
  
> Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.
> 
> Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.
> 
> Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.
    
Le nombre de ports à son tour détermine le nombre de serveurs de médiation et de passerelles qui seront nécessaires. La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)
  
Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.
  

