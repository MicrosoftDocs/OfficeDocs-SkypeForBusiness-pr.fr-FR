---
title: Routage inter-Trunk dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype entreprise Server Voice prend en charge le routage inter-Trunk.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276830"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routage inter-Trunk dans Skype entreprise Server
 
Découvrez comment Skype entreprise Server Voice prend en charge le routage inter-Trunk.
  
Skype entreprise Server fournit une gestion de session de base grâce à la prise en charge du routage intertrunk. Cela permet à Skype entreprise Server de fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval. Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX. De la même façon, Skype entreprise Server peut interconnecter au moins deux systèmes IP-PBX pour que les appels puissent être placés et reçus entre les téléphones PBX des différents systèmes IP PBX. 
  
La figure suivante illustre Skype entreprise Server permettant une interconnexion entre une passerelle RTC et un PBX IP.
  
![Diagramme IP-PBX/Passerelle RTC connectant Lync Server](../../media/inter_trunk01.jpg)
  
La figure suivante illustre Skype entreprise Server connectant deux systèmes PBX IP.
  
![Diagramme IP-PBX/Passerelle RTC interconnectant Lync Server](../../media/inter_trunk02.jpg)
  

