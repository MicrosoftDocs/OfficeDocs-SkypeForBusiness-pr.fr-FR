---
title: Cmdlets dans Skype entreprise Online qui n’utilisent pas d’étendue ou d’identité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3dfc2ee8cd812b597f363934475d1996f2e42a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727594"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="0f0bd-102">Cmdlets dans Skype entreprise Online qui n’utilisent pas d’étendue ou d’identité</span><span class="sxs-lookup"><span data-stu-id="0f0bd-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="0f0bd-103">Les applets de passe utilisés lors de la modification des listes autorisées et des listes bloquées (listes qui déterminent les organisations externes avec lesquelles les utilisateurs sont autorisés à communiquer) n’utilisent pas d’étendue ou d’identité.</span><span class="sxs-lookup"><span data-stu-id="0f0bd-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="0f0bd-104">En fait, l’applet **de nouvelle applet de CsEdgeAllowAllKnownDomains** n’a aucun paramètre.</span><span class="sxs-lookup"><span data-stu-id="0f0bd-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="0f0bd-105">Les applets de applet qui n’utilisent pas d’étendue ou d’identité sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="0f0bd-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="0f0bd-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="0f0bd-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="0f0bd-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="0f0bd-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="0f0bd-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="0f0bd-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="0f0bd-109">Notez que, avec l’applet **de nouvelle cmdlet New-CsEdgeAllowList** et la cmdlet **New-CsEdgeDomainPattern** , vous devez inclure le paramètre domain.</span><span class="sxs-lookup"><span data-stu-id="0f0bd-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="0f0bd-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0f0bd-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="0f0bd-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f0bd-111">See Also</span></span>


[<span data-ttu-id="0f0bd-112">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0f0bd-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="0f0bd-113">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="0f0bd-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

