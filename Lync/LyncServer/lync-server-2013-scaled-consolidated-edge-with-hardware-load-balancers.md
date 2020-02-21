---
title: 'Lync Server 2013 : serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a961b6eabb85e135b1cfb36cf5738cbf757b547
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Dans la topologie de pool de serveurs Edge, deux ou plusieurs serveurs Edge sont déployés en tant que pool à charge équilibrée dans le réseau de périmètre du centre de données. L’équilibrage de la charge matérielle est utilisé pour le trafic vers les interfaces de serveur Edge externe et interne.

Si votre organisation doit prendre en charge plus de 15 000 connexions client du service Edge d’accès, 1 000 connexions client de service Edge de conférence Web actives ou 500 sessions de service Edge A/V simultanées, et que la haute disponibilité du serveur Edge est importante, cette topologie offre des avantages en termes d’extensibilité et de basculement.

Le schéma n’affiche pas les directeurs, un rôle de serveur facultatif déployé sur le réseau interne entre les serveurs Edge et vos pools ou serveurs frontaux. . Pour plus d’informations sur la topologie pour les directeurs, reportez-vous à la rubrique [composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md).

<div>


> [!NOTE]  
> La figure présente l’orientation et un exemple d’adressage IP, mais ne représente pas des flux de communication réels avec les trafics entrant et sortant corrects. Cette figure représente une vue générale d’un trafic. Les détails relatifs à un flux de trafic, en termes de trafic entrant (vers les ports d’écoute) et sortant (vers les serveurs ou clients de destination) sont indiqués dans le diagramme Résumé des ports de chaque scénario. Par exemple, le protocole TCP 443 est réellement entrant (vers le serveur Edge ou proxy inverse) uniquement, et n’est qu’un flux bidirectionnel à partir d’un point de vue du protocole (TCP). De plus, la figure montre la nature du trafic si elle change quand NAT (traduction d’adresses réseau) se produit (l’adresse de destination est modifiée à l’entrée, l’adresse source est modifiée à la sortie). Des exemples de pare-feu externe et interne et des interfaces serveur sont indiqués à titre d’information uniquement. Enfin, un exemple de passerelle par défaut et de relations d’itinéraire est expliqué. Notez également que le diagramme utilise la zone DNS <EM>. com</EM> pour représenter la zone DNS externe pour les serveurs de proxy inverse et Edge, et que la zone DNS <EM>.net</EM> fait référence à la zone DNS interne.



</div>

La nouveauté de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6. Tout comme pour l’adressage IPv4, les adresses IPv6 doivent être assignées afin qu’elles fassent partie de l’espace d’adressage IPv6 assigné. Les adresses de cette rubrique sont des exemples. Vous devez obtenir des adresses IPv6 qui fonctionnent dans votre déploiement, fournissent la bonne portée et interagissent avec l’adressage interne et externe. Windows Server offre une fonctionnalité importante pour les opérations de transition IPv6 et IPv4 vers IPv6, appelée *pile double*. La double pile est une pile réseau séparée et distincte pour IPv4 et pour IPv6. La double pile est ce qui vous permet d’assigner l’adressage pour IPv4 et IPv6 simultanément, et permet au serveur de communiquer avec d’autres hôtes et clients en fonction de leur configuration.

Les types d’adresses standard que vous utiliserez pour l’adressage IPv6 seront les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses de lien local IPv6 (semblables à l’adresse IP privée automatique adresses dans Windows Server pour IPv4)

Des technologies NAT (traduction d’adresses réseau) pour IPv6 existent qui permettent la traduction NAT IPv6 en IPv4 (appelée NAT64) et NAT IPv6 en IPv6 (appelée NAT66). L’existence de technologies NAT signifie que les cinq scénarios présentés pour les serveurs Edge Lync Server sont toujours valides.

<div>


> [!WARNING]  
> IPv6 est une rubrique complexe qui nécessite une planification soignée avec votre équipe réseau et votre fournisseur Internet afin de s’assurer que les adresses que vous affectez au niveau de Windows Server et de Lync Server 2013 fonctionneront comme prévu. Consultez les liens à la fin de cette rubrique pour des ressources supplémentaires sur l’adressage IPv6 et la planification.



</div>

**Configuration du programme d’équilibrage de la charge matérielle**

Pour plus d’informations, reportez-vous à la section « Configuration requise pour l’équilibreur de charge matérielle pour les serveurs Edge A/V » dans [composants requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

**Topologie Edge consolidée mise à l’échelle (avec charge matérielle équilibrée)**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> Si vous utilisez le contrôle d’admission des appels (CAC), vous devez toujours attribuer des adresses IPv4 à l’interface interne du serveur Edge. CAC utilise les adresses IPv4 et elles doivent être disponibles pour qu’il puisse fonctionner.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Résumé des enregistrements DNS-serveur Edge consolidé ajusté avec programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

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

