---
title: "Lync Server 2013 : Top. Edge consol. mise à l’éch. avec des équil. de ch. mat."
TOCTitle: Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398478(v=OCS.15)
ms:contentKeyID: 49297466
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans la topologie du pool de serveurs Edge, au moins deux serveurs Edge sont déployés en tant que pool à charge équilibrée dans le réseau de périmètre du centre de données. L’équilibrage de la charge matérielle concerne le trafic vers les interfaces de serveur Edge internes et externes.

Si votre organisation doit prendre en charge plus de 5 000 connexions client du service Edge d’accès, 1 000 connexions client du service Edge de conférence web actif ou 500 sessions du service Edge A/V simultanées, et si la haute disponibilité du serveur Edge est importante, cette topologie offre des avantages en matière de prise en charge de l’extensibilité et du basculement.

La figure ne montre pas les directeurs, un rôle serveur facultatif déployé sur le réseau interne entre les serveurs Edge et votre pools de serveurs frontaux ou le serveur. Pour plus d’informations sur la topologie pour les directeurs, reportez-vous à [Composants requis pour le directeur dans Lync Server 2013](lync-server-2013-components-required-for-the-director.md).

> [!NOTE]  
> La figure présente l’orientation et un exemple d’adressage IP, mais ne représente pas des flux de communication réels avec un trafic entrant et sortant correct. Cette figure représente une vue générale d’un trafic possible. Les détails relatifs à un flux de trafic, en termes de trafic entrant (vers les ports d’écoute) et sortant (vers les serveurs ou clients de destination) sont indiqués dans le diagramme Résumé des ports de chaque scénario. Par exemple, TCP 443 est un port entrant uniquement (vers le serveur Edge ou le proxy inverse), et est un flux à double-sens du point de vue du protocole (TCP). De plus, la figure montre la nature du trafic quand elle change quand NAT (conversion d’adresses réseau) se produit (l’adresse de destination est modifiée à l’entrée, l’adresse source est modifiée à la sortie). Des exemples de pare-feu externe et interne et des interfaces serveur sont indiqués à titre d’information uniquement. Enfin, un exemple de passerelle par défaut et de relations d’itinéraire est expliqué. Remarquez que ce diagramme utilise la zone DNS <em>.com</em> pour représenter la zone DNS externe pour le proxy inverse et les serveurs Edge, et la zone DNS <em>.net</em> fait référence à la zone DNS interne.

L’une des nouveautés de Microsoft Lync Server 2013 est la prise en charge de l’adressage IPv6. Comme pour l’adressage IPv4, les adresses IPv6 doivent être attribuées de sorte que les adresses fassent partie de votre espace d’adressage IPv6 attribué. Les adresses de cette rubrique sont utilisées uniquement à titre d’exemple. Vous devez acquérir des adresses IPv6 qui fonctionnent dans votre déploiement, fournissent l’étendue correcte et interagissent avec l’adressage interne et externe. Windows Server offre une fonctionnalité importante pour le fonctionnement IPv6 de transition et la communication IPv4 à IPv6, appelée *double pile* . La double pile est une pile réseau distincte pour IPv4 et pour IPv6. C’est ce qui vous permet d’attribuer l’adressage pour IPv4 et IPv6 simultanément, et qui permet au serveur de communiquer avec d’autres hôtes et clients en fonction des conditions requises.

Les types d’adresses habituellement utilisés pour l’adressage IPv6 sont les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses IPv6 locales de liens (similaires aux adresses IP privées automatiques dans Windows Server pour IPv4)

La technologie NAT (Network Address Translation) pour IPv6 existe et tient compte de NAT IPv6 vers IPv4 (appelé NAT64) et de NAT IPv6 vers IPv6 (appelé NAT66). L’existence de la technologie NAT signifie que les cinq scénarios présentés pour Lync Serverserveurs Edge sont toujours valides.

> [!WARNING]  
> IPv6 est un sujet complexe qui requiert une planification minutieuse avec votre équipe de gestion de réseau et votre fournisseur Internet, pour faire en sorte que les adresses que vous attribuez au niveau du serveur Windows et au niveau de Lync Server 2013 fonctionnent comme prévu. Reportez-vous aux liens à la fin de cette rubrique pour des ressources supplémentaires sur l’adressage et la planification IPv6.

**Configuration du programme d’équilibrage de la charge matérielle**

Pour plus d’informations, reportez-vous à la section « Conditions requises pour le programme d’équilibrage de la charge matérielle du serveur Edge A/V » dans [Composants requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

**Topologie Edge consolidée mise à l’échelle (avec charge matérielle équilibrée)**

![Topologie de serveur Edge consolidé avec montée en puissance](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "Topologie de serveur Edge consolidé avec montée en puissance")

> [!IMPORTANT]  
> Si vous utilisez le service de contrôle d’admission des appels, vous devez tout de même attribuer des adresses IPv4 à l’interface interne serveur Edge. Ce service utilise en effet des adresses IPv4 et doit les avoir à disposition pour fonctionner.

## Dans cette section

  - [Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

## Voir aussi

#### Autres ressources

[Architecture d’adressage IP Version 6](http://tools.ietf.org/html/rfc4291)  
[Format d’adresse de monodiffusion globale IPv6](http://tools.ietf.org/html/rfc3587)  
[Adresses de monodiffusion IPv6 locales uniques](http://tools.ietf.org/html/rfc4193)

