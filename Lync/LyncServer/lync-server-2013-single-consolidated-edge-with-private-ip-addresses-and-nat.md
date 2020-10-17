---
title: 'Lync Server 2013 : serveur Edge consolidé unique avec adresses IP privées et NAT'
description: 'Lync Server 2013 : serveur Edge consolidé unique avec adresses IP privées et NAT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e716cd7cd07fdb4e4557cab83db7d8f3aecada2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555670"
---
# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a>Serveur Edge consolidé unique avec des adresses IP privées et une interface NAT dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Si votre organisation requiert la prise en charge de moins de 15 000 connexions client du service Edge d’accès, 1 000 connexions client de service de conférence Web Lync Server actives et 500 sessions Edge A/V simultanées, et que la haute disponibilité du serveur Edge n’est pas importante, cette topologie offre les avantages d’un coût matériel inférieur et d’un déploiement plus simple. Si vous avez besoin d’une plus grande capacité ou si vous avez besoin d’une haute disponibilité, vous devez déployer une topologie de serveur Edge consolidée à l’adaptation. Pour plus d’informations, reportez-vous à l’un des articles suivants :

  - <span></span>  
    [Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

Le schéma n’affiche pas les directeurs, un rôle de serveur facultatif déployé sur le réseau interne entre les serveurs Edge et vos pools ou serveurs frontaux. Pour plus d’informations sur la topologie pour les directeurs, reportez-vous à la rubrique [composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md). La figure représente un proxy inverse seul.

<div>


> [!NOTE]  
> La figure présente l’orientation et un exemple d’adressage IP, mais ne représente pas des flux de communication réels avec les trafics entrant et sortant corrects. Cette figure représente une vue générale d’un trafic. Les détails relatifs à un flux de trafic, en termes de trafic entrant (vers les ports d’écoute) et sortant (vers les serveurs ou clients de destination) sont indiqués dans le diagramme Résumé des ports de chaque scénario. Par exemple, TCP 443 est un port entrant uniquement (vers le serveur Edge ou le proxy inverse), et est un flux à double-sens du point de vue du protocole (TCP). De plus, la figure montre la nature du trafic si elle change quand NAT (traduction d’adresses réseau) se produit (l’adresse de destination est modifiée à l’entrée, l’adresse source est modifiée à la sortie). Des exemples de pare-feu externe et interne et des interfaces serveur sont indiqués à titre d’information uniquement. Enfin, un exemple de passerelle par défaut et de relations d’itinéraire est expliqué. Notez également que le diagramme utilise la zone DNS <EM>. com</EM> pour représenter la zone DNS externe pour les serveurs de proxy inverse et Edge, et que la zone DNS <EM>.net</EM> fait référence à la zone DNS interne.



</div>

La nouveauté de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6. Tout comme pour l’adressage IPv4, les adresses IPv6 doivent être assignées afin qu’elles fassent partie de l’espace d’adressage IPv6 assigné. Les adresses de cette rubrique sont des exemples. Vous devez obtenir des adresses IPv6 qui fonctionnent dans votre déploiement, fournissent la bonne portée et interagissent avec l’adressage interne et externe. Windows Server offre une fonctionnalité importante pour les opérations de transition IPv6 et IPv4 vers IPv6, appelée *pile double*. La double pile est une pile réseau séparée et distincte pour IPv4 et pour IPv6. La double pile est ce qui vous permet d’assigner l’adressage pour IPv4 et IPv6 simultanément, et permet au serveur de communiquer avec d’autres hôtes et clients en fonction de leur configuration.

Les types d’adresses standard que vous utiliserez pour l’adressage IPv6 seront les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses de lien local IPv6 (semblables aux adresses IP privées automatiques dans Windows Server pour IPv4)

Des technologies NAT (traduction d’adresses réseau) pour IPv6 existent qui permettent la traduction NAT IPv6 en IPv4 (appelée NAT64) et NAT IPv6 en IPv6 (appelée NAT66). L’existence de technologies NAT signifie que les cinq scénarios présentés pour les serveurs Edge Lync Server sont toujours valides.

<div>


> [!WARNING]  
> IPv6 est une rubrique complexe qui nécessite une planification soignée avec votre équipe réseau et votre fournisseur Internet afin de s’assurer que les adresses que vous affectez au niveau de Windows Server et de Lync Server 2013 fonctionneront comme prévu. Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.



</div>

**Topologie Edge consolidée unique**

![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")

<div>


> [!IMPORTANT]  
> Si vous utilisez le contrôle d’admission des appels (CAC), vous devez toujours attribuer des adresses IPv4 à l’interface interne du serveur Edge. CAC utilise les adresses IPv4 et elles doivent être disponibles pour qu’il puisse fonctionner.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Résumé des ports-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Résumé des enregistrements DNS-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Architecture d’adressage IP version 6](https://tools.ietf.org/html/rfc4291)  
[Format d’adresse unicast global IPv6](https://tools.ietf.org/html/rfc3587)  
[Adresses unicast IPv6 locales uniques](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

