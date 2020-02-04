---
title: 'Lync Server 2013 : Octroi d’autorisations d’unité organisationnelle'
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
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="5a34f-102">Octroi d’autorisations d’unité organisationnelle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a34f-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a34f-103">_**Dernière modification de la rubrique :** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="5a34f-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="5a34f-104">Vous pouvez utiliser l’applet de passe **Grant-CsOuPermission** pour octroyer des autorisations aux objets d’unités d’organisation (UO) spécifiques de sorte que les membres des groupes universels RTC créés par la préparation de la forêt puissent y accéder sans être membres du groupe administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="5a34f-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="5a34f-105">Les autorisations ajoutées à l’unité d’organisation spécifiée sont les mêmes que celles apportées par l’applet de action **Enable-CsAdDomain** à la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="5a34f-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="5a34f-106">Utilisez l’applet de **contrôle test-CsOuPermission** pour vérifier les autorisations que vous avez configurées à l’aide de l’applet de contrôle **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="5a34f-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="5a34f-107">Vous pouvez utiliser l’applet de passe **Revoke-CsOuPermission** pour supprimer les autorisations accordées à l’aide de l’applet de passe **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="5a34f-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="5a34f-108">Pour octroyer des autorisations d’UO</span><span class="sxs-lookup"><span data-stu-id="5a34f-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="5a34f-109">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine dans lequel vous voulez accorder des autorisations d’UO.</span><span class="sxs-lookup"><span data-stu-id="5a34f-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="5a34f-110">Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.</span><span class="sxs-lookup"><span data-stu-id="5a34f-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5a34f-111">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5a34f-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a34f-112">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="5a34f-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5a34f-113">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="5a34f-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="5a34f-114">Pour vérifier les autorisations d’UO</span><span class="sxs-lookup"><span data-stu-id="5a34f-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="5a34f-115">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine dans lequel vous voulez vérifier les autorisations d’UO que vous avez accordées à l’aide de l’applet de contrôle **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="5a34f-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="5a34f-116">Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.</span><span class="sxs-lookup"><span data-stu-id="5a34f-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5a34f-117">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5a34f-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a34f-118">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="5a34f-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5a34f-119">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="5a34f-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="5a34f-120">Pour révoquer les autorisations d’UO</span><span class="sxs-lookup"><span data-stu-id="5a34f-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="5a34f-121">Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine dans lequel vous voulez révoquer les autorisations d’unité d’organisation accordées par l’applet de connexion **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="5a34f-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="5a34f-122">Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.</span><span class="sxs-lookup"><span data-stu-id="5a34f-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5a34f-123">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5a34f-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a34f-124">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="5a34f-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5a34f-125">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="5a34f-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

