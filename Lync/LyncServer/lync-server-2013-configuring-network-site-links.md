---
title: 'Lync Server 2013 : configuration des liens de sites réseau'
description: 'Lync Server 2013 : configuration des liens de sites réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68b4ecce15b8f3ba5a5717c73a8f97f8a0633b58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572930"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="e2c51-103">Configuration des liens de sites réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2c51-103">Configuring network site links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2c51-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e2c51-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e2c51-105">Dans une configuration de contrôle d’admission des appels (CAC), vous pouvez créer des stratégies réseau intersite qui définissent les limitations de bande passante entre les sites qui sont directement liés.</span><span class="sxs-lookup"><span data-stu-id="e2c51-105">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="e2c51-106">Quand des sites de réseau partagent un lien direct, des restrictions de bande passante pour les connexions audio et vidéo peuvent être définies pour lesdits sites.</span><span class="sxs-lookup"><span data-stu-id="e2c51-106">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="e2c51-107">Vous ne pouvez pas utiliser le panneau de configuration Lync Server pour configurer des stratégies de site réseau, mais vous ne pouvez le faire qu’à l’aide d’applets de commande de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2c51-107">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="e2c51-108">Vous pouvez créer, modifier et supprimer un lien de site réseau (également appelé stratégie inter-site réseau) à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2c51-108">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="e2c51-109">Pour créer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="e2c51-109">To create a network site link</span></span>

1.  <span data-ttu-id="e2c51-110">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e2c51-110">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e2c51-111">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2c51-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e2c51-112">À l’invite de commandes, tapez la commande suivante en spécifiant les valeurs valides pour votre configuration :</span><span class="sxs-lookup"><span data-stu-id="e2c51-112">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="e2c51-113">Cet exemple crée un lien de site réseau nommé Reno \_ Portland qui définit des limites de bande passante entre les sites réseau Reno et Portland.</span><span class="sxs-lookup"><span data-stu-id="e2c51-113">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="e2c51-114">Les sites réseau et le profil de stratégie de bande passante doivent être existants avant d’exécuter cette commande.</span><span class="sxs-lookup"><span data-stu-id="e2c51-114">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="e2c51-115">Pour obtenir des descriptions détaillées des paramètres, voir [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2c51-115">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="e2c51-116">Pour récupérer une liste des profils de stratégie de bande passante pouvant être appliqués au lien de site réseau, appelez l’applet de commande **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="e2c51-116">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="e2c51-117">Pour plus d’informations, reportez-vous à [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2c51-117">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="e2c51-118">Pour modifier un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="e2c51-118">To modify a network site link</span></span>

1.  <span data-ttu-id="e2c51-119">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e2c51-119">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e2c51-120">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2c51-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e2c51-121">Utilisez l’applet de commande **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné.</span><span class="sxs-lookup"><span data-stu-id="e2c51-121">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="e2c51-122">Vous pouvez modifier l’un ou l’autre des sites connectés, ou les deux, ainsi que le profil de stratégie de bande passante associé au lien.</span><span class="sxs-lookup"><span data-stu-id="e2c51-122">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="e2c51-123">Voici un exemple de modification du profil de stratégie de bande passante d’un lien de site nommé Reno \_ Portland :</span><span class="sxs-lookup"><span data-stu-id="e2c51-123">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="e2c51-124">Pour obtenir des descriptions détaillées des paramètres, voir [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2c51-124">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="e2c51-125">Pour supprimer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="e2c51-125">To delete a network site link</span></span>

1.  <span data-ttu-id="e2c51-126">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e2c51-126">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e2c51-127">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2c51-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e2c51-128">Utilisez l’applet de commande **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau.</span><span class="sxs-lookup"><span data-stu-id="e2c51-128">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="e2c51-129">L’exemple suivant supprime le lien de \_ site de réseau Portland Reno :</span><span class="sxs-lookup"><span data-stu-id="e2c51-129">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="e2c51-130">Pour obtenir des descriptions détaillées des paramètres, voir [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2c51-130">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2c51-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2c51-131">See Also</span></span>


[<span data-ttu-id="e2c51-132">Applets de commande de contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2c51-132">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="e2c51-133">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e2c51-133">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="e2c51-134">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e2c51-134">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="e2c51-135">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e2c51-135">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="e2c51-136">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e2c51-136">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="e2c51-137">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="e2c51-137">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

