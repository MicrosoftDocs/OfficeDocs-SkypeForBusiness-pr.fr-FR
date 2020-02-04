---
title: 'Lync Server 2013 : supprimer une règle de mise à jour d’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d367c507ea2e8871231248b1f29d7d033dedbe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="e009c-102">Supprimer une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e009c-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e009c-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e009c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e009c-104">La suppression d’une règle de mise à jour d’appareil permet de supprimer définitivement la file d’attente de mise à jour de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e009c-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="e009c-105">La suppression d’une règle est différente de la désinstallation d’une mise à jour à partir des appareils de votre déploiement ou de vos périphériques de test.</span><span class="sxs-lookup"><span data-stu-id="e009c-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="e009c-106">Pour désinstaller une mise à jour approuvée de votre déploiement, vous *restaurez* la règle de mise à jour de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e009c-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="e009c-107">Pour plus d’informations, reportez-vous à [restaurer une règle de mise à jour d’appareil dans Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="e009c-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="e009c-108">Pour désinstaller une mise à jour que vous n’avez pas approuvée de vos appareils de test, vous pouvez la *Réinitialiser* .</span><span class="sxs-lookup"><span data-stu-id="e009c-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="e009c-109">Pour plus d’informations, voir [Réinitialiser une règle de mise à jour d’appareil dans Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="e009c-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="e009c-110">Vous pouvez supprimer une règle de mise à jour de l’appareil en utilisant le panneau de configuration de Lync Server ou Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e009c-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="e009c-111">Pour supprimer les règles de mise à jour des appareils à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e009c-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e009c-112">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e009c-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e009c-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e009c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e009c-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e009c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e009c-115">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour d’appareil** .</span><span class="sxs-lookup"><span data-stu-id="e009c-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="e009c-116">Dans la page **mise à jour** de l’appareil, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e009c-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e009c-117">Pour supprimer une règle, sélectionnez la règle que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="e009c-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="e009c-118">Pour supprimer toutes les règles, cliquez sur le menu **modifier** , puis sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="e009c-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="e009c-119">Cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e009c-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e009c-120">Suppression des règles de mise à jour des appareils à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e009c-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e009c-121">Les règles de mise à jour d’appareils peuvent également être supprimées à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="e009c-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="e009c-122">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e009c-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e009c-123">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="e009c-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="e009c-124">Pour supprimer une seule règle de mise à jour d’un appareil d’un serveur</span><span class="sxs-lookup"><span data-stu-id="e009c-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="e009c-125">La commande suivante supprime la règle de mise à jour de l’appareil d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 du serveur Web sur atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e009c-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="e009c-126">Pour supprimer toutes les règles de mise à jour d’appareil d’un serveur</span><span class="sxs-lookup"><span data-stu-id="e009c-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="e009c-127">Cette commande supprime toutes les règles de mise à jour de l’appareil du serveur Web sur atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e009c-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="e009c-128">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="e009c-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e009c-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e009c-129">See Also</span></span>


[<span data-ttu-id="e009c-130">Approuver une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e009c-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

