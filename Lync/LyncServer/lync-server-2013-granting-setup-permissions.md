---
title: 'Lync Server 2013 : Octroi d’autorisations de configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751ec9ba024780344596bfc0513c15f7e9eafec7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="c24c2-102">Octroi d’autorisations de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c24c2-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c24c2-103">_**Dernière modification de la rubrique:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="c24c2-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="c24c2-104">Vous pouvez utiliser l’applet de contrôle **Grant-CsSetupPermission** pour ajouter des autorisations de lecture, d’écriture, de ReadSPN et de WriteSPN au groupe RTCUniversalServerAdmins de l’unité d’organisation Active Directory spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c24c2-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="c24c2-105">Les membres du groupe RTCUniversalServerAdmins dans cette UO peuvent installer des serveurs exécutant Lync Server 2013 dans le domaine spécifié sans être membres du groupe administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="c24c2-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="c24c2-106">Utilisez l’applet de **contrôle test-CsSetupPermission** pour vérifier les autorisations que vous avez configurées à l’aide de l’applet de contrôle **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="c24c2-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="c24c2-107">Vous pouvez utiliser l’applet de passe **Revoke-CsSetupPermission** pour supprimer les autorisations accordées à l’aide de l’applet de passe **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="c24c2-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="c24c2-108">Pour accorder des autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="c24c2-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="c24c2-109">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine auquel vous voulez accorder des autorisations de configuration.</span><span class="sxs-lookup"><span data-stu-id="c24c2-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="c24c2-110">Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.</span><span class="sxs-lookup"><span data-stu-id="c24c2-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c24c2-111">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c24c2-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c24c2-112">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c24c2-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c24c2-113">Vous pouvez spécifier le paramètre ComputerOu en fonction du contexte de nommage par défaut du domaine spécifié (par exemple, CN = ordinateurs).</span><span class="sxs-lookup"><span data-stu-id="c24c2-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="c24c2-114">Vous pouvez également spécifier ce paramètre en tant que nom unique de l’unité de nom unique (DN) complet (par exemple, «CN = ordinateurs, DC = contoso, DC = com»).</span><span class="sxs-lookup"><span data-stu-id="c24c2-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="c24c2-115">Dans ce dernier cas, vous devez spécifier un DN d’unité d’organisation qui est cohérent avec le domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="c24c2-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="c24c2-116">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="c24c2-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="c24c2-117">Pour vérifier les autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="c24c2-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="c24c2-118">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine dans lequel vous voulez vérifier les autorisations de configuration que vous avez accordées à l’aide de l’applet de contrôle **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="c24c2-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="c24c2-119">Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.</span><span class="sxs-lookup"><span data-stu-id="c24c2-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c24c2-120">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c24c2-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c24c2-121">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c24c2-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c24c2-122">Vous pouvez spécifier le paramètre ComputerOu en fonction du contexte de nommage par défaut du domaine spécifié (par exemple, CN = ordinateurs).</span><span class="sxs-lookup"><span data-stu-id="c24c2-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="c24c2-123">Vous pouvez également spécifier ce paramètre en tant que nom unique de l’unité de nom unique (DN) complet (par exemple, «CN = ordinateurs, DC = contoso, DC = com»).</span><span class="sxs-lookup"><span data-stu-id="c24c2-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="c24c2-124">Dans ce dernier cas, vous devez spécifier un DN d’unité d’organisation qui est cohérent avec le domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="c24c2-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="c24c2-125">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="c24c2-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="c24c2-126">Pour révoquer les autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="c24c2-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="c24c2-127">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine dans lequel vous voulez révoquer les autorisations de configuration accordées par l’applet de connexion **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="c24c2-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="c24c2-128">Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.</span><span class="sxs-lookup"><span data-stu-id="c24c2-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c24c2-129">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c24c2-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c24c2-130">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c24c2-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c24c2-131">Vous pouvez spécifier le paramètre ComputerOu en fonction du contexte de nommage par défaut du domaine spécifié (par exemple, CN = ordinateurs).</span><span class="sxs-lookup"><span data-stu-id="c24c2-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="c24c2-132">Vous pouvez également spécifier ce paramètre en tant que nom unique de l’unité de nom unique (DN) complet (par exemple, «CN = ordinateurs, DC = contoso, DC = com»).</span><span class="sxs-lookup"><span data-stu-id="c24c2-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="c24c2-133">Dans ce dernier cas, vous devez spécifier un DN d’unité d’organisation qui est cohérent avec le domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="c24c2-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="c24c2-134">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="c24c2-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

