---
title: 'Lync Server 2013 : Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f37395f840e8811d343f11f6ee2a84bd4fcfbf82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a>Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

Si votre organisation a besoin d’une prise en charge de moins de 15 000 connexions clientes du service Edge d’accès, de 1 000 de 500 connexions client de service de conférence rendez-vous actives Lync important, cette topologie offre les avantages de réduire le coût du matériel et de simplifier le déploiement. Si vous avez besoin d’une plus grande capacité ou que vous avez besoin d’une haute disponibilité, vous devez déployer une topologie de serveur Edge consolidée à l’échelle. Pour plus d’informations, consultez l’une des rubriques suivantes:

  - <span></span>  
    [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

La figure ne montre pas les directeurs, un rôle serveur facultatif déployé sur le réseau interne entre les serveurs de périphérie et vos pools ou serveurs. Pour plus d’informations sur la topologie des directeurs, voir [composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md). La figure représente une seule doublure inverse.

<div>


> [!NOTE]  
> La figure affichée correspond à l’orientation et à l’adresse IP, par exemple, sans vouloir représenter les flux de communication réel avec le trafic entrant et sortant correct. La figure représente une vue de haut niveau du trafic potentiel. Les détails relatifs au flux de trafic tels qu’ils sont liés aux ports entrants (vers les ports d’écoute) et sortants (vers les serveurs de destination ou les clients) sont représentés dans le schéma de synthèse de port de chaque scénario. Par exemple, le protocole TCP 443 est en fait entrant (pour le proxy Edge ou inverse) uniquement, et n’est qu’un flux bidirectionnel à partir d’un point de vue du protocole TCP. Par ailleurs, la figure montre la nature du trafic au fur et à mesure de son changement lors de la modification de la traduction d’adresses réseau (la traduction d’adresses de destination a changé sur le trafic sortant). Par exemple, les interfaces serveur et de pare-feu internes et externes sont affichées uniquement à des fins de référence. Enfin, vous pouvez voir des exemples de passerelles et d’itinéraires par défaut, le cas échéant. Notez également que le diagramme utilise la zone DNS <EM>. com</EM> pour représenter la zone DNS externe pour les serveurs de proxy inverse et Edge, et que la zone DNS <EM>.net</EM> fait référence à la zone DNS interne.



</div>

La nouveauté de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6. À l’instar de l’adressage IPv4, une adresse IPv6 doit être attribuée de telle sorte que les adresses font partie de votre espace d’adressage IPv6 attribué. Les adresses figurant dans cette rubrique sont par exemple uniquement. Vous devez acquérir les adresses IPv6 qui fonctionneront dans votre déploiement, fournir l’étendue correcte et utilisera l’adressage interne et externe. Windows Server fournit une fonctionnalité importante pour les opérations IPv6 de transition et IPv4 à IPv6 appelées *pile double*. La pile double est une pile réseau séparée et distincte pour IPv4 et IPv6. La pile double est celle qui vous permet d’attribuer l’adresse IPv4 et IPv6 en même temps, et permet au serveur de communiquer avec d’autres hôtes et clients en fonction de la configuration requise.

Les types d’adresse que vous utiliserez pour l’adressage IPv6 seront les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses locales de liaison IPv6 (similaires à l’adresse IP privée automatique). adresses dans Windows Server pour IPv4)

Il existe des technologies de traduction d’adresses réseau (NAT) pour IPv6 qui autorisent le protocole NAT IPv6 sur IPv4 (également appelé NAT64) et la traduction d’adresses réseau via le protocole IPv6 (appelé NAT66). L’existence de technologies NAT signifie que les cinq scénarios présentés pour les serveurs Edge Lync Server sont toujours valides.

<div>


> [!WARNING]  
> Le protocole IPv6 est un sujet complexe et nécessite une planification soigneuse de votre équipe réseau et de votre fournisseur d’accès à Internet pour vous assurer que les adresses affectées au niveau Windows Server et au niveau Lync Server 2013 fonctionneront comme prévu. Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.



</div>

**Topologie de périphérie consolidée unique**

![d9b889c1-587c-4732-9b68-841186ccff78] (images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")

<div>


> [!IMPORTANT]  
> Si vous utilisez le contrôle d’admission des appels (CAC), vous devez quand même affecter des adresses IPv4 à l’interface interne du serveur Edge. Le CAC utilise les adresses IPv4 et doit être disponible pour fonctionner.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Architecture d’adresse IP version 6](http://tools.ietf.org/html/rfc4291)  
[Format d’adresse monodiffusion global IPv6](http://tools.ietf.org/html/rfc3587)  
[Adresses monodiffusion IPv6 locales uniques](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

