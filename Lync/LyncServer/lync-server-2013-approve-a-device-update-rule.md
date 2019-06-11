---
title: 'Lync Server 2013: approuver une règle de mise à jour de l’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa560be6b8c341310c4831277902dab6f2e5552c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="094a9-102">Approuver une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="094a9-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="094a9-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="094a9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="094a9-104">Une fois que vous avez importé une règle de mise à jour de l’appareil, celle-ci est installée sur vos appareils de test.</span><span class="sxs-lookup"><span data-stu-id="094a9-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="094a9-105">Si le test est concluant et que vous souhaitez déployer la mise à jour de votre organisation, approuvez-la à l’aide du panneau de configuration de Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="094a9-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="094a9-106">Pour approuver une règle de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="094a9-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="094a9-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="094a9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="094a9-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="094a9-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="094a9-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="094a9-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="094a9-110">Dans la page **mise à jour** de l’appareil, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="094a9-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="094a9-111">Pour approuver une règle, sélectionnez cette règle.</span><span class="sxs-lookup"><span data-stu-id="094a9-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="094a9-112">Pour approuver toutes les règles, cliquez sur **modifier**, puis sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="094a9-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="094a9-113">Cliquez sur **action**, puis cliquez sur **approuver**.</span><span class="sxs-lookup"><span data-stu-id="094a9-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="094a9-114">Approbation d’une règle de mise à jour de l’appareil à l’aide des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="094a9-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="094a9-115">Les règles de mise à jour d’appareils peuvent également être approuvées à l’aide de Windows PowerShell et de l’applet de passe approbateur **-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="094a9-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="094a9-116">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="094a9-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="094a9-117">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="094a9-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="094a9-118">Pour approuver une seule règle de mise à jour de l’appareil</span><span class="sxs-lookup"><span data-stu-id="094a9-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="094a9-119">La commande suivante approuve la règle de mise à jour de l’appareil d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 trouvée sur le serveur Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="094a9-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="094a9-120">Pour approuver plusieurs règles de mise à jour de l’appareil</span><span class="sxs-lookup"><span data-stu-id="094a9-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="094a9-121">Cette commande approuve toutes les règles de mise à jour d’appareils pour les appareils de marque Microsoft:</span><span class="sxs-lookup"><span data-stu-id="094a9-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="094a9-122">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion approbateur [-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="094a9-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="094a9-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="094a9-123">See Also</span></span>


[<span data-ttu-id="094a9-124">Importer des règles de mise à jour de périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="094a9-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="094a9-125">Restaurer une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="094a9-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

