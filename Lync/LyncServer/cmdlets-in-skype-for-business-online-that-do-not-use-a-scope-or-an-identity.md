---
title: Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ade4dee78fff151530e0d76279fdbfaeade720b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755314"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="28cfa-102">Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité</span><span class="sxs-lookup"><span data-stu-id="28cfa-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="28cfa-103">Les applets de commande utilisées lors de la modification des listes autorisées et des listes bloquées (listes qui déterminent les organisations externes avec lesquelles vos utilisateurs sont autorisés à communiquer) n’utilisent ni une étendue ni une identité.</span><span class="sxs-lookup"><span data-stu-id="28cfa-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="28cfa-104">En fait, la cmdlet **New-CsEdgeAllowAllKnownDomains** n’a aucun paramètre.</span><span class="sxs-lookup"><span data-stu-id="28cfa-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="28cfa-105">Les applets de commande qui n’utilisent ni une étendue ni une identité sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="28cfa-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="28cfa-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="28cfa-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="28cfa-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="28cfa-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="28cfa-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="28cfa-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="28cfa-109">Notez que, avec la cmdlet **New-CsEdgeAllowList** et la cmdlet **New-CsEdgeDomainPattern** , vous devez inclure le paramètre domain.</span><span class="sxs-lookup"><span data-stu-id="28cfa-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="28cfa-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="28cfa-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="28cfa-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28cfa-111">See Also</span></span>


[<span data-ttu-id="28cfa-112">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="28cfa-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="28cfa-113">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="28cfa-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

