---
title: 'Lync Server 2013 : Déviation du trafic multimédia et serveur de médiation'
TOCTitle: Déviation du trafic multimédia et serveur de médiation
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398719(v=OCS.15)
ms:contentKeyID: 49298041
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

La déviation du trafic multimédia est une nouvelle fonctionnalité de Lync Server qui permet à un administrateur de configurer le routage des appels de manière à ce qu’il s’achemine directement entre le point de terminaison utilisateur et la passerelle RTC sans passer par le serveur de médiation. La déviation du trafic multimédia améliore la qualité d’appel en diminuant la latence, les conversions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels. Là où un site distant sans serveur de médiation est connecté à un site central par une ou plusieurs liaisons de réseau étendu avec une bande passante restreinte, la déviation du trafic multimédia réduit les besoins en bande passante en permettant au média du client d’un site distant de s’acheminer directement vers sa passerelle locale sans avoir besoin de passer par la liaison de réseau étendu vers le serveur de médiation sur le site central et inversement. Cette réduction en termes de traitement du média complète également la capacité du serveur de médiation à contrôler plusieurs passerelles.

La déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement. Si la déviation du trafic multimédia est utilisée pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel.

## Voir aussi

#### Concepts

[Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  

#### Autres ressources

[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

