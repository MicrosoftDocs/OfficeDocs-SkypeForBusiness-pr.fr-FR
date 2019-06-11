---
title: 'Lync Server 2013: création ou modification d’une stratégie de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d3f03735048ab4354db9653554b6227bb7399e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="b8ea7-102">Création ou modification d’une stratégie de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8ea7-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8ea7-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b8ea7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b8ea7-104">Vous pouvez créer ou modifier une stratégie de mobilité pour autoriser les utilisateurs mobiles à utiliser les appareils mobiles pris en charge pour les fonctionnalités Lync telles que la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b8ea7-105">Vous pouvez créer ou modifier des stratégies de mobilité depuis le panneau de configuration de Lync Server 2013 ou Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="b8ea7-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="b8ea7-106">Pour créer une stratégie de mobilité avec le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b8ea7-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b8ea7-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b8ea7-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b8ea7-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b8ea7-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b8ea7-110">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de la **stratégie de mobilité** .</span><span class="sxs-lookup"><span data-stu-id="b8ea7-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="b8ea7-111">Dans la page **stratégie de mobilité** , cliquez sur **nouveau**, puis effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="b8ea7-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="b8ea7-112">Pour créer une stratégie de mobilité de site, cliquez sur **stratégie de site**, cliquez sur un site, cliquez sur **OK**, passez en revue les paramètres par défaut et, si vous le souhaitez, apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="b8ea7-113">Pour créer une stratégie de mobilité des utilisateurs, cliquez sur stratégie de l' **utilisateur**, tapez un nom, passez en revue les paramètres par défaut et, si vous le souhaitez, apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="b8ea7-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="b8ea7-115">Pour modifier une stratégie de mobilité avec le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b8ea7-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b8ea7-116">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b8ea7-117">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b8ea7-118">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b8ea7-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b8ea7-119">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de la **stratégie de mobilité** .</span><span class="sxs-lookup"><span data-stu-id="b8ea7-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="b8ea7-120">Dans la page **stratégie de mobilité** , cliquez sur l’une des stratégies de mobilité existantes.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="b8ea7-121">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b8ea7-122">Modifiez les paramètres.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="b8ea7-123">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b8ea7-124">Création de stratégies d’accès externe à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8ea7-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b8ea7-125">Vous pouvez créer des stratégies de mobilité (à l’étendue du site ou l’étendue par utilisateur) à l’aide de Windows PowerShell et de l’applet **de nouvelle cmdlet New-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b8ea7-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="b8ea7-126">De plus, vous pouvez utiliser l’applet de passe **Set-CsMobilityPolicy** pour modifier l’une de vos stratégies existantes, y compris la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="b8ea7-127">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b8ea7-128">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="b8ea7-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="b8ea7-129">Pour créer une stratégie de mobilité sur l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="b8ea7-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="b8ea7-130">Cette commande crée une nouvelle stratégie de mobilité pour le site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="b8ea7-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="b8ea7-131">Dans la mesure où aucun paramètre (autre que le paramètre d’identité obligatoire) n’a été spécifié dans la commande précédente, les stratégies utilisent les valeurs par défaut de toutes les propriétés.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="b8ea7-132">Pour créer une stratégie de mobilité pour l’étendue par utilisateur</span><span class="sxs-lookup"><span data-stu-id="b8ea7-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="b8ea7-133">Pour créer une stratégie de mobilité pour l’étendue par utilisateur, spécifiez une identité unique pour la stratégie:</span><span class="sxs-lookup"><span data-stu-id="b8ea7-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="b8ea7-134">Pour modifier une valeur de propriété unique lors de la création d’une stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="b8ea7-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="b8ea7-135">Pour créer des stratégies qui utilisent des valeurs de propriété différentes, incluez le paramètre et la valeur de paramètre appropriés.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-135">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="b8ea7-136">Par exemple, cette commande crée une stratégie de mobilité qui désactive l’appel via le Bureau:</span><span class="sxs-lookup"><span data-stu-id="b8ea7-136">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="b8ea7-137">Pour modifier plusieurs valeurs de propriétés lors de la création d’une stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="b8ea7-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="b8ea7-138">Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="b8ea7-138">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="b8ea7-139">Par exemple, cette commande crée une stratégie qui désactive la mobilité et l’appel via le Bureau:</span><span class="sxs-lookup"><span data-stu-id="b8ea7-139">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="b8ea7-140">Pour plus d’informations, consultez la rubrique d’aide pour les applets de [nouvelle-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) et [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .</span><span class="sxs-lookup"><span data-stu-id="b8ea7-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8ea7-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8ea7-141">See Also</span></span>


[<span data-ttu-id="b8ea7-142">Configuration de la stratégie de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8ea7-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

