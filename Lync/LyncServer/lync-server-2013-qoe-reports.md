---
title: 'Lync Server 2013 : rapports QoE'
description: 'Lync Server 2013 : rapports QoE.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571400"
---
# <a name="qoe-reports-in-lync-server-2013"></a>Rapports QoE dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>Rapports de tendance/Résumé QoE

Les rapports de résumé/tendances QoE sont utiles pour trouver les heures d’utilisation maximale du jour et examiner la qualité des médias pendant ces périodes afin de s’assurer que les ressources réseau de votre organisation sont suffisantes. Votre organisation peut également utiliser les nombreux filtres disponibles dans le rapport pour isoler les numéros de performances de certains emplacements, clients et types d’appareils et de serveurs.

Le résumé des données QoE/rapports de tendance se compose des éléments suivants :

  - Rapport de tendance/synthèse UC/Cu

  - Résumé PSTN/rapport de tendance

  - Rapport de tendance/Résumé de conférence

</div>

<div>

## <a name="qoe-performance-reports"></a>Rapports de performances QoE

Les rapports sur les performances QoE fournissent des détails sur les trois rapports qui se concentrent sur les performances QoE des serveurs de médiation, des serveurs de conférence A/V et des emplacements de point de terminaison.

</div>

<div>

## <a name="mediation-server-performance-report"></a>Rapport de performances du serveur de médiation

Le rapport de performances du serveur de médiation répertorie les mesures réalisées par une ou plusieurs médiations pendant la période spécifiée. Les mesures de la jambe de serveur communications unifiées (UC) à médiation et la partie serveur à passerelle de médiation de chaque appel sont signalées séparément. Utilisez ce rapport pour comparer le volume et les performances des différents serveurs de médiation de votre organisation.

Pour chaque serveur de médiation (et pour chaque tronçon d’appel), le rapport affiche les éléments suivants :

  - Nombre d’appels

  - Perte de paquets

  - Durée de la boucle

  - Scintill

  - Note moyenne d’opinion de conversation (MOS)

  - Envoi d’un MOS

  - Réception d’un MOS

  - MOS réseau

  - Dégradation du MOS réseau

  - Retour d’écho

  - Niveau du signal

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>Rapport de performances du serveur de conférence A/V

Le rapport de performances du serveur de conférence A/V fournit des listes de mesures réalisées par un ou plusieurs serveurs de conférence A/V pendant la période spécifiée. Ce rapport peut être utilisé pour comparer le volume et les performances des différents serveurs de conférence A/V de votre organisation. Votre organisation peut également isoler le rapport pour afficher uniquement l’expérience de types de clients spécifiques, tels que les clients Lync ou les clients RTC.

Pour chaque serveur de conférence A/V, le rapport affiche les éléments suivants :

  - Nombre de conférences

  - Perte de paquets

  - Durée de la boucle

  - Scintill

  - Note moyenne d’opinion de conversation (MOS)

  - Envoi d’un MOS

  - Réception d’un MOS

  - MOS réseau

  - Dégradation du MOS réseau

  - Retour d’écho

  - Niveau du signal

</div>

<div>

## <a name="location-based-performance-report"></a>Rapport de performances basé sur l’emplacement

Le rapport de performances de Location-Based fournit une liste des emplacements réseau et indique le nombre d’appels dans chaque plage de qualité prédéterminée. L’objectif de ce rapport est de fournir une vue d’ensemble de la qualité des médias de l’ensemble des appels téléphoniques de votre organisation pour les différents emplacements, afin que vous puissiez identifier les emplacements les plus performants et voir les différentes qualités de médias dans les différents emplacements de votre organisation.

Lors de l’affichage du rapport, différentes tables de mesures apparaissent : une table pour chaque mesure que votre organisation décide d’effectuer des rapports. Vous pouvez choisir l’une des mesures suivantes pour ce rapport :

  - Note moyenne d’opinion de conversation (MOS)

  - MOS réseau

  - Dégradation du MOS réseau

  - Envoi d’un MOS

  - Réception d’un MOS

  - Perte de paquets

  - Scintill

  - Latence

</div>

</div>

<span> </span>

</div>

</div>

</div>

