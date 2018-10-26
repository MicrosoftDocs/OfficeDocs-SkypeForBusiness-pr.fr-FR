---
title: 'Lync Server 2013 : Emplacement de la passerelle RTC'
TOCTitle: Emplacement de la passerelle RTC
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994031(v=OCS.15)
ms:contentKeyID: 53095411
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Emplacement de la passerelle RTC dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-09_

Les appels acheminés via des passerelles RTC et des PBX peuvent nécessiter des restrictions de routage géodépendant selon l’emplacement de ces systèmes. Le routage géodépendant peut être activé au niveau de précision des jonctions individuelles.

Le routage géodépendant applique l’ensemble de règles suivant lorsqu’il est activé sur une jonction :

  - Lorsque le routage géodépendant est activé sur la base des jonctions individuelles, les règles définies sur cette jonction sont appliquées aux appels acheminés via cette jonction uniquement.

  - Pour empêcher le contournement des frais de réseau téléphonique commuté lorsque des appels proviennent d’un site réseau différent de celui sur lequel la passerelle RTC est située, le routage géodépendant associe un site réseau à une jonction donnée. Cela permet de définir le site réseau qui permet l’acheminement des appels vers une jonction donnée.

Le routage géodépendant peut être activé de deux manières sur les jonctions :

  - La jonction est définie pour une passerelle RTC qui fait sortir les appels vers le réseau téléphonique commuté (RTC). Les appels entrants pris en charge par une jonction de ce type sont acheminés uniquement vers les points de terminaison situés au sein du même site réseau que la jonction.

  - La jonction est définie pour un homologue serveur de médiation ne faisant pas sortir les appels vers le réseau téléphonique commuté (RTC) et desservant les utilisateurs à l’aide de téléphones hérités dans des emplacements statiques (téléphones PBX). Pour cette configuration particulière, tous les appels entrants acheminés par une jonction de ce type sont considérés comme provenant du même site réseau que la jonction. Les appels des utilisateurs PBX auront la même application de routage géodépendant que les utilisateurs Lync situés dans le même site réseau que la jonction. Si deux systèmes PBX situés dans des sites réseau distincts sont connectés via Lync Server, le routage géodépendant autorisera le routage à partir d’un point de terminaison de PBX dans un site réseau vers un autre point de terminaison de PBX dans l’autre site réseau. Ce scénario ne sera pas bloqué par le routage géodépendant. À l’instar d’un utilisateur Lync situé dans le même emplacement, les points de terminaison connectés à un homologue serveur de médiation avec cette configuration peuvent par ailleurs passer et recevoir des appels avec l’autre homologue serveur de médiation qui n’achemine pas les appels vers le réseau téléphonique commuté (RTC) (point de terminaison connecté à un autre PBX), quel que soit le site réseau auquel l’homologue serveur de médiation est associé. Tous les appels entrants, appels sortants, transferts d’appel et renvois d’appel impliquant les points de terminaison RTC sont soumis au routage géodépendant afin de n’utiliser que les passerelles RTC définies comme locales pour cet homologue serveur de médiation.

## Voir aussi

#### Autres ressources

[Instructions de routage géodépendant dans Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)

