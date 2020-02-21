---
title: 'Lync Server 2013 : meilleures pratiques pour le contrôle d’admission des appels'
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
ms.openlocfilehash: 1f9c7da9fd484ec0229417233de3f4338dd9f4b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Meilleures pratiques pour le contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-22_

Pour améliorer les performances et faciliter le déploiement, appliquez les meilleures pratiques suivantes lorsque vous déployez le contrôle d’admission des appels :

  - Assurez-vous que les réseaux étendus (WAN) sont correctement configurés pour le trafic multimédia actuel et prévu.
    
    <div>
    

    > [!NOTE]  
    > Nous vous recommandons de factoriser un tampon vers vos limites de bande passante. Certains scénarios, tels que les conditions de concurrence, affectent la bande passante totale utilisée et peuvent entraîner des situations dans lesquelles la limite de bande passante est dépassée. Par exemple, si deux appels essaient de démarrer alors que le trafic multimédia approche de la limite de bande passante, l’un d’entre eux peut être refusé, car l’autre a pu démarrer en premier.

    
    </div>

  - Surveillez l’utilisation du réseau et les enregistrements des détails des appels afin de pouvoir choisir les paramètres CAC optimaux et mettre à jour les paramètres CAC lorsque les modifications de l’utilisation du réseau

  - Utilisez les stratégies de bande passante CAC pour compléter les paramètres QoS.

  - Si vous souhaitez réacheminer les appels bloqués vers le réseau téléphonique commuté, vérifiez la capacité et la fonctionnalité PSTN. Pour plus d’informations, consultez la rubrique [planification de l’acheminement des communications vocales dans Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    <div>
    

    > [!NOTE]  
    > La capacité fait référence au nombre de ports que vous devez ouvrir afin de prendre en charge un éventuel réacheminement RTC.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

