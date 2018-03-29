---
title: Routage interjonctions dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype pour Business Server Voix Entreprise prend en charge le routage inter-trunk.
ms.openlocfilehash: 58872fccca335792ccbdf03c2c8475c328197426
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="inter-trunk-routing-in-skype-for-business-server-2015"></a>Routage interjonctions dans Skype Entreprise Server 2015
 
Découvrez comment Skype pour Business Server Voix Entreprise prend en charge le routage inter-trunk.
  
Skype pour Business Server fournit la gestion de session de base par le biais de la prise en charge de la gamme intertrunk. Ainsi, Skype pour Business Server fournir des fonctionnalités de contrôle d’appel à des systèmes de téléphonie en aval. Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX. De même, Skype pour Business Server pouvez interconnecter deux ou plusieurs systèmes IP-PBX afin que les appels peuvent être placés et reçus entre téléphones PBX de différents systèmes IP-PBX. 
  
La figure suivante illustre la Skype pour Business Server fournissant l’interconnectivité entre une passerelle PSTN et un IP-PBX.
  
![Diagramme IP-PBX/Passerelle RTC connectant Lync Server](../../media/inter_trunk01.jpg)
  
La figure suivante illustre la Skype pour Business Server connexion de deux systèmes IP-PBX.
  
![Diagramme IP-PBX/Passerelle RTC interconnectant Lync Server](../../media/inter_trunk02.jpg)
  

