---
title: 'Lync Server 2013 : restaurer une règle de mise à jour de périphérique'
description: 'Lync Server 2013 : restaurer une règle de mise à jour d’appareil.'
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
ms.openlocfilehash: b3696bc7e074bfd7bea04b08246f07e107d4d0b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543890"
---
# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="20bb3-103">Restaurer une règle de mise à jour de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20bb3-103">Restore a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20bb3-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="20bb3-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="20bb3-105">Pour désinstaller une règle de mise à jour de périphérique à partir des appareils de votre déploiement, restaurez-la.</span><span class="sxs-lookup"><span data-stu-id="20bb3-105">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="20bb3-106">La restauration d’une règle de mise à jour de périphérique désinstalle la mise à jour et réinstalle la version précédente de cette règle.</span><span class="sxs-lookup"><span data-stu-id="20bb3-106">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="20bb3-107">Vous pouvez restaurer une règle de mise à jour des périphériques à l’aide du panneau de configuration Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20bb3-107">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="20bb3-108">Pour restaurer des règles de mise à jour des périphériques à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="20bb3-108">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="20bb3-109">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="20bb3-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="20bb3-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20bb3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="20bb3-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="20bb3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="20bb3-112">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour des périphériques** .</span><span class="sxs-lookup"><span data-stu-id="20bb3-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="20bb3-113">Sur la page **mise à jour du périphérique** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="20bb3-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="20bb3-114">Pour restaurer une règle, sélectionnez cette règle.</span><span class="sxs-lookup"><span data-stu-id="20bb3-114">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="20bb3-115">Pour restaurer toutes les règles, cliquez sur **modifier**, puis cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="20bb3-115">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="20bb3-116">Cliquez sur le menu **action** , puis sur **restaurer**.</span><span class="sxs-lookup"><span data-stu-id="20bb3-116">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="20bb3-117">Restauration des règles de mise à jour des périphériques à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20bb3-117">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="20bb3-118">Les règles de mise à jour des appareils peuvent également être restaurées à l’aide de Windows PowerShell et de la cmdlet **Restore-CsDeviceUpdateRule** ..</span><span class="sxs-lookup"><span data-stu-id="20bb3-118">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="20bb3-119">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20bb3-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20bb3-120">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="20bb3-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="20bb3-121">Pour restaurer une règle de mise à jour de périphérique unique sur un serveur</span><span class="sxs-lookup"><span data-stu-id="20bb3-121">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="20bb3-122">La commande suivante restaure la règle de mise à jour de périphérique d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur Web atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="20bb3-122">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="20bb3-123">Pour restaurer toutes les règles de mise à jour des périphériques sur un serveur</span><span class="sxs-lookup"><span data-stu-id="20bb3-123">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="20bb3-124">Cette commande restaure toutes les règles de mise à jour des périphériques sur le serveur Web atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="20bb3-124">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="20bb3-125">Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="20bb3-125">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

