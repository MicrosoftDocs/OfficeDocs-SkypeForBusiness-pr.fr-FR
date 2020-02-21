---
title: 'Lync Server 2013 : planification de la récupération d’urgence du parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae06a3d0e3e404781e2f51ef18e1ba2ca76d72b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Planification de la récupération d’urgence par le parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Cette section décrit certaines façons de préparer l’application de parcage d’appel pour la récupération d’urgence et quelques considérations pour le processus de récupération d’urgence.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Préparation de la récupération d’urgence du parcage d’appel

Gardez les informations suivantes à l’esprit lorsque vous préparez et menez à bien les procédures de récupération d’urgence.

  - Planifiez la récupération d’urgence lorsque vous effectuez votre planification de capacité. Pour la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel dans les deux pools. Pour plus d’informations sur la planification de la capacité du parcage d’appel, voir [Capacity Planning for Call parcage in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durant la récupération d’urgence, les utilisateurs redirigés vers le pool de sauvegarde durant le processus de basculement utilisent le service de parcage d’appel exécuté dans le pool de sauvegarde. Par conséquent, la prise en charge du parcage d’appel pendant la récupération d’urgence nécessite le déploiement et l’activation de l’application de parcage d’appel dans le pool principal et le pool de sauvegarde.

  - Chaque pool doit avoir une plage de numéros d’orbite valable pour que les utilisateurs hébergés dans ce pool puissent utiliser le parcage d’appels.

  - Conservez toujours une copie de sauvegarde distincte de toute musique personnalisée en conservation qui a été téléchargée pour le parcage d’appel. Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et seront perdus si les fichiers chargés vers le pool sont endommagés, endommagés ou effacés.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Considérations relatives à la récupération d’urgence du parcage d’appel

Vous ne pouvez définir qu’un seul ensemble de paramètres de configuration de l’application de parcage d’appel et un seul fichier audio de mise en attente musicale personnalisé par pool. Ces paramètres incluent le seuil d’expiration, la musique d’attente, le nombre maximum de tentatives de prises d’appels, et l’URI d’expiration. Pour afficher ces paramètres de configuration, exécutez la cmdlet **Get-CsCpsConfiguration**. Pour plus d’informations sur la cmdlet **Get-CsCpsConfiguration** , voir [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Pendant la récupération d’urgence, le parcage d’appel utilise l’application de parcage d’appel dans le pool de sauvegarde, de sorte que les paramètres du pool principal ne sont pas sauvegardés. Si le pool principal ne peut pas être récupéré et si vous déployez un nouveau pool pour remplacer le pool principal, les paramètres du pool principal sont perdus et vous devez reconfigurer les paramètres de parcage d’appel et tous les fichiers audio de la musique personnalisée dans le nouveau pool.

Si vous déployez un nouveau pool avec un nom de domaine complet (FQDN) différent pour remplacer le pool principal, vous devez réaffecter toutes les plages d’orbites de parcage d’appel associées au pool principal au nom de domaine complet du nouveau pool. Pour réaffecter les plages d’orbites au nouveau pool, vous pouvez utiliser le panneau de configuration Lync Server ou la cmdlet **Set-CsCallParkOrbit** . Pour plus d’informations sur l’applet de commande **Set-CsCallParkOrbit** , voir [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

