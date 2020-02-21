---
title: 'Lync Server 2013 : réinitialiser une règle de mise à jour de périphérique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa5bd589a6368e99401f2f84d702756d595f9be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="57c1b-102">Réinitialiser une règle de mise à jour de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57c1b-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57c1b-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="57c1b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="57c1b-104">Si vous n’aimez pas la façon dont une mise à jour fonctionne sur vos périphériques de test, vous pouvez réinitialiser la règle de mise à jour du périphérique, ce qui supprime l’État en attente de la règle et désinstalle la mise à jour des périphériques de test.</span><span class="sxs-lookup"><span data-stu-id="57c1b-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="57c1b-105">Vous pouvez supprimer une règle de mise à jour de périphérique à l’aide du panneau de configuration Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57c1b-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57c1b-106">Pour désinstaller une règle que vous avez déjà approuvée (c’est-à-dire, reprise), restaurez-la.</span><span class="sxs-lookup"><span data-stu-id="57c1b-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="57c1b-107">Pour plus d’informations, consultez <A href="lync-server-2013-restore-a-device-update-rule.md">la rubrique restaurer une règle de mise à jour des périphériques dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57c1b-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="57c1b-108">Pour réinitialiser une règle de mise à jour de périphérique à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="57c1b-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="57c1b-109">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="57c1b-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="57c1b-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57c1b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="57c1b-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="57c1b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="57c1b-112">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour des périphériques** .</span><span class="sxs-lookup"><span data-stu-id="57c1b-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="57c1b-113">Sur la page **mise à jour du périphérique** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="57c1b-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="57c1b-114">Pour réinitialiser une règle, sélectionnez la règle que vous souhaitez réinitialiser.</span><span class="sxs-lookup"><span data-stu-id="57c1b-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="57c1b-115">Pour réinitialiser toutes les règles, dans le menu **Edition** , cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="57c1b-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="57c1b-116">Pour réinitialiser toutes les règles d’une marque, utilisez le menu de la colonne **marque** .</span><span class="sxs-lookup"><span data-stu-id="57c1b-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="57c1b-117">Cliquez sur **action**, puis sur **annuler les mises à jour en attente**.</span><span class="sxs-lookup"><span data-stu-id="57c1b-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="57c1b-118">Si vous êtes sûr de vouloir ne jamais déployer les règles de mise à jour des périphériques que vous avez annulées, vous pouvez les supprimer.</span><span class="sxs-lookup"><span data-stu-id="57c1b-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="57c1b-119">Pour plus d’informations, consultez <A href="lync-server-2013-remove-a-device-update-rule.md">la rubrique supprimer une règle de mise à jour de périphérique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57c1b-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="57c1b-120">Réinitialisation d’une règle de mise à jour de périphérique à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57c1b-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="57c1b-121">Les règles de mise à jour des périphériques peuvent également être réinitialisées à l’aide de Windows PowerShell et de la cmdlet **Reset-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="57c1b-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="57c1b-122">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57c1b-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57c1b-123">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="57c1b-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="57c1b-124">Pour réinitialiser une règle de mise à jour d’appareil spécifique sur un serveur</span><span class="sxs-lookup"><span data-stu-id="57c1b-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="57c1b-125">La commande suivante réinitialise la règle de mise à jour de périphérique d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur Web atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="57c1b-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="57c1b-126">Pour réinitialiser toutes les règles de mise à jour des périphériques sur un serveur</span><span class="sxs-lookup"><span data-stu-id="57c1b-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="57c1b-127">Cette commande réinitialise toutes les règles de mise à jour des périphériques sur le serveur Web atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="57c1b-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="57c1b-128">Pour réinitialiser toutes les règles de mises à jour de périphériques qui ont une marque spécifique</span><span class="sxs-lookup"><span data-stu-id="57c1b-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="57c1b-129">Dans cet exemple, toutes les mises à jour de périphérique de l’organisation dont la marque est égale à Microsoft sont réinitialisées :</span><span class="sxs-lookup"><span data-stu-id="57c1b-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="57c1b-130">Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="57c1b-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57c1b-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57c1b-131">See Also</span></span>


[<span data-ttu-id="57c1b-132">Approuver une règle de mise à jour de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57c1b-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

