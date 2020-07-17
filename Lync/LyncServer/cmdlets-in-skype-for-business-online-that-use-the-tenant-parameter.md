---
title: Applets de commande dans Skype entreprise Online qui utilisent le paramètre client
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 352a33fcff5db306b62535c28fb4a2b2dd766bea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755040"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="953c0-102">Applets de commande dans Skype entreprise Online qui utilisent le paramètre client</span><span class="sxs-lookup"><span data-stu-id="953c0-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="953c0-103">Lors de la modification de vos paramètres de fournisseur public, vous devez toujours fournir une identité de client ; Cela est vrai même si vous n’avez qu’un seul client.</span><span class="sxs-lookup"><span data-stu-id="953c0-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="953c0-104">Par exemple, cette commande définit Windows Live en tant que seul fournisseur public avec lequel les utilisateurs sont autorisés à communiquer :</span><span class="sxs-lookup"><span data-stu-id="953c0-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="953c0-105">Heureusement, il n’est pas nécessaire de taper l’ID de client (par exemple, bf19b7db-6960-41E5-A139-2aa373474354) chaque fois que vous exécutez l’une de ces applets de commande.</span><span class="sxs-lookup"><span data-stu-id="953c0-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="953c0-106">Au lieu de cela, vous pouvez récupérer l’ID de client en exécutant la cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , en stockant l’ID de client dans une variable, puis en utilisant cette variable lorsque vous appelez l’une des autres cmdlets.</span><span class="sxs-lookup"><span data-stu-id="953c0-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="953c0-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="953c0-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="953c0-108">Vous pouvez également effectuer cette opération dans une seule commande en récupérant l’ID de client, puis en canalisant cette valeur vers la cmdlet Set-CsTenantPublicProvider :</span><span class="sxs-lookup"><span data-stu-id="953c0-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="953c0-109">Vous n’avez pas besoin de spécifier l’ID de client lors de l’appel de la cmdlet **Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="953c0-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="953c0-110">Cette commande retourne des informations sur votre client :</span><span class="sxs-lookup"><span data-stu-id="953c0-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="953c0-111">Les applets de commande suivantes acceptent une identité de client.</span><span class="sxs-lookup"><span data-stu-id="953c0-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="953c0-112">Toutefois, dans ce cas, le paramètre est facultatif et n’a pas besoin d’être entré lors de l’appel de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="953c0-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="953c0-113">Au lieu de cela, Windows PowerShell entrera l’identité du client à votre place en fonction du client Skype entreprise Online auquel vous êtes actuellement connecté :</span><span class="sxs-lookup"><span data-stu-id="953c0-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="953c0-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="953c0-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="953c0-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="953c0-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="953c0-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="953c0-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="953c0-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="953c0-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="953c0-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="953c0-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="953c0-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="953c0-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="953c0-120">Par exemple, la cmdlet **Get-CsTenantFederationConfiguration** peut être appelée à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="953c0-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="953c0-121">Bien que cela ne soit pas obligatoire, vous pouvez inclure le paramètre client lors de l’appel de Get-CsTenantFederationConfiguration :</span><span class="sxs-lookup"><span data-stu-id="953c0-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="953c0-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="953c0-122">See Also</span></span>


[<span data-ttu-id="953c0-123">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="953c0-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="953c0-124">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="953c0-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

