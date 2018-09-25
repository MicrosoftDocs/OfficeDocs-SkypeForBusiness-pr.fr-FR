---
title: Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
- skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Teams_ITAdmin_Help
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Voir existe avec des caractères spéciaux dans les noms des stratégies et ce que vous pouvez faire pour résoudre des problèmes.
ms.openlocfilehash: e1d46f70b42b96b2f3811c97d0110946fd013cd7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017502"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="e763e-103">Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?</span><span class="sxs-lookup"><span data-stu-id="e763e-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="e763e-104">**Vous ne pouvez pas créer ou modifier des stratégies (pour la messagerie, réunions, etc.) qui ont un caractère spécial dans le nom des Skype Teams Microsoft Business centre d’administration.**</span><span class="sxs-lookup"><span data-stu-id="e763e-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams and Skype for Business Admin Center.**</span></span> 

<span data-ttu-id="e763e-105">Si un nom de stratégie contient des caractères spéciaux, vous serez limité dans la gestion de ces stratégies dans le Microsoft Teams et Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="e763e-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams and Skype for Business Admin Center.</span></span> <span data-ttu-id="e763e-106">**Par conséquent, il est fortement recommandé que les noms de stratégie ne pas inclure des caractères spéciaux**.</span><span class="sxs-lookup"><span data-stu-id="e763e-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="e763e-107">Les noms de stratégie qui ont été créés à l’aide de PowerShell pour les réunions et messagerie dans les équipes peuvent avoir des caractères spéciaux tels que @, #, $.</span><span class="sxs-lookup"><span data-stu-id="e763e-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="e763e-108">Toutefois, si vous souhaitez apporter des modifications à la stratégie dans le Microsoft Teams et Skype entreprise centre d’administration, vous ne pourrez.</span><span class="sxs-lookup"><span data-stu-id="e763e-108">However, if you are wanting to make changes to the policy in the Microsoft Teams and Skype for Business Admin Center,you won't be able to.</span></span> 

<span data-ttu-id="e763e-109">Si vous disposez d’une stratégie avec des caractères spéciaux, vous devez soit modifier la stratégie à l’aide de Windows PowerShell (toujours) ou créer une nouvelle stratégie dans le Microsoft Teams et Skype entreprise centre d’administration de la même manière que l’ancienne stratégie et l’affecter à la même grou p d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e763e-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams and Skype for Business Admin Center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="e763e-110">Pour supprimer les caractères spéciaux</span><span class="sxs-lookup"><span data-stu-id="e763e-110">To remove special characters</span></span>



<span data-ttu-id="e763e-111">**Étape 1 : établir une connexion à distance PowerShell.** 
 [Configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) si vous n’avez pas encore.</span><span class="sxs-lookup"><span data-stu-id="e763e-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="e763e-112">**Étape 2 : obtenir les paramètres de l’ancienne stratégie et capturer la sortie.**</span><span class="sxs-lookup"><span data-stu-id="e763e-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="e763e-113">Cet exemple est destiné à une stratégie de [messagerie](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e763e-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="e763e-114">Les étapes serait identique pour d’autres types de stratégie, mais vous devez utiliser l’applet de commande correct.</span><span class="sxs-lookup"><span data-stu-id="e763e-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="e763e-115">**Étape 3 : créer une nouvelle stratégie.**</span><span class="sxs-lookup"><span data-stu-id="e763e-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="e763e-116">Vous pouvez créer la nouvelle stratégie avec le même paramètre à l’aide de la Teams Microsoft et Skype pour le centre d’administration Business ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e763e-116">You can either create the new policy with the same setting using the Microsoft Teams and Skype for Business Admin Center or PowerShell.</span></span>

<span data-ttu-id="e763e-117">Exécuter cette crée une nouvelle stratégie pour vous, mais vous devez ajouter les paramètres corrects en consultant la rubrique [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) et puis de l’exécuter :</span><span class="sxs-lookup"><span data-stu-id="e763e-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="e763e-118">**Étape 4 : attribuer la stratégie.**</span><span class="sxs-lookup"><span data-stu-id="e763e-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="e763e-119">Voir [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) pour plus d’informations sur cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="e763e-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="e763e-120">**Étape 5 - supprimer l’ancienne stratégie.**</span><span class="sxs-lookup"><span data-stu-id="e763e-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="e763e-121">Cette opération supprime l’ancienne stratégie avec des caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="e763e-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="e763e-122">[Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) pour plus d’informations sur cette applet de commande, voir.</span><span class="sxs-lookup"><span data-stu-id="e763e-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="e763e-123">Si cette commande réussit, vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="e763e-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="e763e-124">Si la commande ci-dessus retourne une erreur, il est car l’ancienne stratégie est affectée aux utilisateurs afin que vous devez exécuter pour supprimer tous les utilisateurs affectés de la stratégie :</span><span class="sxs-lookup"><span data-stu-id="e763e-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e763e-125">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="e763e-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="e763e-p105">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e763e-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e763e-129">Pourquoi vous devez utiliser Office 365 PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="e763e-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e763e-130">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e763e-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e763e-131">Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="e763e-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="e763e-132">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e763e-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e763e-133">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e763e-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="e763e-134">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e763e-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e763e-135">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e763e-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e763e-136">Le module Windows PowerShell pour Skype pour Business Online permet de vous permet de créer une session Windows PowerShell à distance qui se connecte à Skype pour Business Online et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e763e-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="e763e-137">Ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé depuis le Center Download Microsoft à [le Module Windows PowerShell pour Skype pour Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="e763e-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
### <a name="related-topics"></a><span data-ttu-id="e763e-138">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e763e-138">Related topics</span></span>
