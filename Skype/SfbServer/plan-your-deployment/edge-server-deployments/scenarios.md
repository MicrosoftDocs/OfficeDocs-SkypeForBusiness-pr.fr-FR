---
title: Scénarios de serveur Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Résumé : Passez en revue ces scénarios pour vous aider à planifier votre topologie de serveur de transport Edge dans Skype Business Server 2015.'
ms.openlocfilehash: 30bce96e1764a608bf7bc8daeec3d918b9e5912c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-scenarios-in-skype-for-business-server-2015"></a>Scénarios de serveur Edge dans Skype Entreprise Server 2015
 
**Résumé :** Passez en revue ces scénarios pour vous aider à planifier votre topologie de serveur de transport Edge dans Skype Business Server 2015.
  
Nous avons certains diagrammes des scénarios pour vous aider à visualiser et à décider sur quel Skype pour la topologie de serveur de transport Edge Server entreprise vous souhaitez implémenter. Une fois le scénario idéal sélectionné, vous pouvez effectuer des recherches sur les exigences environnementales devant être prises en compte. Nous allons commencer par les informations suivantes, applicables à tous les scénarios.
  
Ces chiffres, affichés à titre d’exemple uniquement (et contenant de ce fait des exemples de données IPv4 et IPv6), ne représentent pas le flux de communication réel, mais plutôt une vue d’ensemble du trafic potentiel. Les diagrammes des ports incluent également les détails des ports pour chaque scénario ci-dessous.
  
Les diagrammes indiquent .com pour l’interface externe et .net pour l’interface interne. Il s’agit également d’un exemple, et vos entrées peuvent bien sûr être entièrement différentes lors de la planification finale de votre serveur Edge.
  
Nous ne pas inclure le directeur (qui est un composant facultatif) dans un des diagrammes, mais vous pouvez lire à ce sujet séparément (il est mentionné dans les autres rubriques de planification).
  
Comme indiqué ci-dessus, donnée exemple IPv6 dans les diagrammes. La plupart de la documentation dans le [Plan de déploiement de serveur de transport Edge dans Skype pour Business Server 2015](edge-server-deployments.md) fera référence à IPv4, mais vous sont certainement pris en charge si vous souhaitez utiliser IPv6. Notez que vous aurez besoin des adresses IPv6 dans votre espace d’adresse attribué, et doit utiliser l’adressage interne et externe, comme avec IPv4 IPs. Vous pouvez, grâce à Windows, utilisent la fonctionnalité de double pile, qui est une pile réseau distinctes pour IPv4 et IPv6. Ce sera, si vous avez besoin, vous permettent d’affecter IPv4 et des adresses IPv6 simultanément.
  
Il existe des périphériques NAT qui permettent de NAT64 (IPv6 à IPv4) et NAT66 (IPv6 sur IPv6)), ce qui est valide pour une utilisation avec Skype pour Business Server.
  
> [!IMPORTANT]
> Si vous utilisez le contrôle d’admission des appels (CAC), vous devez utiliser IPv4 sur l’interface interne pour que celui-ci fonctionne correctement. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Unique consolidée Skype pour le serveur de transport Edge Server entreprise privée des adresses IP et NAT

Dans ce scénario, il n’existe pas d’option de haute disponibilité. Ainsi, votre matériel sera moins coûteux et votre déploiement sera plus simple. Si la haute disponibilité est requise, reportez-vous aux scénarios de serveurs consolidés mis à l’échelle ci-dessous.
  
![Scénario de serveur Edge pour serveur Edge consolidé unique avec avec IP privée à l’aide de NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme des ports pour des serveurs Edge consolidée unique.
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé unique](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Unique consolidée Skype pour le serveur de transport Edge Server Business avec des adresses IP publiques

Dans ce scénario, il n’existe pas d’option de haute disponibilité. Ainsi, votre matériel sera moins coûteux et votre déploiement sera plus simple. Si la haute disponibilité est requise, reportez-vous aux scénarios de serveurs consolidés mis à l’échelle ci-dessous.
  
![Scénario de serveur Edge pour serveur Edge consolidé unique avec avec IP publique](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme des ports pour des serveurs Edge consolidée unique.
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé unique](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Skype consolidé à l’échelle pour le pool d’entreprise serveur Edge, avec DNS charge équilibrage et privés des adresses IP et NAT

Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance, équilibrage de charge DNS avec IP privée à l’aide de NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme pour les pools de bord consolidés à l’échelle avec l’équilibrage de la charge DNS.
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé avec montée en puissance à l’aide d’équilibrage de charge DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Skype consolidé à l’échelle pour le pool d’entreprise serveur Edge, avec DNS charge les adresses IP publiques et équilibrage

Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance, équilibrage de charge DNS avec IP publique](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme pour les pools de bord consolidés à l’échelle avec l’équilibrage de la charge DNS.
  
![Périmètre de réseau pour scénario de serveur Edge avec serveur Edge consolidé avec montée en puissance à l’aide d’équilibrage de charge DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Mise à l’échelle de Skype consolidée pour le pool d’entreprise serveur Edge, avec équilibrage de charge matériel

Dans ce scénario, vous disposez de l’option de haute disponibilité dans le déploiement de votre serveur Edge, ce qui vous offre des avantages en matière de prise en charge de l’extensibilité et du basculement.
  
![Scénario de serveur Edge pour serveur Edge consolidé avec montée en puissance avec HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a>Diagramme des ports

Nous avons également un diagramme pour les pools de bord consolidés à l’échelle avec l’équilibrage de charge matériel
  
![Ports et protocoles du réseau de périmètre du serveur Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

