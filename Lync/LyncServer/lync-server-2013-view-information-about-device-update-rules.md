---
title: 'Lync Server 2013: afficher des informations sur les règles de mise à jour des appareils'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="d2ac2-102">Afficher des informations sur les règles de mise à jour des appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2ac2-102">View information about Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2ac2-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d2ac2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d2ac2-104">Afficher des détails sur les règles de mise à jour d’appareils qui ont déjà été importées, dont le type, le modèle et la marque des appareils auxquels la mise à jour s’applique; version et type de mise à jour; et des paramètres régionaux et du pool pour la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d2ac2-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="d2ac2-105">Des informations sont disponibles pour toutes les règles de mise à jour d’appareils importées, celles-ci sont en attente d’approbation, de déploiement (approuvé), de rappel (restauration) et de celles que vous avez choisi de ne pas utiliser (Réinitialiser).</span><span class="sxs-lookup"><span data-stu-id="d2ac2-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="d2ac2-106">Accédez à ces informations à partir du panneau de configuration de Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2ac2-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2ac2-107">Pour plus d’informations sur l’importation, l’approbation, la réinitialisation, la restauration et la suppression de règles, voir les rubriques répertoriées dans les <A href="lync-server-2013-device-update-rules.md">règles de mise à jour des appareils de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d2ac2-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="d2ac2-108">Pour afficher les règles de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d2ac2-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d2ac2-109">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="d2ac2-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d2ac2-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2ac2-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d2ac2-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d2ac2-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d2ac2-112">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour d’appareil** .</span><span class="sxs-lookup"><span data-stu-id="d2ac2-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="d2ac2-113">Les règles importées sont répertoriées dans la page de **mise à jour** de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="d2ac2-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d2ac2-114">Affichage des règles de mise à jour des appareils à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2ac2-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d2ac2-115">Vous pouvez également afficher des informations détaillées sur toutes les règles de mise à jour de l’appareil à l’aide de Windows PowerShell et de l’applet **de passe Get-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="d2ac2-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="d2ac2-116">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2ac2-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2ac2-117">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="d2ac2-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="d2ac2-118">Pour afficher toutes les règles de mise à jour de l’appareil</span><span class="sxs-lookup"><span data-stu-id="d2ac2-118">To view all your device update rules</span></span>

  - <span data-ttu-id="d2ac2-119">La commande suivante renvoie des informations sur toutes les règles de mise à jour de l’appareil configurées pour une utilisation au sein de votre organisation:</span><span class="sxs-lookup"><span data-stu-id="d2ac2-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="d2ac2-120">La commande renvoie des informations similaires à ce qui suit pour chacune de vos règles de mise à jour de l’appareil:</span><span class="sxs-lookup"><span data-stu-id="d2ac2-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
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

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="d2ac2-121">Pour afficher toutes les règles de mise à jour de l’appareil sur un serveur Web spécifique</span><span class="sxs-lookup"><span data-stu-id="d2ac2-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="d2ac2-122">Pour afficher les règles de mise à jour de l’appareil sur un ordinateur spécifique, utilisez le paramètre de filtre suivi de l’identité\*du serveur et du caractère générique ().</span><span class="sxs-lookup"><span data-stu-id="d2ac2-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="d2ac2-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d2ac2-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="d2ac2-124">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="d2ac2-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

