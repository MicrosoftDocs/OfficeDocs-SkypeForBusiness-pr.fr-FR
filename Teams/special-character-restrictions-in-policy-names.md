---
title: Restrictions de caractère spécial dans les stratégies Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Découvrez les problèmes qui surentent les caractères spéciaux dans les noms des stratégies et ce que vous pouvez faire pour le résoudre.
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116982"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="1063a-103">Quelles sont les restrictions d’un caractère spécial dans les stratégies Teams ?</span><span class="sxs-lookup"><span data-stu-id="1063a-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="1063a-104">Vous ne pouvez pas créer ou modifier des stratégies (pour la messagerie, les réunions, etc.) qui ont un caractère spécial dans le nom dans le Centre **d’administration Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="1063a-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="1063a-105">Si un nom de stratégie contient des caractères spéciaux, la gestion de ces stratégies dans le Centre d’administration Microsoft Teams sera limitée.</span><span class="sxs-lookup"><span data-stu-id="1063a-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1063a-106">**C’est pourquoi nous recommandons vivement que les noms de stratégie n’incluent pas de caractères spéciaux.**</span><span class="sxs-lookup"><span data-stu-id="1063a-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="1063a-107">Les noms de stratégie qui ont été créés à l’aide de PowerShell pour les réunions et la messagerie dans Teams peuvent avoir des caractères spéciaux tels que @,#,$.</span><span class="sxs-lookup"><span data-stu-id="1063a-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="1063a-108">Toutefois, si vous souhaitez apporter des modifications à la stratégie dans le Centre d’administration Microsoft Teams, vous ne pourrez pas.</span><span class="sxs-lookup"><span data-stu-id="1063a-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="1063a-109">Si vous avez une stratégie avec des caractères spéciaux, vous devrez soit la modifier à l’aide de Windows PowerShell (indéfiniment) soit créer une stratégie dans le Centre d’administration Microsoft Teams avec les mêmes paramètres que l’ancienne stratégie et l’affecter au même groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1063a-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="1063a-110">Pour supprimer les caractères spéciaux</span><span class="sxs-lookup"><span data-stu-id="1063a-110">To remove special characters</span></span>

<span data-ttu-id="1063a-111">**Étape 1 : établir une connexion à distance avec PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="1063a-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="1063a-112">Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.</span><span class="sxs-lookup"><span data-stu-id="1063a-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="1063a-113">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="1063a-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


<span data-ttu-id="1063a-114">**Étape 2 : obtenez les paramètres de l’ancienne stratégie et capturez le résultat.**</span><span class="sxs-lookup"><span data-stu-id="1063a-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="1063a-115">Cet exemple s’agit [d’une stratégie de](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) messagerie.</span><span class="sxs-lookup"><span data-stu-id="1063a-115">This example is for a [Messaging](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="1063a-116">Les étapes seraient les mêmes pour d’autres types de stratégie, mais vous devez utiliser l’cmdlet correcte.</span><span class="sxs-lookup"><span data-stu-id="1063a-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="1063a-117">**Étape 3 : créer une stratégie.**</span><span class="sxs-lookup"><span data-stu-id="1063a-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="1063a-118">Vous pouvez créer la nouvelle stratégie avec le même paramètre à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1063a-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="1063a-119">L’exécution de cette stratégie crée une stratégie pour vous, mais vous devez ajouter les paramètres corrects en voyant [Set-CsTeamsMesspolicy,](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) puis en l’exécutant :</span><span class="sxs-lookup"><span data-stu-id="1063a-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="1063a-120">**Étape 4 : affecter la stratégie.**</span><span class="sxs-lookup"><span data-stu-id="1063a-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="1063a-121">Pour plus d’informations sur cette cmdlet, voir [Grant-CsTeamsMess paysPolicy.](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1063a-121">See, [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="1063a-122">**Étape 5 : supprimer l’ancienne stratégie.**</span><span class="sxs-lookup"><span data-stu-id="1063a-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="1063a-123">L’ancienne stratégie avec les caractères spéciaux est alors supprimé.</span><span class="sxs-lookup"><span data-stu-id="1063a-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="1063a-124">Pour plus d’informations sur cette cmdlet, voir [Remove-CsTeamsMesspolicy.](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1063a-124">See, [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="1063a-125">Si cette commande réussit, vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="1063a-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="1063a-126">Si la commande ci-dessus renvoie une erreur, l’ancienne stratégie étant affectée aux utilisateurs, vous devez exécuter cette stratégie pour supprimer tous les utilisateurs affectés de la stratégie :</span><span class="sxs-lookup"><span data-stu-id="1063a-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1063a-127">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="1063a-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="1063a-128">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="1063a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1063a-129">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="1063a-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1063a-130">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="1063a-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1063a-131">Pourquoi avez-vous besoin d’utiliser PowerShell Office 365 ?</span><span class="sxs-lookup"><span data-stu-id="1063a-131">Why you need to use Office 365 PowerShell?</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="1063a-132">[Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1063a-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="1063a-133">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez les paramètres de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="1063a-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="1063a-134">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1063a-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1063a-135">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1063a-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [<span data-ttu-id="1063a-136">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1063a-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="1063a-137">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1063a-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="1063a-138">Le module Windows PowerShell de Skype Entreprise Online vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1063a-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="1063a-139">Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé à partir du Centre de téléchargement Microsoft dans [le module Windows PowerShell de Skype Entreprise Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="1063a-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
