---
title: Composants de connectivité PSTN dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Découvrez les passerelles PSTN et les passerelles SIP pour les Voix Entreprise dans Skype Entreprise Server.
---

# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Composants de connectivité PSTN dans Skype Entreprise Server
 
Découvrez les passerelles PSTN et les passerelles SIP pour les Voix Entreprise dans Skype Entreprise Server.
  
Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (PSTN) avec une qualité de service constante. En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels. De leur point de vue, un appel entre l’infrastructure Voix Entreprise et le RTC doit ressembler à toute autre session SIP.
  
Pour les connexions PSTN, vous pouvez déployer une connexion SIP ou une passerelle PSTN (avec un PBX, également appelé lien SIP direct, ou sans PBX).
  
## <a name="sip-trunking"></a>Jonction SIP

Une alternative à l’utilisation des passerelles PSTN consiste à connecter votre solution Voix Entreprise au PSTN à l’aide d’une jonction SIP. La jonction SIP autorise les scénarios suivants :
  
- Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau PSTN en tant que service du fournisseur de services correspondant.
    
- Chaque abonné PSTN peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) associé à cet utilisateur.
    
L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP. 
  
## <a name="pstn-gateways"></a>Passerelles PSTN

Les passerelles PSTN sont des périphériques tiers qui traduisent la signalisation et le trafic multimédia entre l’infrastructure Voix Entreprise et un PSTN ou un PBX. Les passerelles PSTN fonctionnent avec le serveur de médiation pour présenter un appel PSTN ou PBX à un client Voix Entreprise. Le serveur de médiation présente également des appels de clients Voix Entreprise à la passerelle PSTN pour le routage vers le PSTN ou le PBX. Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des appareils qui fonctionnent Skype Entreprise Server, consultez le site [Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Autocommutateurs privés (PBX, Private branch exchange)

 Si vous avez une infrastructure vocale existante qui utilise un pbX (private branch exchange), vous pouvez utiliser votre PBX avec Voix Entreprise.
  
Les scénarios d’intégration Voix Entreprise-PBX pris en charge sont les suivants :
  
- IP-PBX qui prend en charge le contournement de média, avec un serveur de médiation.
    
- IP-PBX qui requiert une passerelle PSTN autonome.
    
- PBX TDM (multiplexage temporel), avec une passerelle PSTN autonome.
    
> [!NOTE]
> Le contournement de média n’interagit pas avec chaque passerelle PSTN, système IP-PBX et contrôleur de session en périphérie (SBC). Microsoft a testé un ensemble de passerelles PSTN et de SCS avec des partenaires certifiés et a effectué des tests avec des PBX IP Cisco. Le contournement de média est pris en charge uniquement avec les produits et versions répertoriés dans [le programme Unified Communications Open Interoperability Program - Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). 
  
Pour plus d’informations sur les partenaires qui proposent des solutions Voix Entreprise, consultez le site [Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Pour plus d’informations sur les partenaires qui proposent Voix Entreprise solutions matérielles, y compris les passerelles PSTN, consultez le site [Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
