---
title: 'Lync Server 2013 : création ou modification de régions réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04f85e4546d8cfa3154c2fc5a87676ff0377795b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="f8a09-102">Création ou modification de régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8a09-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8a09-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f8a09-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f8a09-104">Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="f8a09-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f8a09-105">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="f8a09-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="f8a09-106">Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute.</span><span class="sxs-lookup"><span data-stu-id="f8a09-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="f8a09-107">Vous pouvez utiliser le panneau de configuration Lync Server pour configurer des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="f8a09-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="f8a09-108">Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="f8a09-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="f8a09-109">Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="f8a09-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="f8a09-110">Consultez la rubrique pour créer et modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="f8a09-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="f8a09-111">Pour plus d’informations sur la suppression des régions réseau existantes, voir [Suppression de régions réseau existantes dans Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="f8a09-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="f8a09-112">Pour créer une région réseau</span><span class="sxs-lookup"><span data-stu-id="f8a09-112">To create a network region</span></span>

1.  <span data-ttu-id="f8a09-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f8a09-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8a09-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8a09-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8a09-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f8a09-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8a09-116">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.</span><span class="sxs-lookup"><span data-stu-id="f8a09-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="f8a09-117">Dans la page **Région**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f8a09-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="f8a09-118">Tapez une valeur dans le champ **Nom** de la page **Nouvelle région**.</span><span class="sxs-lookup"><span data-stu-id="f8a09-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="f8a09-119">Cette valeur doit être unique dans votre déploiement de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8a09-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="f8a09-120">Dans la liste déroulante **Site central**, sélectionnez le site central pour cette région réseau.</span><span class="sxs-lookup"><span data-stu-id="f8a09-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="f8a09-p104">La case à cocher **Activer un autre chemin d’accès à l’audio** est activée par défaut. Ce champ détermine si les appels audio seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.</span><span class="sxs-lookup"><span data-stu-id="f8a09-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="f8a09-p105">La case à cocher **Activer un autre chemin d’accès à la vidéo** est activée par défaut. Ce champ détermine si les appels vidéo seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.</span><span class="sxs-lookup"><span data-stu-id="f8a09-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="f8a09-129">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région, car son nom seul ne suffit pas à la décrire.</span><span class="sxs-lookup"><span data-stu-id="f8a09-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="f8a09-130">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f8a09-130">Click **Commit**.</span></span>

<span data-ttu-id="f8a09-131">Le tableau **Sites associés** n’est pas utilisé pour la création d’une région réseau.</span><span class="sxs-lookup"><span data-stu-id="f8a09-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="f8a09-132">Vous associez un site à une région lorsque vous créez ou modifiez le site.</span><span class="sxs-lookup"><span data-stu-id="f8a09-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="f8a09-133">Pour plus d’informations, reportez-vous à la rubrique [création ou modification de sites réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="f8a09-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="f8a09-134">Pour modifier une région réseau</span><span class="sxs-lookup"><span data-stu-id="f8a09-134">To modify a network region</span></span>

1.  <span data-ttu-id="f8a09-135">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f8a09-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8a09-136">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8a09-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8a09-137">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f8a09-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8a09-138">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.</span><span class="sxs-lookup"><span data-stu-id="f8a09-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="f8a09-139">Dans la page **Région**, cliquez sur la région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="f8a09-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="f8a09-140">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f8a09-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f8a09-141">Dans la page **Modifier la région**, vous pouvez modifier les paramètres permettant d’activer et de désactiver les chemins audio et vidéo alternatifs et modifier également la description (pour plus d’informations, voir la section « Pour créer une région réseau » plus haut dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="f8a09-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="f8a09-142">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f8a09-142">Click **Commit**.</span></span>

<span data-ttu-id="f8a09-p108">Vous ne pouvez pas modifier les **sites associés** sur cette page. La liste des sites associés est fournie à titre de référence pour vous informer des sites qui seront affectés par la modification des paramètres de région.</span><span class="sxs-lookup"><span data-stu-id="f8a09-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8a09-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8a09-145">See Also</span></span>


[<span data-ttu-id="f8a09-146">Suppression des régions réseau existantes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8a09-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="f8a09-147">Configuration des régions réseau pour le contrôle d’admission des serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8a09-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="f8a09-148">New-applet csnetworkregion</span><span class="sxs-lookup"><span data-stu-id="f8a09-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="f8a09-149">Set-applet csnetworkregion</span><span class="sxs-lookup"><span data-stu-id="f8a09-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="f8a09-150">Remove-applet csnetworkregion</span><span class="sxs-lookup"><span data-stu-id="f8a09-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="f8a09-151">Get-applet csnetworkregion</span><span class="sxs-lookup"><span data-stu-id="f8a09-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

