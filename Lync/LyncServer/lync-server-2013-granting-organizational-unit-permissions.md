---
title: 'Lync Server 2013 : octroi d’autorisations d’unité d’organisation'
description: 'Lync Server 2013 : octroi d’autorisations d’unité d’organisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554510"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="dea44-103">Octroi d’autorisations d’unité d’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dea44-103">Granting organizational unit permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dea44-104">_**Dernière modification de la rubrique :** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="dea44-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="dea44-105">Vous pouvez utiliser l’applet de commande **Grant-CsOuPermission** pour accorder des autorisations à des objets dans des unités d’organisation (UO) spécifiées afin que les membres des groupes universels RTC créés par la préparation de la forêt puissent y accéder sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="dea44-105">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="dea44-106">Les autorisations ajoutées à l’unité d’organisation spécifiée sont les mêmes que celles que l’applet de commande **Enable-CsAdDomain** ajoute aux conteneurs ordinateurs et utilisateurs lors de la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="dea44-106">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="dea44-107">Utilisez l’applet de commande **test-CsOuPermission** pour vérifier les autorisations que vous avez configurées à l’aide de l’applet de commande **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="dea44-107">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="dea44-108">Vous pouvez utiliser l’applet de commande **Revoke-CsOuPermission** pour supprimer les autorisations que vous avez accordées à l’aide de la cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="dea44-108">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="dea44-109">Pour accorder des autorisations d’unité d’organisation</span><span class="sxs-lookup"><span data-stu-id="dea44-109">To grant OU permissions</span></span>

1.  <span data-ttu-id="dea44-110">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez accorder des autorisations d’unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="dea44-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="dea44-111">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="dea44-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="dea44-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dea44-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dea44-113">Générer</span><span class="sxs-lookup"><span data-stu-id="dea44-113">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="dea44-114">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="dea44-114">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="dea44-115">Pour vérifier les autorisations d’unité d’organisation</span><span class="sxs-lookup"><span data-stu-id="dea44-115">To verify OU permissions</span></span>

1.  <span data-ttu-id="dea44-116">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez vérifier les autorisations d’unité d’organisation que vous avez accordées à l’aide de la cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="dea44-116">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="dea44-117">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="dea44-117">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="dea44-118">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dea44-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dea44-119">Générer</span><span class="sxs-lookup"><span data-stu-id="dea44-119">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="dea44-120">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="dea44-120">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="dea44-121">Pour révoquer les autorisations d’unité d’organisation</span><span class="sxs-lookup"><span data-stu-id="dea44-121">To revoke OU permissions</span></span>

1.  <span data-ttu-id="dea44-122">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez révoquer les autorisations d’unité d’organisation qui ont été accordées par la cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="dea44-122">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="dea44-123">Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="dea44-123">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="dea44-124">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dea44-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dea44-125">Générer</span><span class="sxs-lookup"><span data-stu-id="dea44-125">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="dea44-126">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="dea44-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

