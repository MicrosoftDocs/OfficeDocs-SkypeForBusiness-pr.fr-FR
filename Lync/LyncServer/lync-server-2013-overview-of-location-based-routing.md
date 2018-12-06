---
title: 'Lync Server 2013 : Vue d’ensemble du routage géodépendant'
TOCTitle: Vue d’ensemble du routage géodépendant
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994032(v=OCS.15)
ms:contentKeyID: 53095412
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble du routage géodépendant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Le routage géodépendant introduit de nouvelles règles modifiant le routage des appels RTC nationaux et internationaux pour empêcher le contournement des frais de réseau téléphonique commuté. Il offre la flexibilité nécessaire pour appliquer ces règles à certaines régions, passerelles ou groupes d’utilisateurs uniquement.

Les scénarios suivants illustrent les principaux types de restriction que le routage géodépendant peut mettre en œuvre :

  - Acheminer les appels : le routage géodépendant peut configurer les appels sortants pour les acheminer depuis une passerelle RTC basée dans la même région que l’appelant pour empêcher le contournement des frais de réseau téléphonique commuté RTC et, ainsi, les acheminer depuis une passerelle RTC située dans une région autre que celle de l’appelant.

  - Acheminer les appels : le routage géodépendant peut empêcher les appels RTC entrants d’atteindre les points de terminaison Lync si la passerelle RTC dirigeant les appels entrants se trouve dans une région autre que celle de l’utilisateur Lync appelé.

  - Régions inconnues : le routage géodépendant restreint les appels entrants et sortants RTC vers et depuis les utilisateurs dont la localisation est indéterminée (à savoir les utilisateurs distants se connectant depuis Internet ou vivant dans des régions inconnues).

  - Régions internationales : le routage géodépendant achemine les appels sortants via les passerelles RTC internationales si aucune passerelle n’est disponible à proximité de la région de l’utilisateur.

## Voir aussi

#### Autres ressources

[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

