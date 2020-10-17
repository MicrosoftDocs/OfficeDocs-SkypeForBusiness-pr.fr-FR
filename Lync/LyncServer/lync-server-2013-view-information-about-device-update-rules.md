---
title: 'Lync Server 2013 : affichage des informations sur les règles de mise à jour des appareils'
description: 'Lync Server 2013 : Affichez des informations sur les règles de mise à jour des appareils.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4aecfd0dd778b576ea4a672e550f9e27d7ca463e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569630"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="73d03-103">Afficher des informations sur les règles de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73d03-103">View information about Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73d03-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="73d03-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="73d03-105">Afficher les détails sur les règles de mise à jour des périphériques qui ont déjà été importées, y compris le type, le modèle et la marque des périphériques auxquels la mise à jour s’applique ; version et type de mise à jour ; et les paramètres régionaux et pool pour la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="73d03-105">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="73d03-106">Les informations sont disponibles pour toutes les règles de mise à jour des appareils importées, celles qui sont en attente d’approbation, déployées (approuvées), rappelées (restaurées) et celles que vous avez décidé de ne pas utiliser (Réinitialiser).</span><span class="sxs-lookup"><span data-stu-id="73d03-106">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="73d03-107">Accédez à ces informations à partir du panneau de configuration Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73d03-107">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73d03-108">Pour plus d’informations sur l’importation, l’approbation, la réinitialisation, la restauration et la suppression de règles, voir les rubriques répertoriées <A href="lync-server-2013-device-update-rules.md">dans règles de mise à jour des périphériques dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73d03-108">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="73d03-109">Pour afficher les règles de mise à jour des périphériques à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="73d03-109">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="73d03-110">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="73d03-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73d03-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73d03-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73d03-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="73d03-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="73d03-113">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour des périphériques** .</span><span class="sxs-lookup"><span data-stu-id="73d03-113">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="73d03-114">Les règles importées sont répertoriées dans la page **mise à jour du périphérique** .</span><span class="sxs-lookup"><span data-stu-id="73d03-114">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="73d03-115">Affichage des règles de mise à jour des périphériques à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73d03-115">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="73d03-116">Vous pouvez également afficher des informations détaillées sur toutes les règles de mise à jour des appareils à l’aide de Windows PowerShell et de la cmdlet **Get-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="73d03-116">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="73d03-117">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73d03-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73d03-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="73d03-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="73d03-119">Pour afficher toutes les règles de mise à jour des appareils</span><span class="sxs-lookup"><span data-stu-id="73d03-119">To view all your device update rules</span></span>

  - <span data-ttu-id="73d03-120">La commande suivante retourne des informations sur toutes les règles de mises à jour de périphériques configurées pour être utilisées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="73d03-120">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="73d03-121">La commande retourne des informations semblables aux suivantes pour chacune de vos règles de mise à jour de périphérique :</span><span class="sxs-lookup"><span data-stu-id="73d03-121">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="73d03-122">Pour afficher toutes les règles de mise à jour des périphériques sur un serveur Web spécifique</span><span class="sxs-lookup"><span data-stu-id="73d03-122">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="73d03-123">Pour afficher les règles de mise à jour des périphériques sur un ordinateur spécifique, utilisez le paramètre Filter suivi de l’identité du serveur et du caractère générique ( \* ).</span><span class="sxs-lookup"><span data-stu-id="73d03-123">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="73d03-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="73d03-124">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="73d03-125">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="73d03-125">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

