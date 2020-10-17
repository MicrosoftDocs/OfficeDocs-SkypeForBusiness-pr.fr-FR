---
title: 'Lync Server 2013 : surveillance des fichiers journaux de suivi des demandes IIS'
description: 'Lync Server 2013 : surveillance des fichiers journaux de suivi des demandes IIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09692b79b1cc59ad18ad520885c0a795736b53cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569950"
---
# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="69624-103">Surveillance des fichiers journaux de suivi des demandes IIS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69624-103">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69624-104">_**Dernière modification de la rubrique :** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="69624-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="69624-105">Lorsque vous activez le suivi des demandes IIS (Internet Information Services) pour le service Lync Server Mobility (MCX), les fichiers journaux générés peuvent consommer jusqu’à trois gigaoctets d’espace disque par jour.</span><span class="sxs-lookup"><span data-stu-id="69624-105">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="69624-106">La journalisation du suivi IIS est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="69624-106">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="69624-107">Vous devez analyser les serveurs frontaux pour vous assurer qu’ils ne manquent pas d’espace disque.</span><span class="sxs-lookup"><span data-stu-id="69624-107">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="69624-108">Par défaut, les services Internet (IIS) stockent les fichiers journaux dans% SystemDrive% \\ Inetpub \\ logs journaux \\ .</span><span class="sxs-lookup"><span data-stu-id="69624-108">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="69624-109">Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="69624-109">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="69624-110">Pour plus d’informations sur la commande **httpLogging** , reportez-vous à la rubrique [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927) .</span><span class="sxs-lookup"><span data-stu-id="69624-110">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

