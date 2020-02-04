---
title: Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur et une étendue de balises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727564"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="44239-102">Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur et une étendue de balises</span><span class="sxs-lookup"><span data-stu-id="44239-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="44239-103">Les applets de demande d' **autorisation-CS** (utilisées pour attribuer des stratégies aux utilisateurs) nécessitent deux identificateurs : une identité d’utilisateur (le paramètre Identity) et l’identité d’une stratégie par utilisateur (paramètre PolicyName).</span><span class="sxs-lookup"><span data-stu-id="44239-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="44239-104">Par exemple, pour affecter la stratégie vocale, RedmondVoicePolicy, à l’utilisateur Ken Myer, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="44239-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="44239-105">Il existe deux éléments à garder à l’esprit lors de l’attribution de stratégies aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="44239-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="44239-106">Tout d’abord, seules les stratégies par utilisateur peuvent être affectées.</span><span class="sxs-lookup"><span data-stu-id="44239-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="44239-107">Vous ne pouvez pas attribuer de stratégie globale à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44239-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="44239-108">Par exemple, la commande suivante échoue :</span><span class="sxs-lookup"><span data-stu-id="44239-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="44239-109">Cette commande échoue, car il n’est pas nécessaire d’affecter la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="44239-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="44239-110">Si vous souhaitez gérer un utilisateur à l’aide de la stratégie globale, veillez à ne pas affecter cet utilisateur à une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44239-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="44239-111">Si aucune stratégie par utilisateur n’a été attribuée à un utilisateur, l’utilisateur est automatiquement géré à l’aide de la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="44239-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="44239-112">Que se passe-t-il si une stratégie par utilisateur a déjà été affectée à l’utilisateur et que vous souhaitez annuler l’affectation de cette stratégie et l’utilisateur est-il géré à la place par la politique globale ?</span><span class="sxs-lookup"><span data-stu-id="44239-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="44239-113">Dans ce cas, vous devez commencer par utiliser la syntaxe suivante, qui annule l’affectation d’une stratégie par utilisateur en attribuant une stratégie null à l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="44239-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="44239-114">Grant-CsVoicePolicy-Identity "Ken Myer"-PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="44239-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="44239-115">Deuxièmement, gardez à l’esprit que les stratégies par utilisateur sont créées à l’étendue de la balise.</span><span class="sxs-lookup"><span data-stu-id="44239-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="44239-116">Toutefois, vous pouvez omettre le **préfixe** d’indicateur lorsque vous spécifiez le nom d’une stratégie.</span><span class="sxs-lookup"><span data-stu-id="44239-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="44239-117">Ces deux commandes sont identiques :</span><span class="sxs-lookup"><span data-stu-id="44239-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="44239-118">Si vous souhaitez renvoyer les identités pour toutes les stratégies par utilisateur (ou, au moins, toutes les stratégies par utilisateur de type spécifié, par exemple les stratégies vocales), utilisez une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="44239-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="44239-119">Les applets de commande suivantes utilisent à la fois une identité d’utilisateur et l’étendue de la balise :</span><span class="sxs-lookup"><span data-stu-id="44239-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="44239-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="44239-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="44239-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="44239-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="44239-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="44239-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="44239-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="44239-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="44239-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="44239-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="44239-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="44239-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="44239-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="44239-126">See Also</span></span>


[<span data-ttu-id="44239-127">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="44239-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="44239-128">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="44239-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

