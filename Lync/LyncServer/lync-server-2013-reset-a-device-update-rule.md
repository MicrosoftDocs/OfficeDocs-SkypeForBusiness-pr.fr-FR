---
title: 'Lync Server 2013: réinitialiser une règle de mise à jour d’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab03c5c28db28ddbd883f3f50845eaf91d4fd1a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="26d4a-102">Réinitialiser une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d4a-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d4a-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="26d4a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="26d4a-104">Si vous ne voulez pas que la mise à jour fonctionne sur vos appareils de test, vous pouvez réinitialiser la règle de mise à jour de l’appareil, qui supprime l’État en attente de la règle et désinstaller la mise à jour des périphériques de test.</span><span class="sxs-lookup"><span data-stu-id="26d4a-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="26d4a-105">Vous pouvez supprimer une règle de mise à jour de l’appareil en utilisant le panneau de configuration de Lync Server ou Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26d4a-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26d4a-106">Pour désinstaller une règle que vous avez déjà approuvée (qui est déployée), restaurez-la.</span><span class="sxs-lookup"><span data-stu-id="26d4a-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="26d4a-107">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-restore-a-device-update-rule.md">restaurer une règle de mise à jour d’appareil dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d4a-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="26d4a-108">Pour réinitialiser une règle de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="26d4a-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="26d4a-109">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="26d4a-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="26d4a-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="26d4a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="26d4a-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26d4a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="26d4a-112">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour d’appareil** .</span><span class="sxs-lookup"><span data-stu-id="26d4a-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="26d4a-113">Dans la page **mise à jour** de l’appareil, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="26d4a-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="26d4a-114">Pour réinitialiser une règle, sélectionnez la règle que vous voulez réinitialiser.</span><span class="sxs-lookup"><span data-stu-id="26d4a-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="26d4a-115">Pour réinitialiser toutes les règles, dans le menu **édition** , cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="26d4a-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="26d4a-116">Pour réinitialiser toutes les règles pour une seule marque, utilisez le menu de la colonne de **marque** .</span><span class="sxs-lookup"><span data-stu-id="26d4a-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="26d4a-117">Cliquez sur **action**, puis sur **annuler les mises à jour en attente**.</span><span class="sxs-lookup"><span data-stu-id="26d4a-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="26d4a-118">Si vous êtes sûr de ne jamais vouloir déployer les règles de mise à jour de l’appareil que vous avez annulées, vous souhaiterez peut-être les supprimer.</span><span class="sxs-lookup"><span data-stu-id="26d4a-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="26d4a-119">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-remove-a-device-update-rule.md">supprimer une règle de mise à jour d’appareil dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d4a-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="26d4a-120">Réinitialisation d’une règle de mise à jour de l’appareil à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26d4a-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="26d4a-121">Les règles de mise à jour d’appareils peuvent également être réinitialisées à l’aide de Windows PowerShell et de l’applet de passe **Reset-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="26d4a-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="26d4a-122">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26d4a-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26d4a-123">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="26d4a-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="26d4a-124">Pour réinitialiser une règle de mise à jour de l’appareil spécifique sur un serveur</span><span class="sxs-lookup"><span data-stu-id="26d4a-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="26d4a-125">La commande suivante réinitialise la règle de mise à jour de l’appareil d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="26d4a-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="26d4a-126">Pour réinitialiser toutes les règles de mise à jour de l’appareil sur un serveur</span><span class="sxs-lookup"><span data-stu-id="26d4a-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="26d4a-127">Cette commande réinitialise toutes les règles de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="26d4a-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="26d4a-128">Pour réinitialiser toutes les règles de mises à jour de périphériques ayant une marque spécifique</span><span class="sxs-lookup"><span data-stu-id="26d4a-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="26d4a-129">Dans cet exemple, toutes les mises à jour de l’appareil dans l’ensemble de l’organisation dont la marque est égale à Microsoft sont réinitialisées:</span><span class="sxs-lookup"><span data-stu-id="26d4a-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="26d4a-130">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="26d4a-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="26d4a-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26d4a-131">See Also</span></span>


[<span data-ttu-id="26d4a-132">Approuver une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d4a-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

