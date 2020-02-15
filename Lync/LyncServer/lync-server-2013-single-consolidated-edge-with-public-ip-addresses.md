---
title: 'Lync Server 2013 : serveur Edge unique consolidé avec adresses IP publiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1867abe0cc16190650d2be303a55ecf0dd6a5efd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Si votre organisation a besoin d’une prise en charge pour moins de 15 000 connexions client de service Edge d’accès, 1 000 connexions de client de service de conférence Web Lync Server et 500 sessions Edge A/V simultanées, et que la haute disponibilité du serveur Edge n’est pas importante, cette topologie offre les avantages d’un coût matériel inférieur et d’un déploiement plus simple. Si vous avez besoin d’une capacité supérieure ou d’une haute disponibilité, vous devez déployer une topologie de serveur Edge consolidé ajusté.

  - <span></span>  
    [Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> Lors de l’utilisation de l’adresse IP publique sur le serveur Edge, la passerelle par défaut sur le serveur Edge n’est plus votre pare-feu ou routeur, mais le routeur ou le pare-feu de votre serveur Edge de périmètre public, qui sera une adresse publique. Le proxy inverse continue d’utiliser le routeur ou pare-feu associé au réseau de périmètre le plus éloigné. La différence entre le proxy inverse et le serveur Edge avec des adresses IP publiques est que le proxy inverse continue d’utiliser la traduction d’adresses réseau et que le serveur Edge utilise une relation d’itinéraire.



</div>

Le schéma n’affiche pas les directeurs, un rôle de serveur facultatif déployé sur le réseau interne entre les serveurs Edge et vos pools ou serveurs frontaux. Pour plus d’informations sur la topologie pour les directeurs, reportez-vous à la rubrique [composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md). La figure représente un proxy inverse seul.

<div>


> [!NOTE]  
> La figure présente l’orientation et un exemple d’adressage IP, mais ne représente pas des flux de communication réels avec les trafics entrant et sortant corrects. Cette figure représente une vue générale d’un trafic. Les détails relatifs à un flux de trafic, en termes de trafic entrant (vers les ports d’écoute) et sortant (vers les serveurs ou clients de destination) sont indiqués dans le diagramme Résumé des ports de chaque scénario. Par exemple, TCP 443 est un port entrant uniquement (vers le serveur Edge ou le proxy inverse), et est un flux à double-sens du point de vue du protocole (TCP). De plus, la figure montre la nature du trafic si elle change quand NAT (traduction d’adresses réseau) se produit (l’adresse de destination est modifiée à l’entrée, l’adresse source est modifiée à la sortie). Des exemples de pare-feu externe et interne et des interfaces serveur sont indiqués à titre d’information uniquement. Enfin, un exemple de passerelle par défaut et de relations d’itinéraire est expliqué. Notez également que le diagramme utilise la zone DNS <EM>. com</EM> pour représenter la zone DNS externe pour les serveurs de proxy inverse et Edge, et que la zone DNS <EM>.net</EM> fait référence à la zone DNS interne.



</div>

La nouveauté de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6. Tout comme pour l’adressage IPv4, les adresses IPv6 doivent être assignées afin qu’elles fassent partie de l’espace d’adressage IPv6 assigné. Les adresses de cette rubrique sont des exemples. Vous devez obtenir des adresses IPv6 qui fonctionnent dans votre déploiement, fournissent la bonne portée et interagissent avec l’adressage interne et externe. Windows Server offre une fonctionnalité importante pour les opérations de transition IPv6 et IPv4 vers IPv6, appelée *pile double*. La double pile est une pile réseau séparée et distincte pour IPv4 et pour IPv6. La double pile est ce qui vous permet d’assigner l’adressage pour IPv4 et IPv6 simultanément, et permet au serveur de communiquer avec d’autres hôtes et clients en fonction de leur configuration.

Les types d’adresses standard que vous utiliserez pour l’adressage IPv6 seront les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses de lien local IPv6 (semblables à l’adresse IP privée automatique adresses dans Windows Server pour IPv4)

Des technologies NAT (traduction d’adresses réseau) pour IPv6 existent qui permettent la traduction NAT IPv6 en IPv4 (appelée NAT64) et NAT IPv6 en IPv6 (appelée NAT66). L’existence de technologies NAT signifie que les cinq scénarios présentés pour les serveurs Edge Lync Server sont toujours valides.

<div>


> [!WARNING]  
> IPv6 est une rubrique complexe qui nécessite une planification soignée avec votre équipe réseau et votre fournisseur Internet afin de s’assurer que les adresses que vous affectez au niveau de Windows Server et de Lync Server 2013 fonctionneront comme prévu. Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.



</div>

**Serveur Edge consolidé unique avec topologie d’adresses IP publiques**

![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")

<div>


> [!IMPORTANT]  
> Si vous utilisez le contrôle d’admission des appels (CAC), vous devez toujours attribuer des adresses IPv4 à l’interface interne du serveur Edge. CAC utilise les adresses IPv4 et elles doivent être disponibles pour qu’il puisse fonctionner.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Résumé des enregistrements DNS-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Architecture d’adressage IP version 6](http://tools.ietf.org/html/rfc4291)  
[Format d’adresse unicast global IPv6](http://tools.ietf.org/html/rfc3587)  
[Adresses unicast IPv6 locales uniques](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

