---
title: 'Lync Server 2013 : création ou modification de profils de stratégie de bande passante'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="1d1c2-102">Création ou modification des profils de stratégie de bande passante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d1c2-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d1c2-103">_**Dernière modification de la rubrique :** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="1d1c2-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="1d1c2-104">Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des limitations de bande passante pour certaines modalités.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="1d1c2-105">Dans Microsoft Lync Server 2013, seules les modalités d’audio et de vidéo peuvent être affectées par des limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="1d1c2-106">Vous pouvez définir les limites générales de bande passante et les limites de session.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="1d1c2-107">Vous pouvez utiliser le panneau de configuration de Lync Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="1d1c2-108">Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="1d1c2-109">Pour créer ou modifier un profil de stratégie de bande passante, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="1d1c2-110">Pour supprimer un profil de stratégie de bande passante, reportez-vous à [suppression des profils de stratégie de bande passante réseau dans Lync 2013 Server](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1d1c2-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="1d1c2-111">Pour créer un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="1d1c2-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="1d1c2-112">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d1c2-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d1c2-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1d1c2-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d1c2-115">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="1d1c2-116">Dans la page **stratégie de bande passante** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="1d1c2-117">Dans **nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="1d1c2-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="1d1c2-118">Ce nom doit être unique parmi tous les profils de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="1d1c2-119">Dans le champ **limite audio** , entrez une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="1d1c2-120">Cette valeur correspond au nombre maximal de bande passante à allouer pour toutes les connexions audio, exprimée en kbps.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="1d1c2-121">Entrez une valeur numérique dans le champ **limite de session audio** .</span><span class="sxs-lookup"><span data-stu-id="1d1c2-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="1d1c2-122">Cette valeur correspond au volume maximal de bande passante à allouer pour une connexion audio individuelle, exprimée en kbps.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="1d1c2-123">Cette valeur doit être 40 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="1d1c2-124">Entrez une valeur numérique dans le champ **limite vidéo** .</span><span class="sxs-lookup"><span data-stu-id="1d1c2-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="1d1c2-125">Cette valeur correspond au volume maximal de bande passante à allouer pour toutes les connexions vidéo, exprimée en kbps.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="1d1c2-126">Entrez une valeur numérique dans le champ **limite de session vidéo** .</span><span class="sxs-lookup"><span data-stu-id="1d1c2-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="1d1c2-127">Cette valeur correspond au volume maximal de bande passante à allouer pour une connexion vidéo individuelle, exprimée en kbps.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="1d1c2-128">Cette valeur doit être 100 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="1d1c2-129">Facultatif Tapez une valeur dans le champ **Description** pour fournir des informations supplémentaires sur le profil de la stratégie de bande passante qui ne peut pas être exprimé uniquement par le nom.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="1d1c2-130">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d1c2-131">La création d’un profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="1d1c2-132">Vous devez d’abord associer le profil de la stratégie à un site.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="1d1c2-133">Pour plus d’informations sur l’Association d’un profil de stratégie à un site, voir <A href="lync-server-2013-creating-or-modifying-network-sites.md">création ou modification de sites réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="1d1c2-134">Pour modifier le profil d’une stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="1d1c2-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="1d1c2-135">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d1c2-136">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d1c2-137">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1d1c2-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d1c2-138">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="1d1c2-139">Dans la page **stratégie de bande passante** , cliquez sur le profil de la stratégie de bande passante que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="1d1c2-140">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1d1c2-141">Dans la page **modifier le profil de la stratégie de bande passante** , modifiez les champs si nécessaire (pour plus d’informations, consultez la section « pour créer un profil de stratégie de bande passante » plus haut dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="1d1c2-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="1d1c2-142">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d1c2-143">Lorsque vous modifiez le profil de la stratégie de bande passante, il met à jour immédiatement les limites de bande passante pour tous les sites réseau associés à ce profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d1c2-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d1c2-144">See Also</span></span>


[<span data-ttu-id="1d1c2-145">Supprimer des profils de stratégie de bande passante réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d1c2-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="1d1c2-146">Configurer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d1c2-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="1d1c2-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1d1c2-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="1d1c2-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1d1c2-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="1d1c2-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1d1c2-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

