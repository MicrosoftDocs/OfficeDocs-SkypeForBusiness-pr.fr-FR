---
title: 'Lync Server 2013 : supprimer les fichiers de mise à jour d’appareils non associés à un appareil'
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
ms.openlocfilehash: 42a2579360fbb4af8d6f3c491f5a56c380b593d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="4a706-102">Supprimer les fichiers de mise à jour des appareils non associés à un appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a706-102">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a706-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="4a706-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="4a706-104">Chaque fois que de nouvelles mises à jour de périphériques sont téléchargées sur le système, une règle de mise à jour d’appareil correspondante est créée.</span><span class="sxs-lookup"><span data-stu-id="4a706-104">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="4a706-105">Par défaut, ces nouvelles règles de mise à jour de l’appareil sont affectées à l’État en attente.</span><span class="sxs-lookup"><span data-stu-id="4a706-105">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="4a706-106">Cela signifie que les règles peuvent être téléchargées et installées sur les appareils de test, mais pas sur les appareils de production, ce qui vous permet de tester les mises à jour avant de les rendre accessibles aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a706-106">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="4a706-107">D’après les tests, vous acceptez et déployez ou rejetez et supprimez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="4a706-107">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="4a706-108">Lorsque vous refusez une mise à jour, la mise à jour de l’appareil est désassociée de sa règle de mise à jour de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="4a706-108">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="4a706-109">Les fichiers de mise à jour d’appareil qui ne sont plus associés à un appareil peuvent être supprimés à l’aide de Windows PowerShell et de l’applet **de cmdlet Clear-CsDeviceUpdateFile** .</span><span class="sxs-lookup"><span data-stu-id="4a706-109">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="4a706-110">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a706-110">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a706-111">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="4a706-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="4a706-112">Par exemple, la commande suivante supprime toutes les règles de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com qui ne sont plus associées à un appareil :</span><span class="sxs-lookup"><span data-stu-id="4a706-112">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="4a706-113">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .</span><span class="sxs-lookup"><span data-stu-id="4a706-113">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

