---
title: 'Lync Server 2013 : surveillance des fichiers journaux de suivi de requête IIS'
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
ms.openlocfilehash: 3d29082fd4f2e988d586501d4d867be0dc23a0c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="6a61b-102">Surveiller les fichiers journaux de suivi de requête IIS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a61b-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a61b-103">_**Dernière modification de la rubrique :** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="6a61b-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="6a61b-104">Lorsque vous activez le suivi des demandes d’accès à Internet Information Services (IIS) pour le service de mobilité Lync Server (MCX), les fichiers journaux générés peuvent utiliser jusqu’à 3 Go d’espace disque par jour.</span><span class="sxs-lookup"><span data-stu-id="6a61b-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="6a61b-105">La journalisation du suivi IIS est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="6a61b-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="6a61b-106">Vous devez surveiller les serveurs front-end pour vous assurer qu’ils ne sont pas à court d’espace disque.</span><span class="sxs-lookup"><span data-stu-id="6a61b-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="6a61b-107">Par défaut, IIS stocke les fichiers journaux dans% SystemDrive\\%\\Inetpub\\journaux.</span><span class="sxs-lookup"><span data-stu-id="6a61b-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="6a61b-108">Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="6a61b-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="6a61b-109">Pour plus d’informations \*\*\*\* sur la commande httpLogging [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927), voir.</span><span class="sxs-lookup"><span data-stu-id="6a61b-109">For details about the **httpLogging** command, see [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

