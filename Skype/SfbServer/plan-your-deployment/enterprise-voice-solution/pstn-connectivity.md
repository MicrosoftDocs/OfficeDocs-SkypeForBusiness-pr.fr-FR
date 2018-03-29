---
title: Documents de connectivité PSTN dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: En savoir plus sur SIP trunking et passerelles RTPC pour Voix Entreprise dans Skype pour Business Server.
ms.openlocfilehash: 051066643649f9f8f872f4a2795e5ea71417d810
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a>Documents de connectivité PSTN dans Skype Entreprise Server 2015
 
En savoir plus sur SIP trunking et passerelles RTPC pour Voix Entreprise dans Skype pour Business Server.
  
Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante. En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels. Du point de vue de l’utilisateur, un appel entre l’infrastructure de Voix Entreprise et RTC doit sembler à une autre session SIP.
  
Pour les connexions RTC, vous pouvez déployer une jonction SIP ou une passerelle RTC (avec un PBX, également appelé lien SIP direct, ou sans PBX).
  
## <a name="sip-trunking"></a>Jonction SIP

Comme alternative à l’utilisation des passerelles RTPC, vous pouvez connecter votre solution Voix Entreprise au RTC, à l’aide de SIP trunking. La jonction SIP autorise les scénarios suivants :
  
- Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau RTC en tant que service du fournisseur de services correspondant.
    
- Chaque abonné RTC peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) associé à cet utilisateur.
    
L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP. 
  
## <a name="pstn-gateways"></a>Passerelles RTC

Passerelles RTPC sont les périphériques tiers qui traduisent de signalisation et multimédias entre l’infrastructure de Voix Entreprise et un RTC ou un PBX. Passerelles RTPC fonctionnent avec le serveur de médiation pour présenter un appel PSTN ou PBX à un client de Voix Entreprise. Le serveur de médiation présente également des appels de clients de Voix Entreprise vers la passerelle RTC pour le routage vers le PSTN ou PBX. Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des périphériques qui fonctionnent avec Skype pour Business Server, consultez [le site Web partenaires de Microsoft Unified Communications](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Autocommutateurs privés (PBX, Private branch exchange)

 Si vous avez une infrastructure vocale qui utilise un autocommutateur privé (PBX), vous pouvez utiliser votre PBX avec Voix Entreprise.
  
Les scénarios d’intégration PBX Voix Entreprise pris en charge sont les suivantes :
  
- IP-PBX qui prend en charge le contournement de média, avec un serveur de médiation.
    
- IP-PBX qui requiert une passerelle RTC autonome.
    
- PBX TDM (multiplexage temporel), avec une passerelle RTC autonome.
    
> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé un ensemble de passerelles RTC et des contrôleurs SBC avec des partenaires certifiés et a effectué des tests avec des systèmes IP-PBX de Cisco. Le contournement de média est pris en charge uniquement avec les produits et versions répertoriées au [Unified Communications Ouvrir programme d’interopérabilité - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Pour plus d’informations sur les partenaires qui proposent des solutions de Voix Entreprise, consultez le [site Web des partenaires de Microsoft Unified Communications](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Pour plus d’informations sur les partenaires qui proposent des solutions matérielles de Voix Entreprise, y compris les passerelles RTPC, rendez-vous sur le [site Web des partenaires de Microsoft Unified Communications](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

