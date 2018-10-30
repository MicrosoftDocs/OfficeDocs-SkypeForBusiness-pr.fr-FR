---
title: 'Lync Server 2013 : Délégation'
TOCTitle: Délégation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994045(v=OCS.15)
ms:contentKeyID: 53095457
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Délégation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-09_

Les fonctionnalités de délégation dans Lync sont affectées par le routage géodépendant comme suit :

  - Si un délégué pour lequel le routage géodépendant est activé passe un appel de la part d’un responsable, la stratégie de voix du délégué est utilisée pour autoriser l’appel et la stratégie de routage des communications vocales du site du délégué est utilisée pour acheminer l’appel.

  - Pour les appels RTC passés à un responsable, les règles applicables au transfert d’appel ou à la sonnerie simultanée sont utilisées, comme décrit dans les rubriques « Transfert et renvoi des appels » et « Sonnerie simultanée ».

  - Si un délégué définit un point de terminaison RTC comme cible de sonnerie simultanée, pour un appel entrant passé à un responsable, la stratégie de routage des communications vocales du site associé à la jonction entrante est utilisée pour acheminer l‘appel vers le point de terminaison RTC du délégué.

  - Pour la délégation, il est recommandé que le responsable et ses délégués soient situés dans le même site réseau.

## Voir aussi

#### Autres ressources

[Scénarios de routage géodépendant dans Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

