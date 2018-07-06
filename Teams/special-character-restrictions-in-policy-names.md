---
title: Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Voir existe avec des caractères spéciaux dans les noms des stratégies et ce que vous pouvez faire pour résoudre des problèmes.
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205077"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="11687-103">Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?</span><span class="sxs-lookup"><span data-stu-id="11687-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="11687-104">**Bien que les caractères spéciaux peuvent être utilisés pour créer des stratégies d’équipes avec PowerShell, vous serez limité dans la gestion de ces stratégies.  Par conséquent, nous vous recommandons vivement de noms de stratégies n’incluent pas de caractères spéciaux.**</span><span class="sxs-lookup"><span data-stu-id="11687-104">**Although special characters can be used for creating Teams policies with PowerShell, you will be limited in managing these policies .  As such, we strongly recommend policy names do not include special characters.**</span></span>

<span data-ttu-id="11687-105">Les noms de stratégie que vous créez à l’aide de PowerShell pour les réunions et de conversation dans les équipes peuvent avoir des caractères spéciaux tels que @, #, $.</span><span class="sxs-lookup"><span data-stu-id="11687-105">Policy names that you create using PowerShell for meetings and chat in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="11687-106">Toutefois, si vous souhaitez modifier la stratégie dans le Microsoft Teams et Skype entreprise centre d’administration, vous ne pourrez.</span><span class="sxs-lookup"><span data-stu-id="11687-106">However, if you are wanting to edit the policy in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="11687-107">Vous devez utiliser Windows PowerShell et l’applet de commande stratégie correcte pour apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="11687-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="11687-108">Si vous disposez d’un objet de stratégie avec des caractères spéciaux et que vous souhaitez supprimer les caractères spéciaux afin de mieux gérer la stratégie dans le Microsoft Teams et Skype entreprise centre d’administration, vous devez utiliser la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="11687-108">If you have a policy object with special characters and you want to remove the special characters in order to better manage the policy in the Microsoft Teams and Skype for Business admin center, you will need to use the below procedure.</span></span> 

<span data-ttu-id="11687-109">Remarque : La procédure articulée ici utilise l’exemple d’une stratégie de messagerie.</span><span class="sxs-lookup"><span data-stu-id="11687-109">Note: The procedure articulated here uses the example of a Messaging policy.</span></span>  <span data-ttu-id="11687-110">Le même processus doit être utilisé pour un autre type de stratégie (par exemple de réunions) en subsituting les applets de commande pertinents.</span><span class="sxs-lookup"><span data-stu-id="11687-110">The same process would be used for another policy type (Meetings for example) by subsituting the relevant cmdlets.</span></span> 

<span data-ttu-id="11687-111">1.) appeler Get-CSMessagingPolicy-identity < ancien_nom_stratégie > et la capture de la sortie de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="11687-111">1.) Call Get-CSMessagingPolicy -identity <old_policy_name> and capture the output of the policy.</span></span>
<span data-ttu-id="11687-112">2.) appeler Set-CSMessagingPolicy-identity < nouveau_nom_stratégie > pour créer une nouvelle stratégie avec la même configuration que la stratégie d’origine, mais sans caractères spéciaux dans le nom.</span><span class="sxs-lookup"><span data-stu-id="11687-112">2.) Call Set-CSMessagingPolicy -identity <new_policy_name> to create a new policy with the same configuration as the original policy but without any special characters in the name.</span></span>
<span data-ttu-id="11687-113">3.) appel Delete-CSMessagingPolicy-identity < ancien_nom_stratégie > pour supprimer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="11687-113">3.) Call Delete-CSMessagingPolicy -identity <old_policy_name> to delete the policy.</span></span>  <span data-ttu-id="11687-114">Si cette commande réussit, vous avez terminé et vous pouvez commencer à affecter des utilisateurs à la nouvelle stratégie à l’aide de PowerShell ou les Microsoft Teams et Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="11687-114">If this command succeeds, you're done and can begin to assign users to the new policy using either PowerShell or the Microsoft Teams and Skype for Business admin center.</span></span>
<span data-ttu-id="11687-115">4.) si la commande ci-dessus n’aboutit pas, il est, car l’ancienne stratégie a été affecté à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="11687-115">4.) If the above command does not succeed, it is because the old policy has been assigned to a user.</span></span>  <span data-ttu-id="11687-116">Exécuter annuler l’affectation d’applet de commande pour annuler l’affectation de la stratégie de l’utilisateur, affecter la nouvelle stratégie, puis réexécutez dwlete.</span><span class="sxs-lookup"><span data-stu-id="11687-116">Run unassign cmdlet to unassign the policy from user, assign new policy, then run dwlete again.</span></span>


