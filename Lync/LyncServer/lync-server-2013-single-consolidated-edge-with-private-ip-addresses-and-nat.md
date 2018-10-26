---
title: "Lync Server 2013 : Serveur Edge cons. unique ac ad. IP pri. et conv. ad. rés."
TOCTitle: Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399001(v=OCS.15)
ms:contentKeyID: 49299119
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Si votre entreprise doit prendre en charge moins de 15 000 connexions client du service Edge d’accès, 1 000 connexions client du service de conférence web Lync Server et 500 sessions Edge audio/vidéo simultanées, et si la disponibilité du serveur Edge n’est pas importante, cette topologie offre des coûts de matériel inférieurs et un déploiement simplifié. Si vous avez besoin d’une plus grande capacité ou disponibilité, vous devez déployer une topologie Edge Server consolidée mise à l’échelle. Pour plus d’informations, reportez-vous à ’un des éléments suivants :

  -   
    [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  -   
    [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  -   
    [Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

La figure ne montre pas les directeurs, un rôle de serveur facultatif déployé dans le réseau interne entre les serveurs Edge et vos pools de serveurs frontaux ou votre serveur. Pour plus d’informations sur la topologie destinée aux directeurs, reportez-vous à [Composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md). Cette figure représente un proxy inverse unique.

> [!NOTE]  
> La figure affichée est destinée à l’orientation et sert d’exemple d’adressage IP, mais n’est pas censée représenter les flux de communication réelle avec le trafic entrant et sortant correct. Elle représente une vue globale du trafic possible. Les informations concernant le flux du trafic entrant (vers les ports d’écoute) et sortant (vers les serveurs de destination ou clients) sont représentées dans le diagramme Résumé de port de chaque scénario. Par exemple, TCP 443 est en fait entrant (vers le proxy Edge ou inverse) uniquement, et constitue seulement un flux bidirectionnel depuis une perspective de protocole (TCP). De plus, la figure montre la nature du trafic quand il change lors de l’intervention d’un NAT (Network Address Translation) (l’adresse de destination est modifiée pour un flux entrant, l’adresse source est modifiée pour un flux sortant). Des exemples de pare-feu externe et interne, ainsi que d’interfaces de serveurs, sont présentés pour référence uniquement. Enfin, des exemples de passerelle par défaut et de relations de routage sont indiqués, le cas échéant. Notez également que le diagramme utilise la zone DNS <em>.com</em> pour représenter la zone DNS externe pour le proxy inverse et les serveurs Edge, tandis que la zone DNS <em>.net</em> fait référence à la zone DNS interne.

L’une des nouveautés de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6. Comme pour l’adressage IPv4, les adresses IPv6 doivent être attribuées de sorte que les adresses fassent partie de votre espace d’adressage IPv6 attribué. Les adresses de cette rubrique sont utilisées uniquement à titre d’exemple. Vous devez acquérir des adresses IPv6 qui fonctionnent dans votre déploiement, fournissent l’étendue correcte et interagissent avec l’adressage interne et externe. Windows Server offre une fonctionnalité importante pour le fonctionnement IPv6 de transition et la communication IPv4 à IPv6, appelée *double pile* . La double pile est une pile réseau distincte pour IPv4 et pour IPv6. C’est ce qui vous permet d’attribuer l’adressage pour IPv4 et IPv6 simultanément, et qui permet au serveur de communiquer avec d’autres hôtes et clients en fonction des conditions requises.

Les types d’adresses habituellement utilisés pour l’adressage IPv6 sont les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses IPv6 locales de liens (similaires aux adresses IP privées automatiques dans Windows Server pour IPv4)

La technologie NAT (Network Address Translation) pour IPv6 existe et tient compte de NAT IPv6 vers IPv4 (appelé NAT64) et de NAT IPv6 vers IPv6 (appelé NAT66). L’existence de la technologie NAT signifie que les cinq scénarios présentés pour Lync Serverserveurs Edge sont toujours valides.

> [!WARNING]  
> IPv6 est un sujet complexe qui requiert une planification minutieuse avec votre équipe de gestion de réseau et votre fournisseur Internet, pour faire en sorte que les adresses que vous attribuez au niveau du serveur Windows et au niveau de Lync Server 2013 fonctionnent comme prévu. Reportez-vous aux liens à la fin de cette rubrique pour obtenir des ressources supplémentaires sur l’adressage et la planification IPv6.

**Topologie Edge consolidée unique**

![Topologie Edge consolidée unique](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "Topologie Edge consolidée unique")

> [!IMPORTANT]  
> Si vous utilisez le service de contrôle d’admission des appels, vous devez tout de même attribuer des adresses IPv4 à l’interface interne serveur Edge. Ce service utilise en effet des adresses IPv4 et doit les avoir à disposition pour fonctionner.

## Dans cette section

  - [Résumé des certificats - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

## Voir aussi

#### Autres ressources

[Architecture d’adressage IP Version 6](http://tools.ietf.org/html/rfc4291)  
[Format d’adresse de monodiffusion globale IPv6](http://tools.ietf.org/html/rfc3587)  
[Adresses de monodiffusion IPv6 locales uniques](http://tools.ietf.org/html/rfc4193)

