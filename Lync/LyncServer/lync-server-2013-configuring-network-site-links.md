---
title: 'Lync Server 2013: configuration de liens de site réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ddd5e28cd37cd31e28e5c6427b9b700b5a4c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="9886f-102">Configuration de liens de site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9886f-102">Configuring network site links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9886f-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9886f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9886f-104">Dans le cadre d’une configuration de contrôle d’admission des appels (CAC), vous pouvez créer des stratégies entre site réseau qui définissent les limitations de bande passante entre les sites qui sont directement liés.</span><span class="sxs-lookup"><span data-stu-id="9886f-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="9886f-105">Lorsque les sites réseau partagent un lien direct, les limites de bande passante pour les connexions audio et vidéo peuvent être définies entre ces deux sites.</span><span class="sxs-lookup"><span data-stu-id="9886f-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="9886f-106">Dans le panneau de configuration de Lync Server, vous ne pouvez pas utiliser l’applet de commande de Lync Server Management Shell pour configurer les stratégies de site réseau.</span><span class="sxs-lookup"><span data-stu-id="9886f-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="9886f-107">Vous pouvez créer, modifier et supprimer un lien de site réseau (également connu sous le nom de stratégie intersite réseau) de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9886f-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="9886f-108">Pour créer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="9886f-108">To create a network site link</span></span>

1.  <span data-ttu-id="9886f-109">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9886f-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9886f-110">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9886f-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9886f-111">À partir de l’invite de commandes, tapez la commande suivante, en remplaçant les valeurs valides pour votre configuration:</span><span class="sxs-lookup"><span data-stu-id="9886f-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="9886f-112">Cet exemple crée un lien de site réseau intitulé Reno\_Portland qui définit les limites de bande passante entre les sites réseau Reno et Portland.</span><span class="sxs-lookup"><span data-stu-id="9886f-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="9886f-113">Les sites réseau et le profil de la stratégie de bande passante doivent déjà exister avant d’exécuter cette commande.</span><span class="sxs-lookup"><span data-stu-id="9886f-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="9886f-114">Pour obtenir une description détaillée des paramètres, consultez la rubrique [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9886f-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="9886f-115">Pour récupérer la liste des profils de stratégie de bande passante qui peuvent être appliqués au lien site réseau, appelez l’applet **de passe Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="9886f-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="9886f-116">Pour plus d’informations, consultez la rubrique [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9886f-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="9886f-117">Pour modifier un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="9886f-117">To modify a network site link</span></span>

1.  <span data-ttu-id="9886f-118">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9886f-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9886f-119">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9886f-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9886f-120">Utilisez l’applet de connexion **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné.</span><span class="sxs-lookup"><span data-stu-id="9886f-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="9886f-121">Vous pouvez modifier l’un ou l’autre des sites connectés, et vous pouvez modifier le profil de la stratégie de bande passante associé au lien.</span><span class="sxs-lookup"><span data-stu-id="9886f-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="9886f-122">Voici un exemple de modification du profil de la stratégie de bande passante d’un lien\_de site nommé Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="9886f-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="9886f-123">Pour obtenir une description détaillée des paramètres, consultez la rubrique [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9886f-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="9886f-124">Pour supprimer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="9886f-124">To delete a network site link</span></span>

1.  <span data-ttu-id="9886f-125">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9886f-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9886f-126">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9886f-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9886f-127">Utilisez l’applet de connexion **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau.</span><span class="sxs-lookup"><span data-stu-id="9886f-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="9886f-128">Dans l’exemple suivant, le lien\_vers le site réseau de Portland de Reno est supprimé:</span><span class="sxs-lookup"><span data-stu-id="9886f-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="9886f-129">Pour obtenir une description détaillée des paramètres, consultez la rubrique [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9886f-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9886f-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9886f-130">See Also</span></span>


[<span data-ttu-id="9886f-131">Applets de commande de contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9886f-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="9886f-132">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="9886f-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="9886f-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="9886f-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="9886f-134">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="9886f-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="9886f-135">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="9886f-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="9886f-136">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="9886f-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

