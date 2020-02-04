---
title: 'Lync Server 2013 : affichage des paramètres de configuration de la mise à jour des dispositifs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01edeb2d40fae7b82ac35fb5561a1332f67c9e11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8b8fa-102">Affichage des paramètres de configuration de la mise à jour des dispositifs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b8fa-102">View Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b8fa-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8b8fa-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8b8fa-104">Vous pouvez afficher les paramètres de configuration du service de mise à jour de l’appareil à l’aide de Lync Server Management Shell et de l’applet de commande **Get-CsDeviceUpdateConfiguration** , que vous pouvez exécuter à partir de lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b8fa-104">You can view the Device Update Service configuration settings by using Lync Server Management Shell and the **Get-CsDeviceUpdateConfiguration** cmdlet, which you can run from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b8fa-105">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="8b8fa-105">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>


  - <span data-ttu-id="8b8fa-106">Pour afficher des informations sur l’ensemble de vos itinéraires vocaux, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="8b8fa-106">To view information about all your voice routes, type the following command in the Lync Server Management Shell and press Enter:</span></span>
    
        Get-CsDeviceUpdateConfiguration
    
    <span data-ttu-id="8b8fa-107">Cette commande renvoie le type d’informations suivant :</span><span class="sxs-lookup"><span data-stu-id="8b8fa-107">This command returns information similar to the following:</span></span>
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

<span data-ttu-id="8b8fa-108">Pour plus d’informations sur cette applet de connexion, consultez la rubrique d’aide sur [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8b8fa-108">For details about this cmdlet, see Help topic at [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

