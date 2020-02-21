---
title: 'Lync Server 2013 : approuver une règle de mise à jour de périphérique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c6fad9547e9c738523ac0f460d3e6696d1920a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="29f3a-102">Approuver une règle de mise à jour de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29f3a-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29f3a-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="29f3a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="29f3a-104">Une fois que vous avez importé une règle de mise à jour de périphérique, celle-ci est installée sur vos périphériques de test.</span><span class="sxs-lookup"><span data-stu-id="29f3a-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="29f3a-105">Si le test réussit et que vous souhaitez déployer la mise à jour pour votre organisation, approuvez-le à l’aide du panneau de configuration Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29f3a-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="29f3a-106">Pour approuver une règle de mise à jour de périphérique à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="29f3a-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="29f3a-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="29f3a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="29f3a-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29f3a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29f3a-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="29f3a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="29f3a-110">Sur la page **mise à jour du périphérique** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="29f3a-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="29f3a-111">Pour approuver une règle, sélectionnez cette règle.</span><span class="sxs-lookup"><span data-stu-id="29f3a-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="29f3a-112">Pour approuver toutes les règles, cliquez sur **modifier**, puis cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="29f3a-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="29f3a-113">Cliquez sur **action**, puis sur **approuver**.</span><span class="sxs-lookup"><span data-stu-id="29f3a-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="29f3a-114">Approbation d’une règle de mise à jour de périphérique à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29f3a-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="29f3a-115">Les règles de mise à jour des périphériques peuvent également être approuvées à l’aide de Windows PowerShell et de la cmdlet **Approve-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="29f3a-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="29f3a-116">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29f3a-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29f3a-117">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="29f3a-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="29f3a-118">Pour approuver une règle de mise à jour de périphérique unique</span><span class="sxs-lookup"><span data-stu-id="29f3a-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="29f3a-119">La commande suivante approuve la règle de mise à jour de périphérique d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 trouvée sur le serveur Web atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="29f3a-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="29f3a-120">Pour approuver plusieurs règles de mise à jour des périphériques</span><span class="sxs-lookup"><span data-stu-id="29f3a-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="29f3a-121">Cette commande approuve toutes les règles de mise à jour des appareils pour les périphériques de marque Microsoft :</span><span class="sxs-lookup"><span data-stu-id="29f3a-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="29f3a-122">Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="29f3a-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29f3a-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29f3a-123">See Also</span></span>


[<span data-ttu-id="29f3a-124">Importer des règles de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29f3a-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="29f3a-125">Restaurer une règle de mise à jour de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29f3a-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

