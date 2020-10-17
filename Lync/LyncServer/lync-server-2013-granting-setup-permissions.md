---
title: 'Lync Server 2013 : octroi d’autorisations de configuration'
description: 'Lync Server 2013 : octroi d’autorisations de configuration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554480"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="525c2-103">Octroi d’autorisations de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="525c2-103">Granting setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="525c2-104">_**Dernière modification de la rubrique :** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="525c2-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="525c2-105">L’applet de commande **Grant-CsSetupPermission** vous permet d’ajouter des autorisations Read, Write, ReadSPN et WriteSPN au groupe RTCUniversalServerAdmins d’une unité d’organisation (UO) Active Directory spécifiée.</span><span class="sxs-lookup"><span data-stu-id="525c2-105">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="525c2-106">Les membres du groupe RTCUniversalServerAdmins de cette unité d’organisation peuvent alors installer des serveurs exécutant Lync Server 2013 dans le domaine spécifié sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="525c2-106">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="525c2-107">L’applet de commande **Test-CsSetupPermission** vous permet de vérifier les autorisations que vous avez configurées à l’aide de l’applet de commande **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="525c2-107">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="525c2-108">L’applet de commande **Revoke-CsSetupPermission** vous permet de supprimer les autorisations que vous avez accordées à l’aide de l’applet de commande **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="525c2-108">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="525c2-109">Pour accorder des autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="525c2-109">To grant setup permissions</span></span>

1.  <span data-ttu-id="525c2-110">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez accorder des autorisations de configuration.</span><span class="sxs-lookup"><span data-stu-id="525c2-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="525c2-111">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="525c2-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="525c2-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="525c2-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="525c2-113">Générer</span><span class="sxs-lookup"><span data-stu-id="525c2-113">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="525c2-p103">Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="525c2-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="525c2-117">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="525c2-117">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="525c2-118">Pour vérifier les autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="525c2-118">To verify setup permissions</span></span>

1.  <span data-ttu-id="525c2-119">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez vérifier les autorisations d’installation que vous avez accordées à l’aide de la cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="525c2-119">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="525c2-120">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="525c2-120">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="525c2-121">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="525c2-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="525c2-122">Générer</span><span class="sxs-lookup"><span data-stu-id="525c2-122">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="525c2-p105">Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="525c2-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="525c2-126">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="525c2-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="525c2-127">Pour révoquer des autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="525c2-127">To revoke setup permissions</span></span>

1.  <span data-ttu-id="525c2-128">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez révoquer les autorisations d’installation accordées par la cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="525c2-128">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="525c2-129">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="525c2-129">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="525c2-130">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="525c2-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="525c2-131">Générer</span><span class="sxs-lookup"><span data-stu-id="525c2-131">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="525c2-p107">Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="525c2-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="525c2-135">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="525c2-135">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

