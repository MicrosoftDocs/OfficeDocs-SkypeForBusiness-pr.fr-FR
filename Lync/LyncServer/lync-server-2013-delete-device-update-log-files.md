---
title: 'Lync Server 2013 : supprimer les fichiers journaux de mise à jour de l’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c684978445f727dc155fade59654ff6e2866f084
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="763ff-102">Supprimer des fichiers journaux de mise à jour de périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="763ff-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="763ff-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="763ff-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="763ff-104">Le service Web de mise à jour des appareils conserve une collection complète de fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="763ff-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="763ff-105">Cette collection inclut les journaux d’audit effectués par le service proprement dit, ainsi que les fichiers journaux téléchargés à partir des appareils clients.</span><span class="sxs-lookup"><span data-stu-id="763ff-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="763ff-106">Pour empêcher le serveur de saturer les journaux de service Web de mise à jour de l’appareil, vous souhaiterez probablement effacer les fichiers journaux qui se trouvent dans un certain nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="763ff-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="763ff-107">Définissez le nombre de jours en fonction de l’activité de mise à jour et du nombre d’appareils clients au sein de votre organisation, et à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="763ff-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="763ff-108">Pour vider le journal des mises à jour de l’appareil à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="763ff-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="763ff-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="763ff-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="763ff-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="763ff-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="763ff-111">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur **configuration du journal de périphériques**.</span><span class="sxs-lookup"><span data-stu-id="763ff-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="763ff-112">Dans la page **configuration du journal des appareils** , double-cliquez sur la configuration que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="763ff-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="763ff-113">Dans la boîte de dialogue **modifier les paramètres du journal** , en **nombre de jours pour conserver les fichiers journaux (1-365)**, spécifiez un nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="763ff-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="763ff-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="763ff-114">Click **Commit**.</span></span> <span data-ttu-id="763ff-115">Tous les fichiers qui se trouvent sur le serveur pour plus d’informations sur le nombre de jours spécifié sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="763ff-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="763ff-116">Ce paramètre sera appliqué à cette configuration tant que vous ne la modifiez pas.</span><span class="sxs-lookup"><span data-stu-id="763ff-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="763ff-117">Effacement du journal de mise à jour de l’appareil à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="763ff-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="763ff-118">Vous pouvez effacer les journaux de mise à jour de l’appareil à l’aide de Windows PowerShell et de l’applet **de connexion Clear-CsDeviceUpdateLog** .</span><span class="sxs-lookup"><span data-stu-id="763ff-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="763ff-119">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="763ff-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="763ff-120">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="763ff-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="763ff-121">Pour effacer les journaux de mise à jour de l’appareil sur un serveur</span><span class="sxs-lookup"><span data-stu-id="763ff-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="763ff-122">La commande suivante efface le journal de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="763ff-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="763ff-123">Toutes les entrées du journal de plus de 10 jours (la valeur spécifiée par le paramètre DaysBack) sera supprimée du journal.</span><span class="sxs-lookup"><span data-stu-id="763ff-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="763ff-124">Pour effacer tous les journaux de mise à jour de l’appareil</span><span class="sxs-lookup"><span data-stu-id="763ff-124">To clear all device update logs</span></span>

  - <span data-ttu-id="763ff-125">Cette commande supprime les entrées obsolètes (dans cet exemple, les entrées de plus de 10 jours) de tous les journaux de mise à jour d’appareils actuellement utilisés au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="763ff-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="763ff-126">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .</span><span class="sxs-lookup"><span data-stu-id="763ff-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

