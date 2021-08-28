---
title: Scénarios de serveur Edge dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Résumé : Examinez ces scénarios pour vous aider à planifier votre topologie de serveur Edge dans Skype Entreprise Server.'
ms.openlocfilehash: 213081e5e232ff2d033c556fa9e037cdf813da3a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622176"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Scénarios de serveur Edge dans Skype Entreprise Server
 
**Résumé :** Examinez ces scénarios pour vous aider à planifier votre topologie de serveur Edge dans Skype Entreprise Server.
  
Nous avons des diagrammes de scénarios pour vous aider à visualiser et à choisir la topologie Skype Entreprise Server serveur Edge que vous souhaitez implémenter. Une fois que vous avez choisi un bon candidat, vous pouvez consulter les exigences environnementales que vous devrez répondre. Les exemples suivants s’appliquent à tous les scénarios, c’est pourquoi nous le mentionnons en premier.
  
Ces chiffres, qui sont affichés à titre d’exemple uniquement (et qui contiennent des exemples de données IPv4 et IPv6), ne représentent pas le flux de communication réel, mais plutôt une vue d’ensemble de votre trafic possible. Les détails des ports sont également visibles dans les diagrammes de port pour chaque scénario ci-dessous.
  
Les diagrammes montrent .com pour l’interface externe et .net pour l’interface interne, qui est également un exemple de matériel ; Bien entendu, vos propres entrées peuvent être assez différentes lorsque vous rassemblez votre propre plan Edge final.
  
Nous n’incluons pas le directeur (qui est un composant facultatif) dans les diagrammes, mais vous pouvez en savoir plus séparément (il est mentionné dans d’autres rubriques de planification).
  
Comme indiqué ci-dessus, il existe des exemples de données IPv6 dans les diagrammes. La majeure partie de la documentation de plan pour les [déploiements](edge-server-deployments.md) de serveurs Edge dans Skype Entreprise Server fait référence à IPv4, mais vous êtes certainement pris en charge si vous souhaitez utiliser IPv6. Notez que vous aurez besoin d’adresses IPv6 dans votre espace d’adressare affecté et qu’elles devront fonctionner avec l’adressare interne et externe, comme avec les adresses IP IPv4. Grâce à Windows, vous pouvez utiliser la fonctionnalité double pile, qui est une pile réseau distincte pour IPv4 et IPv6. Cela vous permettra, si nécessaire, d’affecter simultanément des adresses IPv4 et IPv6.
  
Il existe des périphériques NAT qui autorisent NAT64 (IPv6 vers IPv4) et NAT66 (IPv6 vers IPv6)), et cela est valide pour une utilisation avec Skype Entreprise Server.
  
> [!IMPORTANT]
> Si vous utilisez le contrôle d’admission des appels (CAC), vous devez utiliser IPv4 sur l’interface interne pour qu’il fonctionne. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Serveur Edge consolidé unique Skype Entreprise Server avec adresses IP privées et NAT

Avec ce scénario, il n’existe aucune option pour la haute disponibilité. Cela signifie que vous dépensez moins sur le matériel et que vous avez un déploiement plus simple. Si la haute disponibilité est une valeur à prendre en compte, consultez les scénarios consolidés à l’échelle ci-dessous.
  
![Scénario edge pour un seul edge consolidé avec une adresse IP privée à l’aide de nat](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramme de port

Nous avons également un diagramme pour les ports pour les serveurs Edge consolidés.
  
![Périmètre réseau pour le périmètre unique consolidé du scénario Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Serveur Edge Skype Entreprise Server consolidé unique avec adresses IP publiques

Avec ce scénario, il n’existe aucune option pour la haute disponibilité. Cela signifie que vous dépensez moins sur le matériel et que vous avez un déploiement plus simple. Si la haute disponibilité est une valeur à prendre en compte, consultez les scénarios consolidés à l’échelle ci-dessous.
  
![Scénario edge pour un seul edge consolidé avec une adresse IP publique](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramme de port

Nous avons également un diagramme pour les ports pour les serveurs Edge consolidés.
  
![Périmètre réseau pour le périmètre unique consolidé du scénario Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Mise à l’échelle consolidée Skype Entreprise Server pool edge, avec équilibrage de charge DNS, adresses IP privées et NAT

Avec ce scénario, vous pouvez bénéficier d’une haute disponibilité dans votre déploiement Edge, ce qui vous offre les avantages de l’évolutivité et de la prise en charge duover.
  
![Scénario Edge pour edge consolidé à l’échelle, DNS LB avec ip privée à l’aide de nat](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramme de port

Nous avons également un diagramme pour les pools Edge consolidés à l’échelle avec équilibrage de charge DNS.
  
![Périmètre réseau pour le scénario Edge consolidé mis à l’échelle à l’aide de la base de données DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Mise à l’échelle Skype Entreprise Server pool edge, avec équilibrage de charge DNS et adresses IP publiques

Avec ce scénario, vous pouvez bénéficier d’une haute disponibilité dans votre déploiement Edge, ce qui vous offre les avantages de l’évolutivité et de la prise en charge duover.
  
![Scénario Edge pour le service Edge consolidé à l’échelle, DNS LB avec ip publique](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramme de port

Nous avons également un diagramme pour les pools Edge consolidés à l’échelle avec équilibrage de charge DNS.
  
![Périmètre réseau pour le scénario Edge consolidé mis à l’échelle à l’aide de la base de données DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Mise à l’échelle consolidée Skype Entreprise Server pool Edge, avec équilibrage de la charge matérielle

Avec ce scénario, vous pouvez bénéficier d’une haute disponibilité dans votre déploiement Edge, ce qui vous offre les avantages de l’évolutivité et de la prise en charge duover.
  
![Scénario edge pour le edge consolidé à l’échelle avec hLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
