---
title: Cmdlets dans Skype entreprise Online utilisant le paramètre locataire
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3b09e6f419c7425332427ccf4a4ff664b9e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838089"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="e755e-102">Cmdlets dans Skype entreprise Online utilisant le paramètre locataire</span><span class="sxs-lookup"><span data-stu-id="e755e-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="e755e-103">Lorsque vous modifiez les paramètres de votre fournisseur public, vous devez toujours fournir une identité de client; C’est vrai, même si vous n’avez qu’un seul client.</span><span class="sxs-lookup"><span data-stu-id="e755e-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="e755e-104">Par exemple, cette commande définit Windows Live en tant que seul fournisseur public auquel les utilisateurs sont autorisés à communiquer:</span><span class="sxs-lookup"><span data-stu-id="e755e-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="e755e-105">Heureusement, vous n’avez pas besoin de taper l’ID de locataire (par exemple, bf19b7db-6960-41E5-A139-2aa373474354) chaque fois que vous exécutez l’une de ces applets de connexion.</span><span class="sxs-lookup"><span data-stu-id="e755e-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="e755e-106">Au lieu de cela, vous pouvez récupérer l’ID de locataire en exécutant l’applet de demande [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , en stockant l’ID de locataire dans une variable, puis en utilisant cette variable lorsque vous appelez l’une des autres cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e755e-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="e755e-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e755e-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="e755e-108">Vous pouvez également effectuer cette opération dans une seule commande en récupérant l’ID de locataire, puis en canalisant cette valeur vers l’applet de commande Set-CsTenantPublicProvider:</span><span class="sxs-lookup"><span data-stu-id="e755e-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="e755e-109">Vous n’avez pas besoin de spécifier l’ID de locataire lorsque vous appelez l’applet **de action Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="e755e-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="e755e-110">Cette commande renvoie des informations sur votre client:</span><span class="sxs-lookup"><span data-stu-id="e755e-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="e755e-111">Les applets de commande suivantes acceptent une identité de client.</span><span class="sxs-lookup"><span data-stu-id="e755e-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="e755e-112">Néanmoins, dans ces cas-là, le paramètre est facultatif et n’a pas besoin d’être entré lorsque vous appelez l’applet de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e755e-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="e755e-113">Au lieu de cela, Windows PowerShell entrera efficacement l’identité du client en fonction du client Skype entreprise Online auquel vous êtes actuellement connecté:</span><span class="sxs-lookup"><span data-stu-id="e755e-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="e755e-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e755e-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e755e-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e755e-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e755e-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e755e-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e755e-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e755e-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e755e-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e755e-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e755e-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e755e-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="e755e-120">Par exemple, vous pouvez appeler l’applet de commande **Get-CsTenantFederationConfiguration** à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="e755e-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="e755e-121">Même si ce n’est pas obligatoire, vous pouvez inclure le paramètre locataire lors de l’appel de Get-CsTenantFederationConfiguration:</span><span class="sxs-lookup"><span data-stu-id="e755e-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="e755e-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e755e-122">See Also</span></span>


[<span data-ttu-id="e755e-123">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e755e-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e755e-124">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e755e-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

