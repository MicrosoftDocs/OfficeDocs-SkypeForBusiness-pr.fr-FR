---
title: 'Lync Server 2013 : Planification de la récupération d’urgence pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7da940f55574e1c6d50aeb06c0c80710bdbaad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Planification de la récupération d’urgence pour le parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-30_

Cette section décrit quelques méthodes de préparation de l’application de parc d’appels à des fins de reprise après sinistre et des éléments à prendre en compte lors du processus de reprise après sinistre.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Préparation de la reprise après sinistre du parc d’appels

Gardez les points suivants à l’esprit lorsque vous préparez et mettez en oeuvre des procédures de reprise après sinistre.

  - Prévoyez une reprise après sinistre lors de la planification de la capacité. Pour la capacité de reprise après sinistre, chaque pool dans un pool couplé doit être capable de gérer les charges de travail des services de parc d’appels dans les deux pools. Pour plus d’informations sur la planification de la capacité de parc d’appels, voir [planification de la capacité pour le parc d’appels dans Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent le service de parc d’appels qui s’exécute dans le pool de sauvegarde. Par conséquent, la prise en charge du parc d’appels lors d’une reprise après sinistre nécessite que l’application du parc d’appels soit déployée et activée dans le pool principal et dans le pool de sauvegarde.

  - Chaque liste doit avoir une plage de numéros en orbite valide pour les utilisateurs qui sont dans le groupe, à utiliser pour les appels en stationnement.

  - Conservez toujours une copie de sauvegarde séparée de tout morceau de musique personnalisé en attente qui a été téléchargé pour le parc d’appels. Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et seront perdus si les fichiers téléchargés vers le pool sont endommagés, endommagés ou supprimés.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Considérations en matière de reprise après sinistre du parc d’appels

Vous ne pouvez définir qu’un seul ensemble de paramètres de configuration d’application de parc d’appels et un seul fichier audio de musique personnalisé par liste. Ces paramètres incluent le seuil de temporisation, la musique en attente, les tentatives de sélection d’appels maximum et l’URI de délai d’expiration. Pour afficher ces paramètres de configuration, exécutez l’applet **de passe Get-CsCpsConfiguration** . Pour plus d’informations sur l’applet de connexion **Get-CsCpsConfiguration** , voir [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

En cas de reprise après sinistre, le parc d’appels utilise l’application de parc d’appels dans le pool de sauvegarde, de sorte que les paramètres du pool principal ne soient pas sauvegardés. Si le pool principal ne peut pas être récupéré et que vous déployez un nouveau pool pour remplacer le pool principal, les paramètres du pool principal sont perdus et vous devez reconfigurer les paramètres de parc d’appels et les fichiers audio de la musique personnalisée dans le nouveau pool.

Si vous déployez un nouveau pool avec un nom de domaine complet différent (FQDN) pour remplacer le pool principal, vous devez réaffecter toutes les plages d’orbite de parking d’appel associées au pool principal au FQDN du nouveau pool. Pour réattribuer des plages d’Orbit à la nouvelle liste de choix, vous pouvez utiliser le panneau de configuration de Lync Server ou l’applet **de commande Set-CsCallParkOrbit** . Pour plus d’informations sur l’applet **de connexion Set-CsCallParkOrbit** , reportez-vous à [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

