---
title: 'Lync Server 2013 : suppression des fichiers de mise à jour de périphérique non associés à un appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1376e82ac29efbe2fcbf996445a75fc3bea1492d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="080f7-102">Supprimer les fichiers de mise à jour des périphériques qui ne sont pas associés à un périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="080f7-102">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="080f7-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="080f7-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="080f7-104">Dès que de nouvelles mises à jour des périphériques sont téléchargées sur le système, une règle de mise correspondante est créée.</span><span class="sxs-lookup"><span data-stu-id="080f7-104">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="080f7-105">Par défaut, ces nouvelles règles de mise à jour des appareils sont affectées à l’État en attente.</span><span class="sxs-lookup"><span data-stu-id="080f7-105">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="080f7-106">Cela signifie que les règles peuvent être téléchargées et installées sur des périphériques de test, mais pas sur des appareils de production, ce qui vous permet de tester les mises à jour avant de les rendre accessibles aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="080f7-106">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="080f7-107">En fonction des tests, vous acceptez et déployez ou rejetez et supprimez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="080f7-107">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="080f7-108">Lorsque vous rejetez une mise à jour, la mise à jour de l’appareil n’est pas associée à sa règle de mise à jour d’appareil.</span><span class="sxs-lookup"><span data-stu-id="080f7-108">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="080f7-109">Les fichiers de mise à jour de périphérique qui ne sont plus associés à un périphérique peuvent être supprimés à l’aide de Windows PowerShell et de la cmdlet **Clear-CsDeviceUpdateFile** .</span><span class="sxs-lookup"><span data-stu-id="080f7-109">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="080f7-110">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="080f7-110">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="080f7-111">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="080f7-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="080f7-112">Par exemple, la commande suivante supprime toutes les règles de mise à jour des périphériques sur le serveur Web atl-cs-001.litwareinc.com qui ne sont plus associées à un périphérique :</span><span class="sxs-lookup"><span data-stu-id="080f7-112">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="080f7-113">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .</span><span class="sxs-lookup"><span data-stu-id="080f7-113">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

