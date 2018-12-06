---
title: "Lync Server 2013 : Fonct. non prises en charge par le routage géodépendant"
TOCTitle: Fonctionnalités non prises en charge par le routage géodépendant
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994071(v=OCS.15)
ms:contentKeyID: 53095522
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fonctionnalités non prises en charge par le routage géodépendant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-03-12_

Le routage géodépendant ne s’applique pas aux types d’interactions suivants. Le routage géodépendant n’est pas appliqué quand les points de terminaison Lync interagissent avec les points de terminaison RTC à l’aide de ces fonctionnalités.

  - Appels RTC entrants pour les conférences

  - Appels RTC entrants et sortants via le groupe de réponse

  - Parcage d’appel ou récupération des appels via le parcage d’appels

  - Appels RTC entrants pour le service d’annonce

  - Appels RTC entrants récupérés via la prise d’appel de groupe

Pour appliquer les règles de routage géodépendant aux types d’interactions dans la liste suivante, vous devez activer le routage géodépendant pour les conférences :

  - Appels RTC sortants à partir des conférences

  - Escalades à partir de conversations audio d’P2P vers des conférences impliquant des points de terminaison RTC

  - Transferts consultatifs impliquant les points de terminaison RTC

Pour activer le routage géodépendant pour les conférences, reportez-vous à [Routage géodépendant pour les conférences dans Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

## Voir aussi

#### Autres ressources

[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

