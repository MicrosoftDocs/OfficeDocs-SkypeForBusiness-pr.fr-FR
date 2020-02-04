---
title: 'Lync Server 2013 : Meilleures pratiques liées au contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8f75c546b2307de8f55504c2c6ebaab5c48f7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Meilleures pratiques liées au contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-22_

Pour améliorer les performances et faciliter le déploiement, appliquez les recommandations suivantes lors du déploiement du contrôle d’admission des appels :

  - Vérifiez que les réseaux étendus (WAN) sont configurés en conséquence pour le trafic multimédia actuel et envisagé.
    
    <div>
    

    > [!NOTE]  
    > Nous vous conseillons de définir un facteur en mémoire tampon quant aux limites de votre bande passante. Il existe des scénarios de condition de concurrence qui agissent sur la bande passante totale utilisée et qui peuvent entraîner des situations de dépassement de la limite de la bande. Prenons l’exemple de deux appels amorcés alors que le trafic multimédia approche de la limite de la bande passante : l’un des appels pourra être refusé, car l’autre a été configuré pour démarrer en premier.

    
    </div>

  - Contrôlez l’utilisation du réseau et les enregistrements des détails des appels pour pouvoir choisir les meilleurs paramètres de contrôle d’admission des appels (CAC) et les mettre à jour en fonction de l’évolution de l’utilisation du réseau.

  - Utilisez les stratégies de bande passante CAC pour compléter les paramètres QoS.

  - Si vous souhaitez réacheminer des appels bloqués sur le réseau RTC, vérifiez les fonctionnalités et capacités correspondantes. Pour plus d’informations, reportez-vous à la [planification du routage de la voix sortante dans Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    <div>
    

    > [!NOTE]  
    > La capacité fait référence au nombre de ports à ouvrir pour prendre en charge un éventuel réacheminement vers le réseau RTC.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

