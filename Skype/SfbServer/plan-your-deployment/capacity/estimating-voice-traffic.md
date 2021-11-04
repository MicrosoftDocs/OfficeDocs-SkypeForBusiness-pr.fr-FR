---
title: Estimation de l’utilisation et du trafic des Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Vous pouvez utiliser la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.
ms.openlocfilehash: bfc5e35b839f3accc139f3f9a02fdb8436426462
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746850"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Estimation de l’utilisation et du trafic des Skype Entreprise Server
 
Vous pouvez utiliser la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.
  
> Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.
> 
> Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.
> 
> Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.
    
Le nombre de ports détermine à son tour le nombre de serveurs de médiation et de passerelles qui seront requis. La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)
  
Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.
  

