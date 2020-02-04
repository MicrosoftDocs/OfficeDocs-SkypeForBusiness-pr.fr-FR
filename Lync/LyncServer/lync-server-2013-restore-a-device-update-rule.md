---
title: 'Lync Server 2013 : restaurer une règle de mise à jour d’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0416092c7021d599ec7e516d72c19e8baa3c598
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="d1c70-102">Restaurer une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c70-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1c70-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d1c70-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d1c70-104">Pour désinstaller une règle de mise à jour de l’appareil des appareils de votre déploiement, restaurez-la.</span><span class="sxs-lookup"><span data-stu-id="d1c70-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="d1c70-105">La restauration d’une règle de mise à jour de l’appareil à la fois désinstalle la mise à jour et réinstalle la version précédente de cette règle.</span><span class="sxs-lookup"><span data-stu-id="d1c70-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="d1c70-106">Vous pouvez restaurer une règle de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c70-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="d1c70-107">Pour restaurer les règles de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d1c70-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d1c70-108">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="d1c70-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d1c70-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1c70-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1c70-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d1c70-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1c70-111">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour d’appareil** .</span><span class="sxs-lookup"><span data-stu-id="d1c70-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="d1c70-112">Dans la page **mise à jour** de l’appareil, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1c70-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d1c70-113">Pour restaurer une règle, sélectionnez cette règle.</span><span class="sxs-lookup"><span data-stu-id="d1c70-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="d1c70-114">Pour restaurer toutes les règles, cliquez sur **modifier**, puis sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="d1c70-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="d1c70-115">Cliquez sur le menu **action** , puis cliquez sur **restaurer**.</span><span class="sxs-lookup"><span data-stu-id="d1c70-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d1c70-116">Restauration de règles de mise à jour de l’appareil à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1c70-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d1c70-117">Les règles de mises à jour de périphériques peuvent également être restaurées à l’aide de Windows PowerShell et de l’applet de passe **Restore-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="d1c70-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="d1c70-118">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c70-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1c70-119">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="d1c70-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="d1c70-120">Pour restaurer une seule règle de mise à jour d’un appareil sur un serveur</span><span class="sxs-lookup"><span data-stu-id="d1c70-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="d1c70-121">La commande suivante restaure la règle de mise à jour d’appareil d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur Web atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="d1c70-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="d1c70-122">Pour restaurer toutes les règles de mise à jour de l’appareil sur un serveur</span><span class="sxs-lookup"><span data-stu-id="d1c70-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="d1c70-123">Cette commande restaure toutes les règles de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="d1c70-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="d1c70-124">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="d1c70-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

