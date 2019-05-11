---
title: Routage entre les jonctions dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype pour Business Server Enterprise Voice prend en charge le routage entre les jonctions.
ms.openlocfilehash: 60e91003e9b1b70393f99ef2ce6d8021fa2e5010
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924219"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routage entre les jonctions dans Skype pour Business Server
 
Découvrez comment Skype pour Business Server Enterprise Voice prend en charge le routage entre les jonctions.
  
Skype pour Business Server assure la gestion de session de base par le biais de la prise en charge de routage d’inter-jonctions. Cela permet de Skype pour Business Server fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval. Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX. De même, Skype pour Business Server peut interconnect deux ou plusieurs systèmes IP-PBX afin que les appels peuvent être placés et reçus entre les téléphones PBX à partir de différents systèmes IP-PBX. 
  
La figure suivante illustre Skype pour Business Server fournissant une interconnectivité entre une passerelle PSTN et un IP-PBX.
  
![Diagramme IP-PBX/Passerelle RTC connectant Lync Server](../../media/inter_trunk01.jpg)
  
La figure suivante illustre Skype pour Business Server connectent deux systèmes IP-PBX.
  
![Diagramme IP-PBX/Passerelle RTC interconnectant Lync Server](../../media/inter_trunk02.jpg)
  

