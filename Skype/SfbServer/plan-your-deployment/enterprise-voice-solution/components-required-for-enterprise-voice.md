---
title: Composants requis pour Enterprise Voice sur Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un résumé des composants Enterprise Voice dans Skype pour Business Server.
ms.openlocfilehash: 800a12b2d83703f188fff04452cf865757d5cad9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970478"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Composants requis pour Enterprise Voice sur Skype pour Business Server
 
Un résumé des composants Enterprise Voice dans Skype pour Business Server.
  
Pour déployer Enterprise Voice, les composants suivants sont requis dans votre topologie. 
  
- Un ou plusieurs serveurs de médiation, qui traduit la signalisation et, dans certaines configurations, les médias entre votre interne Skype pour Business Server, l’infrastructure Enterprise Voice et une passerelle de réseau téléphonique commuté ou une Session Initiation Protocol Jonction (SIP). Les serveurs de médiation sont le plus important composant dans votre déploiement d’Enterprise Voice. Pour plus d’informations, voir [composant serveur de médiation dans Skype pour Business Server](mediation-server.md).
    
    Serveurs de médiation peuvent être colocalisés avec les serveurs frontaux ou installés en tant que serveurs autonomes.
    
- Des composants de connectivité PSTN, pouvant inclure des jonctions SIP ou des passerelles PSTN. Pour plus d’informations, consultez [composants de connectivité PSTN dans Skype pour Business Server](pstn-connectivity.md).
    
- Serveurs de périphérie, qui permet d’utiliser des fonctionnalités d’Enterprise Voice par vos utilisateurs lorsqu’ils sont en dehors du pare-feu de votre organisation. 
    
    Le service Edge d’accès fournit la signalisation SIP pour les appels Skype pour les utilisateurs professionnels qui sont trouvent en dehors du pare-feu de votre organisation. Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu. Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.
    
    Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.
    
- En outre, certains composants d’Enterprise Voice s’exécuter sur les serveurs frontaux. Pour plus d’informations sur ces composants, consultez [composants VoIP du serveur frontal pour Skype pour Business Server](front-end-server-voip.md)
    

