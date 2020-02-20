---
title: 'Lync Server 2013 : création ou modification des profils de stratégie de bande passante'
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
ms.openlocfilehash: b40b4a397ffe3eeeaade138542e5634bf8f7afd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="82695-102">Création ou modification des profils de stratégie de bande passante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82695-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82695-103">_**Dernière modification de la rubrique :** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="82695-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="82695-104">La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis.</span><span class="sxs-lookup"><span data-stu-id="82695-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="82695-105">Dans Microsoft Lync Server 2013, seules les modalités audio et vidéo peuvent se voir affecter des limites de bande passante.</span><span class="sxs-lookup"><span data-stu-id="82695-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="82695-106">Vous pouvez définir des restrictions de bande passante et de session globales.</span><span class="sxs-lookup"><span data-stu-id="82695-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="82695-107">Vous pouvez utiliser le panneau de configuration Lync Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="82695-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="82695-108">Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau.</span><span class="sxs-lookup"><span data-stu-id="82695-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="82695-109">Effectuez les procédures suivantes pour créer ou modifier un profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="82695-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="82695-110">Pour supprimer un profil de stratégie de bande passante, consultez [la rubrique Suppression des profils de stratégie de bande passante réseau dans Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="82695-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="82695-111">Pour créer un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="82695-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="82695-112">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="82695-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="82695-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82695-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="82695-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="82695-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="82695-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="82695-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="82695-116">Dans la page **Stratégie de bande passante**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="82695-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="82695-p103">Dans **Nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **Nom**. Ce nom doit être unique parmi tous les profils de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="82695-p103">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="82695-p104">Dans le champ **Limite audio**, tapez une valeur numérique. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions audio.</span><span class="sxs-lookup"><span data-stu-id="82695-p104">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="82695-p105">Entrez une valeur numérique dans le champ **Limite de session audio**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion audio. Cette valeur doit être égale ou supérieure à 40.</span><span class="sxs-lookup"><span data-stu-id="82695-p105">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="82695-p106">Entrez une valeur numérique dans le champ **Limite vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions vidéo.</span><span class="sxs-lookup"><span data-stu-id="82695-p106">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="82695-p107">Entrez une valeur numérique dans le champ **Limite de session vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion vidéo. Cette valeur doit être égale ou supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="82695-p107">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="82695-129">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce profil de stratégie de bande passante, car son nom ne suffit pas à le décrire.</span><span class="sxs-lookup"><span data-stu-id="82695-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="82695-130">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="82695-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82695-131">La création d’un nouveau profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="82695-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="82695-132">Vous devez d’abord associer le profil de stratégie à un site.</span><span class="sxs-lookup"><span data-stu-id="82695-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="82695-133">Pour plus d’informations sur l’Association d’un profil de stratégie à un site, voir <A href="lync-server-2013-creating-or-modifying-network-sites.md">création ou modification de sites réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="82695-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="82695-134">Pour modifier un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="82695-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="82695-135">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="82695-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="82695-136">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82695-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="82695-137">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="82695-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="82695-138">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="82695-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="82695-139">Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="82695-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="82695-140">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="82695-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="82695-141">Dans la page **Modifier le profil de stratégie de bande passante**, modifiez les champs comme il convient (pour plus d’informations, voir la section « Pour créer un profil de stratégie de bande passante » plus haut dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="82695-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="82695-142">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="82695-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82695-143">Lorsque vous modifiez le profil de stratégie de bande passante, celui-ci met immédiatement à jour les restrictions de bande passante de tous les sites réseau qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="82695-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82695-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82695-144">See Also</span></span>


[<span data-ttu-id="82695-145">Suppression des profils de stratégie de bande passante réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82695-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="82695-146">Configurer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82695-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="82695-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="82695-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="82695-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="82695-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="82695-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="82695-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

