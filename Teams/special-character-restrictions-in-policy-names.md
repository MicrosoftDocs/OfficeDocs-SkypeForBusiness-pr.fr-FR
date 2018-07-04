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
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192163"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="007b4-103">Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?</span><span class="sxs-lookup"><span data-stu-id="007b4-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="007b4-104">**Bien que vous pouvez utiliser des caractères spéciaux dans les noms de stratégies que vous avez créé dans les équipes, il est vivement recommandé que vous n’avez pas.**</span><span class="sxs-lookup"><span data-stu-id="007b4-104">**Although you can use special characters in the names of policies you created in Teams, we strongly recommend that you don't.**</span></span>

<span data-ttu-id="007b4-105">Les noms de stratégie que vous créez pour les réunions, les conversations et prescense, et autres éléments dans les équipes peuvent avoir des caractères spéciaux tels que @, #, $.</span><span class="sxs-lookup"><span data-stu-id="007b4-105">Policy names that you create for meetings, chat and prescense, and other things in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="007b4-106">Toutefois, si vous souhaitez apporter des modifications sur le nom des Skype Teams Microsoft Business centre d’administration, vous ne pourrez.</span><span class="sxs-lookup"><span data-stu-id="007b4-106">However, if you are wanting to make changes to the name in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="007b4-107">Vous devez utiliser Windows PowerShell et l’applet de commande stratégie correcte pour apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="007b4-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="007b4-108">Par exemple, si vous disposez d’une stratégie de réunion avec des caractères spéciaux et que vous souhaitez modifier le nom ou supprimer les caractères spéciaux à partir du nom, vous devez utiliser l’applet de commande Set-CsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="007b4-108">For example, if you have a meeting policy with special characters and you want to change the name or remove the special characters from the name, you will need to use the Set-CsMeetingPolicy cmdlet.</span></span> 

<span data-ttu-id="007b4-109">Voici une liste des applets de commande stratégie que vous devrez peut-être effectuer cette opération :</span><span class="sxs-lookup"><span data-stu-id="007b4-109">Here is a list of the policy cmdlets that you may need to do this:</span></span>
1. <span data-ttu-id="007b4-110">Set-CsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="007b4-110">Set-CsMeetingPolicy</span></span>
2. <span data-ttu-id="007b4-111">Set-CsAppPolicy</span><span class="sxs-lookup"><span data-stu-id="007b4-111">Set-CsAppPolicy</span></span>
3. <span data-ttu-id="007b4-112">Set-\*</span><span class="sxs-lookup"><span data-stu-id="007b4-112">Set-\*</span></span>


