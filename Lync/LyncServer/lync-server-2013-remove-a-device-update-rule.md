---
title: 'Lync Server 2013 : suppression d’une règle de mise à jour de périphérique'
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
ms.openlocfilehash: 13b639e6541478874e80ab632b2ee231ea65151d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="8fa70-102">Supprimer une règle de mise à jour de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fa70-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fa70-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8fa70-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8fa70-104">La suppression d’une règle de mise à jour de périphérique supprime définitivement la file d’attente de mise à jour des périphériques.</span><span class="sxs-lookup"><span data-stu-id="8fa70-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="8fa70-105">La suppression d’une règle est différente de la désinstallation d’une mise à jour des appareils de votre déploiement ou de vos périphériques de test.</span><span class="sxs-lookup"><span data-stu-id="8fa70-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="8fa70-106">Pour désinstaller une mise à jour approuvée de votre déploiement, vous devez *restaurer* la règle de mise à jour des périphériques.</span><span class="sxs-lookup"><span data-stu-id="8fa70-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="8fa70-107">Pour plus d’informations, consultez [la rubrique restaurer une règle de mise à jour des périphériques dans Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="8fa70-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="8fa70-108">Pour désinstaller une mise à jour que vous n’avez pas approuvée de vos périphériques de test, vous devez la *Réinitialiser* .</span><span class="sxs-lookup"><span data-stu-id="8fa70-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="8fa70-109">Pour plus d’informations, voir [Réinitialiser une règle de mise à jour de périphérique dans Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="8fa70-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="8fa70-110">Vous pouvez supprimer une règle de mise à jour de périphérique à l’aide du panneau de configuration Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8fa70-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="8fa70-111">Pour supprimer des règles de mise à jour des périphériques à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fa70-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8fa70-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8fa70-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8fa70-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8fa70-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8fa70-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8fa70-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8fa70-115">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour des périphériques** .</span><span class="sxs-lookup"><span data-stu-id="8fa70-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="8fa70-116">Sur la page **mise à jour du périphérique** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8fa70-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="8fa70-117">Pour supprimer une règle, sélectionnez la règle que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="8fa70-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="8fa70-118">Pour supprimer toutes les règles, cliquez sur le menu **Edition** , puis cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="8fa70-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="8fa70-119">Cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8fa70-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8fa70-120">Suppression des règles de mise à jour des périphériques à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fa70-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8fa70-121">Les règles de mise à jour des périphériques peuvent également être supprimées à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="8fa70-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="8fa70-122">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8fa70-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8fa70-123">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="8fa70-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="8fa70-124">Pour supprimer une seule règle de mise à jour de périphérique d’un serveur</span><span class="sxs-lookup"><span data-stu-id="8fa70-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="8fa70-125">La commande suivante supprime la règle de mise à jour de périphérique d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 du serveur Web sur atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8fa70-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="8fa70-126">Pour supprimer toutes les règles de mise à jour des périphériques d’un serveur</span><span class="sxs-lookup"><span data-stu-id="8fa70-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="8fa70-127">Cette commande supprime toutes les règles de mise à jour des périphériques du serveur Web sur atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8fa70-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="8fa70-128">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="8fa70-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8fa70-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8fa70-129">See Also</span></span>


[<span data-ttu-id="8fa70-130">Approuver une règle de mise à jour de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fa70-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

