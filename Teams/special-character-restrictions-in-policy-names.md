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
description: Découvrez les problèmes liés aux caractères spéciaux dans les noms de stratégies et ce que vous pouvez faire pour résoudre ce problème.
ms.openlocfilehash: 7358bd989b793e988f0a3dacdded275b5232c8cc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691510"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="e376f-103">Quelles sont les restrictions d’un caractère spécial dans les stratégies Teams ?</span><span class="sxs-lookup"><span data-stu-id="e376f-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="e376f-104">**Vous ne pouvez pas créer ou modifier des stratégies (pour la messagerie, les réunions, etc.) dont le nom contient un caractère spécial dans le centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="e376f-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="e376f-105">Si le nom d’une stratégie contient des caractères spéciaux, vous ne serez plus limité à la gestion de ces stratégies dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e376f-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e376f-106">Par **exemple, nous vous recommandons vivement de ne pas inclure de caractères spéciaux dans les noms de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="e376f-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="e376f-107">Les noms de stratégie qui ont été créés à l’aide de PowerShell pour les réunions et la messagerie dans teams peuvent avoir des caractères spéciaux tels que @, #, $.</span><span class="sxs-lookup"><span data-stu-id="e376f-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="e376f-108">Toutefois, si vous souhaitez apporter des modifications à la stratégie dans le centre d’administration Microsoft Teams, vous ne serez pas en mesure de le faire.</span><span class="sxs-lookup"><span data-stu-id="e376f-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="e376f-109">Si vous disposez d’une stratégie contenant des caractères spéciaux, vous devez modifier la stratégie à l’aide de Windows PowerShell (Forever) ou créer une nouvelle stratégie dans le centre d’administration Microsoft teams avec les mêmes paramètres que l’ancienne stratégie et l’affecter au même groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e376f-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="e376f-110">Pour supprimer des caractères spéciaux</span><span class="sxs-lookup"><span data-stu-id="e376f-110">To remove special characters</span></span>

<span data-ttu-id="e376f-111">**Étape 1 : créer une connexion à distance avec PowerShell.** 
 Si ce n’est déjà fait, [configurez votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) .</span><span class="sxs-lookup"><span data-stu-id="e376f-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="e376f-112">**Étape 2 : obtenir les paramètres de l’ancienne stratégie et capturer la sortie.**</span><span class="sxs-lookup"><span data-stu-id="e376f-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="e376f-113">Cet exemple s’utilise pour une stratégie de [messagerie](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e376f-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="e376f-114">Les étapes sont identiques pour les autres types de stratégies, mais vous devez utiliser l’applet de cmdlet correcte.</span><span class="sxs-lookup"><span data-stu-id="e376f-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="e376f-115">**Étape 3 : créer une nouvelle stratégie.**</span><span class="sxs-lookup"><span data-stu-id="e376f-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="e376f-116">Vous pouvez créer une nouvelle stratégie avec le même paramètre à l’aide du centre d’administration Microsoft teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e376f-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="e376f-117">L’exécution de cette opération entraîne la création d’une stratégie pour vous, mais vous devrez ajouter les paramètres appropriés en vérifiant [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) , puis en exécutant celle-ci :</span><span class="sxs-lookup"><span data-stu-id="e376f-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="e376f-118">**Étape 4 : affecter la stratégie.**</span><span class="sxs-lookup"><span data-stu-id="e376f-118">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="e376f-119">Pour plus d’informations sur cette cmdlet, voir [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e376f-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="e376f-120">**Étape 5 : supprimer l’ancienne stratégie.**</span><span class="sxs-lookup"><span data-stu-id="e376f-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="e376f-121">Cette opération a pour effet de supprimer l’ancienne stratégie qui contient les caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="e376f-121">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="e376f-122">Pour plus d’informations sur cette cmdlet, voir [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e376f-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="e376f-123">Si cette commande aboutit, vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="e376f-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="e376f-124">Si la commande ci-dessus renvoie une erreur, c’est parce que l’ancienne stratégie est affectée aux utilisateurs et que vous devez les exécuter pour supprimer tous les utilisateurs assignés de la stratégie :</span><span class="sxs-lookup"><span data-stu-id="e376f-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e376f-125">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="e376f-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="e376f-126">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="e376f-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e376f-127">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="e376f-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e376f-128">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="e376f-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e376f-129">Pourquoi avez-vous besoin d’utiliser Office 365 PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="e376f-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e376f-130">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e376f-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e376f-131">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité qui consiste à utiliser le centre d’administration Microsoft 365, par exemple, lorsque vous modifiez les paramètres de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="e376f-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="e376f-132">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e376f-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e376f-133">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e376f-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="e376f-134">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e376f-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e376f-135">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e376f-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e376f-136">Le module Windows PowerShell pour Skype entreprise Online vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise Online et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e376f-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="e376f-137">Ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé à partir du centre de téléchargement Microsoft dans le [module Windows PowerShell pour Skype entreprise online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="e376f-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

