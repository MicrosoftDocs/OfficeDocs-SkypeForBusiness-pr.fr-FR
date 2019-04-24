---
title: Edge des scénarios de serveur dans Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Résumé : Passez en revue ces scénarios pour vous aider à planifier votre topologie de serveur de transport Edge dans Skype Business Server.'
ms.openlocfilehash: 26bdb7e007c3ba0da6c5590db4c1e6953e43e701
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32208907"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Edge des scénarios de serveur dans Skype pour Business Server
 
**Résumé :** Passez en revue ces scénarios pour vous aider à planifier votre topologie de serveur de transport Edge dans Skype Business Server.
  
Nous avons certains diagrammes scénarios pour vous aider à visualiser et décider sur quels Skype pour la topologie de serveur de périphérie Business Server vous voulez implémenter. Une fois le scénario idéal sélectionné, vous pouvez effectuer des recherches sur les exigences environnementales devant être prises en compte. Nous allons commencer par les informations suivantes, applicables à tous les scénarios.
  
Ces chiffres, affichés à titre d’exemple uniquement (et contenant de ce fait des exemples de données IPv4 et IPv6), ne représentent pas le flux de communication réel, mais plutôt une vue d’ensemble du trafic potentiel. Les diagrammes des ports incluent également les détails des ports pour chaque scénario ci-dessous.
  
Les diagrammes indiquent .com pour l’interface externe et .net pour l’interface interne. Il s’agit également d’un exemple, et vos entrées peuvent bien sûr être entièrement différentes lors de la planification finale de votre serveur Edge.
  
Nous n’incluez pas le directeur (qui est un composant facultatif) dans un des diagrammes, mais vous pouvez en savoir plus sur qui séparément (mentionné dans d’autres rubriques de planification).
  
Comme mentionné ci-dessus, il est exemples de données IPv6 dans les diagrammes. La plupart de la documentation de [planification pour les déploiements de serveur de transport Edge dans Skype pour Business Server](edge-server-deployments.md) fait référence à IPv4, mais vous sont certainement pris en charge si vous souhaitez utiliser le protocole IPv6. Notez que vous aurez besoin des adresses IPv6 dans votre espace d’adresse attribué, et les utilisateurs ont besoin travailler avec l’adressage internes et externes, comme avec les adresses IP IPv4. Vous pouvez, grâce à Windows, utiliser la fonctionnalité de double pile, qui est une pile réseau distinctes pour IPv4 et IPv6. Il sera, si vous avez besoin, vous permettent d’affecter IPv4 et des adresses IPv6 simultanément.
  
Il existe des périphériques NAT qui autorisent pour NAT64 (IPv6 à IPv4) et NAT66 (IPv6 pour IPv6)), et il est valide pour une utilisation avec Skype pour Business Server.
  
> [!IMPORTANT]
> Si vous utilisez le contrôle d’admission des appels (CAC), vous devez utiliser IPv4 sur l’interface interne pour que celui-ci fonctionne correctement. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Consolidé Skype pour Business Server Edge Server avec privées des adresses IP et NAT

Dans ce scénario, il n’existe pas d’option de haute disponibilité. Ainsi, votre matériel sera moins coûteux et votre déploiement sera plus simple. Si la haute disponibilité est requise, reportez-vous aux scénarios de serveurs consolidés mis à l’échelle ci-dessous.
  
![Scénario de serveur Edge pour serveur Edge consolidé unique avec avec IP privée à l’aide de NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme pour les ports pour les serveurs de périphérie consolidé unique.
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé unique](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Consolidé Skype pour Business Server Edge Server avec des adresses IP publiques

Dans ce scénario, il n’existe pas d’option de haute disponibilité. Ainsi, votre matériel sera moins coûteux et votre déploiement sera plus simple. Si la haute disponibilité est requise, reportez-vous aux scénarios de serveurs consolidés mis à l’échelle ci-dessous.
  
![Scénario de serveur Edge pour serveur Edge consolidé unique avec avec IP publique](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme pour les ports pour les serveurs de périphérie consolidé unique.
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé unique](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Skype consolidée mise à l’échelle pour le pool d’entreprise serveur Edge, avec le système DNS charge équilibrage et privées des adresses IP et NAT

Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance, équilibrage de charge DNS avec IP privée à l’aide de NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme pour les pools Edge consolidés mis à l’échelle avec équilibrage de charge DNS.
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé avec montée en puissance à l’aide d’équilibrage de charge DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Les adresses IP publiques et l’équilibrage de charge Skype consolidée mise à l’échelle pour le pool d’entreprise serveur Edge, avec le système DNS

Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance, équilibrage de charge DNS avec IP publique](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme pour les pools Edge consolidés mis à l’échelle avec équilibrage de charge DNS.
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé avec montée en puissance à l’aide d’équilibrage de charge DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Mise à l’échelle consolidée Skype pour le pool d’entreprise serveur Edge, l’équilibrage de charge matérielle

Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance avec HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme pour les pools Edge consolidés mis à l’échelle avec équilibrage de charge matérielle
  
![Ports et protocoles du réseau de périmètre du serveur Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

