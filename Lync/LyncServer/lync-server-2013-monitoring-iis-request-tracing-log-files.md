---
title: 'Lync Server 2013: surveillance des fichiers journaux de suivi de requête IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Surveiller les fichiers journaux de suivi de requête IIS dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Lorsque vous activez le suivi des demandes d’accès à Internet Information Services (IIS) pour le service de mobilité Lync Server (MCX), les fichiers journaux générés peuvent utiliser jusqu’à 3 Go d’espace disque par jour. La journalisation du suivi IIS est activée par défaut. Vous devez surveiller les serveurs front-end pour vous assurer qu’ils ne sont pas à court d’espace disque.

Par défaut, IIS stocke les fichiers journaux dans% SystemDrive\\%\\Inetpub\\journaux.

Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Pour plus d’informations **** sur la commande httpLogging [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927), voir.

</div>

<span> </span>

</div>

</div>

</div>

