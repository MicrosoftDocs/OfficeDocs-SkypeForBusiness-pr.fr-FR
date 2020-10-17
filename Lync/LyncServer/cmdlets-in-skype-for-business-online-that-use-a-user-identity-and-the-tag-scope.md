---
title: Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur et l’étendue de la balise
description: Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur et l’étendue de la balise.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 3e2ddbcc9c90096cea5fad4cb680f4ea1797ce48
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545610"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="4106a-103">Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur et l’étendue de la balise</span><span class="sxs-lookup"><span data-stu-id="4106a-103">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="4106a-104">Les applets **de commande Grant-CS** (utilisées pour affecter des stratégies aux utilisateurs) nécessitent deux identificateurs : une identité d’utilisateur (le paramètre Identity) et l’identité d’une stratégie par utilisateur (le paramètre PolicyName).</span><span class="sxs-lookup"><span data-stu-id="4106a-104">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="4106a-105">Par exemple, pour affecter la stratégie de voix, RedmondVoicePolicy, à l’utilisateur Ken Myer, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4106a-105">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="4106a-106">Il y a deux éléments à garder à l’esprit lors de l’affectation de stratégies aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4106a-106">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="4106a-107">Tout d’abord, seules les stratégies par utilisateur peuvent être affectées.</span><span class="sxs-lookup"><span data-stu-id="4106a-107">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="4106a-108">Vous ne pouvez pas attribuer la stratégie globale à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4106a-108">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="4106a-109">Par exemple, la commande suivante échoue :</span><span class="sxs-lookup"><span data-stu-id="4106a-109">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="4106a-110">Cette commande échoue, car il n’est pas nécessaire d’attribuer la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="4106a-110">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="4106a-111">Si vous souhaitez gérer un utilisateur à l’aide de la stratégie globale, assurez-vous que vous n’affectez pas cette stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4106a-111">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="4106a-112">Si aucune stratégie par utilisateur n’a été affectée à un utilisateur, l’utilisateur est automatiquement géré à l’aide de la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="4106a-112">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="4106a-113">Que se passe-t-il si l’utilisateur a été précédemment affecté à une stratégie par utilisateur et que vous souhaitez annuler l’affectation de cette stratégie et faire en sorte que l’utilisateur soit géré par la stratégie globale à la place ?</span><span class="sxs-lookup"><span data-stu-id="4106a-113">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="4106a-114">Dans ce cas, vous utiliserez d’abord la syntaxe suivante, qui annule l’affectation d’une stratégie par utilisateur en accordant à cet utilisateur une stratégie NULL :</span><span class="sxs-lookup"><span data-stu-id="4106a-114">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="4106a-115">Grant-CsVoicePolicy – Identity "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="4106a-115">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="4106a-116">Deuxièmement, gardez à l’esprit que les stratégies par utilisateur sont créées au niveau de l’étendue de la balise.</span><span class="sxs-lookup"><span data-stu-id="4106a-116">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="4106a-117">Toutefois, vous pouvez omettre le **préfixe** de balise lors de la spécification d’un nom de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4106a-117">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="4106a-118">Ces deux commandes sont identiques :</span><span class="sxs-lookup"><span data-stu-id="4106a-118">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="4106a-119">Si vous souhaitez renvoyer les identités de toutes vos stratégies par utilisateur (ou au moins, toutes les stratégies par utilisateur de type spécifié, telles que les stratégies de voix), utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="4106a-119">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="4106a-120">Les applets de commande suivantes utilisent à la fois l’identité d’un utilisateur et l’étendue de la balise :</span><span class="sxs-lookup"><span data-stu-id="4106a-120">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="4106a-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4106a-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4106a-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4106a-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4106a-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4106a-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4106a-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4106a-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4106a-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4106a-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4106a-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4106a-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="4106a-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4106a-127">See Also</span></span>


[<span data-ttu-id="4106a-128">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4106a-128">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="4106a-129">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4106a-129">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

