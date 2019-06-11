---
title: 'Lync Server 2013 : Basculement vers un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Basculement vers un pool dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Une fois que le regroupement qui a expérimenté le désastre est en ligne (à savoir Pool1 dans cet exemple), procédez comme suit pour restaurer le statut de travail normal de votre déploiement.

Notez que le processus de restauration automatique prend quelques minutes.À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.

1.  Restaurez les utilisateurs qui ont été initialement hébergés dans Pool1 et qui ont échoué sur Pool2 en tapant l’applet de commande suivante:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Aucune autre étape n’est nécessaire. Si vous avez échoué sur le serveur de gestion central, vous pouvez le laisser dans Pool2.

</div>

<span> </span>

</div>

</div>

</div>

