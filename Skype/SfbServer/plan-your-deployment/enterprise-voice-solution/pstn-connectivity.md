---
title: Composants de connectivité PSTN dans Skype entreprise Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: En savoir plus sur le trunking SIP et les passerelles RTC pour Enterprise Voice dans Skype entreprise Server.
ms.openlocfilehash: 443f5425beeed5b032968837ac56ce3a26468cdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802534"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Composants de connectivité PSTN dans Skype entreprise Server
 
En savoir plus sur le trunking SIP et les passerelles RTC pour Enterprise Voice dans Skype entreprise Server.
  
Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante. En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels. Du point de vue de l’utilisateur, un appel entre l’infrastructure voix entreprise et le RTC devrait paraître une seule et même session SIP.
  
Pour les connexions RTC, vous pouvez déployer une jonction SIP ou une passerelle RTC (avec un PBX, également appelé lien SIP direct, ou sans PBX).
  
## <a name="sip-trunking"></a>Jonction SIP

À la place des passerelles RTC, vous pouvez connecter votre solution vocale d’entreprise au RTC en utilisant le trunking SIP. La jonction SIP autorise les scénarios suivants :
  
- Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau RTC en tant que service du fournisseur de services correspondant.
    
- Chaque abonné RTC peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) associé à cet utilisateur.
    
L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP. 
  
## <a name="pstn-gateways"></a>Passerelles RTC

Les passerelles RTC sont des appareils tiers qui convertissent le signalement et le contenu multimédia entre l’infrastructure voix entreprise et un réseau PBX ou PSTN. Les passerelles RTC fonctionnent avec le serveur de médiation pour présenter un appel PSTN ou PBX à un client voix entreprise. Le serveur de médiation présente également des appels de clients voix entreprise vers la passerelle RTC pour le routage vers le RTC ou le PBX. Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des appareils compatibles avec Skype entreprise Server, voir [le site Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Autocommutateurs privés (PBX, Private branch exchange)

 Si vous disposez d’une infrastructure vocale existante qui utilise un système PBX, vous pouvez utiliser votre système PBX avec Enterprise Voice.
  
Les scénarios d’intégration PBX voix entreprise pris en charge sont les suivants :
  
- IP-PBX prenant en charge la dérivation multimédia, avec un serveur de médiation.
    
- IP-PBX qui requiert une passerelle RTC autonome.
    
- PBX TDM (multiplexage temporel), avec une passerelle RTC autonome.
    
> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. La dérivation de média est uniquement prise en charge avec les produits et les versions répertoriés dans [le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Pour plus d’informations sur les partenaires proposant des solutions voix entreprise, consultez le [site Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Pour plus d’informations sur les partenaires qui proposent des solutions matérielles voix entreprise, notamment les passerelles RTC, consultez le [site Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

