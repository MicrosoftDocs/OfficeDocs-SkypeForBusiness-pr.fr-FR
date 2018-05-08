---
title: Documents de connectivité PSTN dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: En savoir plus sur l’acheminement SIP et des passerelles PSTN pour Enterprise Voice sur Skype pour Business Server.
ms.openlocfilehash: 4f346209b483a3d469beba233bd22ee39e45745a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a>Documents de connectivité PSTN dans Skype Entreprise Server 2015
 
En savoir plus sur l’acheminement SIP et des passerelles PSTN pour Enterprise Voice sur Skype pour Business Server.
  
Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante. En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels. Point de vue de l’utilisateur, d’un appel entre l’infrastructure Enterprise Voice et le réseau RTC doit ressembler à toute autre session SIP.
  
Pour les connexions RTC, vous pouvez déployer une jonction SIP ou une passerelle RTC (avec un PBX, également appelé lien SIP direct, ou sans PBX).
  
## <a name="sip-trunking"></a>Jonction SIP

Comme alternative à l’utilisation de passerelles PSTN, vous pouvez connecter votre solution Enterprise Voice au RTC à l’aide de l’acheminement SIP. La jonction SIP autorise les scénarios suivants :
  
- Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau RTC en tant que service du fournisseur de services correspondant.
    
- Chaque abonné RTC peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) associé à cet utilisateur.
    
L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP. 
  
## <a name="pstn-gateways"></a>Passerelles RTC

Passerelles PSTN sont des périphériques tiers qui traduisent la signalisation et les médias entre l’infrastructure Enterprise Voice et un réseau RTC ou un PBX. Passerelles PSTN fonctionnent avec le serveur de médiation pour présenter un appel RTC ou PBX à un client Enterprise Voice. Le serveur de médiation présente également les appels de clients Enterprise Voice vers la passerelle PSTN pour le routage vers le RTC ou un PBX. Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des périphériques fonctionnant avec Skype pour Business Server, consultez [le site Web partenaires des Communications unifiées de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Autocommutateurs privés (PBX, Private branch exchange)

 Si vous disposez d’une infrastructure vocale existante qui utilise un autocommutateur privé (PBX), vous pouvez utiliser votre système PBX avec Enterprise Voice.
  
Les scénarios d’intégration voix entreprise-PBX pris en charge sont les suivantes :
  
- IP-PBX qui prend en charge le contournement de média, avec un serveur de médiation.
    
- IP-PBX qui requiert une passerelle RTC autonome.
    
- PBX TDM (multiplexage temporel), avec une passerelle RTC autonome.
    
> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé un ensemble de passerelles RTC et des contrôleurs SBC avec des partenaires certifiés et a effectué des tests avec des systèmes IP-PBX de Cisco. Le contournement de média est pris en charge uniquement avec les produits et les versions répertoriés au [Unified Communications programme Open Interoperability - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Pour plus d’informations sur les partenaires qui proposent des solutions voix entreprise, consultez le [site Web des partenaires des Communications unifiées de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Pour plus d’informations sur les partenaires qui proposent des solutions matérielles de voix entreprise, notamment des passerelles PSTN, consultez le [site Web des partenaires des Communications unifiées de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

