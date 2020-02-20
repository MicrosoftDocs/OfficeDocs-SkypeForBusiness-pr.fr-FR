---
title: 'Lync Server 2013 : octroi d’autorisations de configuration'
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
ms.openlocfilehash: 014af4f0e03a8d49e3d08c68cff169283bd007bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="e3339-102">Octroi d’autorisations de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3339-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3339-103">_**Dernière modification de la rubrique :** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="e3339-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="e3339-104">L’applet de commande **Grant-CsSetupPermission** vous permet d’ajouter des autorisations Read, Write, ReadSPN et WriteSPN au groupe RTCUniversalServerAdmins d’une unité d’organisation (UO) Active Directory spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e3339-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="e3339-105">Les membres du groupe RTCUniversalServerAdmins de cette unité d’organisation peuvent alors installer des serveurs exécutant Lync Server 2013 dans le domaine spécifié sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="e3339-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="e3339-106">L’applet de commande **Test-CsSetupPermission** vous permet de vérifier les autorisations que vous avez configurées à l’aide de l’applet de commande **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="e3339-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="e3339-107">L’applet de commande **Revoke-CsSetupPermission** vous permet de supprimer les autorisations que vous avez accordées à l’aide de l’applet de commande **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="e3339-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="e3339-108">Pour accorder des autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="e3339-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="e3339-109">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez accorder des autorisations de configuration.</span><span class="sxs-lookup"><span data-stu-id="e3339-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="e3339-110">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="e3339-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e3339-111">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e3339-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e3339-112">Générer</span><span class="sxs-lookup"><span data-stu-id="e3339-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e3339-p103">Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="e3339-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="e3339-116">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="e3339-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="e3339-117">Pour vérifier les autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="e3339-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="e3339-118">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez vérifier les autorisations d’installation que vous avez accordées à l’aide de la cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="e3339-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="e3339-119">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="e3339-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e3339-120">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e3339-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e3339-121">Générer</span><span class="sxs-lookup"><span data-stu-id="e3339-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e3339-p105">Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="e3339-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="e3339-125">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="e3339-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="e3339-126">Pour révoquer des autorisations de configuration</span><span class="sxs-lookup"><span data-stu-id="e3339-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="e3339-127">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez révoquer les autorisations d’installation accordées par la cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="e3339-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="e3339-128">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="e3339-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e3339-129">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e3339-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e3339-130">Générer</span><span class="sxs-lookup"><span data-stu-id="e3339-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e3339-p107">Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="e3339-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="e3339-134">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="e3339-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

