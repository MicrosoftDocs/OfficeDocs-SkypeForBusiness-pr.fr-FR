---
title: Basculement entre les interfaces utilisateur des clients Skype Entreprise et Lync
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 9edbc3642a0b8459cc658d32d135eb21e0b3edf8
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="5732f-103">Basculement entre les interfaces utilisateur des clients Skype Entreprise et Lync</span><span class="sxs-lookup"><span data-stu-id="5732f-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="5732f-104">Dans les organisations utilisant Skype Entreprise Online, vous pouvez utiliser une session PowerShell distante dans Office 365 pour permettre aux utilisateurs de Skype Entreprise d'utiliser le client Skype Entreprise ou l'interface utilisateur du client Skype Entreprise (Lync).</span><span class="sxs-lookup"><span data-stu-id="5732f-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="5732f-105">Par défaut, l'interface utilisateur du client Skype Entreprise est utilisée.</span><span class="sxs-lookup"><span data-stu-id="5732f-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="5732f-106">Si vous préférez utiliser l’expérience du client Lync, vous pouvez gérer le comportement du client premier lancement pour afficher l’interface utilisateur de Lync en suivant les étapes décrites plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5732f-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5732f-p102">L'expérience client Lync 2013 n'est pas une option pour les versions client de Skype Entreprise 2016. Avant de tenter de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez la version du client pour vous assurer qu'elle ne commence pas par le numéro 16. Par exemple : 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="5732f-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="5732f-109">Si vous souhaitez changer facilement d'interface utilisateur sans procéder manuellement, reportez-vous au [Centre de téléchargement Microsoft ](https://go.microsoft.com/fwlink/?LinkId=532431) pour obtenir un script PowerShell afin de simplifier cette procédure.</span><span class="sxs-lookup"><span data-stu-id="5732f-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center ](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="5732f-110">Changement d'interface utilisateur de Skype Entreprise pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="5732f-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="5732f-p103">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell distante, qui se connecte à Skype Entreprise Online. Ce module pris en charge uniquement sur les ordinateurs 64 bits peut être téléchargé à partir du Centre de téléchargement Microsoft : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Pour plus d'informations, reportez-vous à l'article [Configuration de votre ordinateur pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=534539).</span><span class="sxs-lookup"><span data-stu-id="5732f-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5732f-p104">Le paramètre de stratégie  _Global_ pour le changement d'interface utilisateur ne s'applique pas à un utilisateur pour lequel une stratégie personnalisée est déjà appliquée. Pour pouvoir modifier l'interface utilisateur, vous devez exécuter les opérations suivantes pour chaque utilisateur qui possède une stratégie personnalisée :</span><span class="sxs-lookup"><span data-stu-id="5732f-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="5732f-116">La stratégie  _ClientPolicyEnableSkypeUI_ remplacera le paramètre de stratégie personnalisée en vigueur pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5732f-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="5732f-117">Pour permettre à tous les utilisateurs de votre organisation d'utiliser le client Skype Entreprise, ouvrez la session PowerShell distante et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="5732f-118">Si vous définissez la stratégie actuelle, vous verrez :</span><span class="sxs-lookup"><span data-stu-id="5732f-118">If you set the policy right, you will see:</span></span>
  
![PowerShell : SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="5732f-120">Pour permettre à tous les utilisateurs de votre organisation d'utiliser le client Skype Entreprise (Lync), ouvrez la session PowerShell distante et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="5732f-121">Si vous définissez la stratégie actuelle, vous verrez :</span><span class="sxs-lookup"><span data-stu-id="5732f-121">If you set the policy right, you will see:</span></span>
  
![PowerShell : SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="5732f-123">Pour permettre à un seul utilisateur de votre organisation d'utiliser le client Skype Entreprise, ouvrez la session PowerShell distante et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="5732f-124">Si vous définissez la stratégie actuelle, vous verrez :</span><span class="sxs-lookup"><span data-stu-id="5732f-124">If you set the policy right, you will see:</span></span>
  
![Skype Entreprise Online - Activer l'IU](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="5732f-126">Pour permettre à un seul utilisateur de votre organisation d'utiliser le client Skype Entreprise (Lync), ouvrez la session PowerShell distante et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="5732f-127">Si vous définissez la stratégie actuelle, vous verrez :</span><span class="sxs-lookup"><span data-stu-id="5732f-127">If you set the policy right, you will see:</span></span>
  
![Skype Entreprise Online - IU désactivée](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="5732f-129">Pour permettre à plusieurs utilisateurs de votre organisation d'utiliser le client Skype Entreprise, ouvrez la session PowerShell distante et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="5732f-130">Pour permettre à plusieurs utilisateurs de votre organisation d'utiliser le client Skype Entreprise (Lync), ouvrez la session PowerShell distante et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="5732f-131">Pour permettre à un groupe d'utilisateurs de votre organisation d'utiliser le client Skype Entreprise, ouvrez la session PowerShell distante et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="5732f-132">Pour permettre à un groupe d'utilisateurs de votre organisation d'utiliser le client Skype Entreprise (Lync), ouvrez la session PowerShell distante et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="5732f-p105">Le nom d'utilisateur correspond au nom du compte d'utilisateur auquel la stratégie doit être attribuée. Le nom du compte d'utilisateur peut être entré dans l'un des formats suivants :>  Adresse SIP de l'utilisateur>  Nom d'utilisateur principal (UPN)>  Domaine\\nom d'utilisateur>  Nom complet Active Directory de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5732f-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="5732f-135">Utilisation de Windows PowerShell pour gérer Lync Online</span><span class="sxs-lookup"><span data-stu-id="5732f-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="5732f-136">Paramètres de stratégie de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="5732f-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="5732f-137">Ce tableau indique l'expérience utilisateur lorsque la stratégie est d'abord appliquée aux utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="5732f-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="5732f-138">**Paramètre de stratégie d'administration**</span><span class="sxs-lookup"><span data-stu-id="5732f-138">**Admin policy setting**</span></span>|<span data-ttu-id="5732f-139">**Interface utilisateur affichée**</span><span class="sxs-lookup"><span data-stu-id="5732f-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5732f-140">La stratégie n'est pas définie.</span><span class="sxs-lookup"><span data-stu-id="5732f-140">The policy isn't set.</span></span> |<span data-ttu-id="5732f-141">L'interface utilisateur restera celle du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="5732f-141">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```<br/>|<span data-ttu-id="5732f-142">L'interface utilisateur restera celle du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="5732f-142">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```<br/>|<span data-ttu-id="5732f-p106">L'utilisateur sera invité à basculer sur l'interface utilisateur du client Skype Entreprise (Lync). Le basculement peut être effectué plus tard.</span><span class="sxs-lookup"><span data-stu-id="5732f-p106">The user will be asked to switch to the Skype for Business (Lync) client user interface. They can switch later.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>```|<span data-ttu-id="5732f-145">L'interface utilisateur du client Skype Entreprise sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="5732f-145">The user will be using the Skype for Business client user interface.</span></span> |
```Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>```|<span data-ttu-id="5732f-146">L’utilisateur sera invité pour basculer vers le Skype pour l’interface utilisateur du client entreprise (Lync).</span><span class="sxs-lookup"><span data-stu-id="5732f-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="5732f-147">Un administrateur peut modifier le paramètre afin de basculer sur l'interface utilisateur du client Skype Entreprise ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="5732f-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="5732f-148">Ce tableau indique l'expérience utilisateur une fois la stratégie modifiée :</span><span class="sxs-lookup"><span data-stu-id="5732f-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="5732f-149">**Paramètre de stratégie d'administration**</span><span class="sxs-lookup"><span data-stu-id="5732f-149">**Admin policy setting**</span></span>|<span data-ttu-id="5732f-150">**Interface utilisateur de Skype Entreprise (Lync)**</span><span class="sxs-lookup"><span data-stu-id="5732f-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="5732f-151">**Interface utilisateur de Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="5732f-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```|<span data-ttu-id="5732f-152">L'utilisateur sera invité à basculer sur l'interface utilisateur du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="5732f-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="5732f-153">L'interface utilisateur restera celle du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="5732f-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```|<span data-ttu-id="5732f-154">L’utilisateur continue à utiliser le Skype pour interface métier (Lync).</span><span class="sxs-lookup"><span data-stu-id="5732f-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="5732f-155">L’utilisateur sera invité pour basculer vers le Skype pour l’interface utilisateur du client entreprise (Lync).</span><span class="sxs-lookup"><span data-stu-id="5732f-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="5732f-156">La stratégie n'est pas définie.</span><span class="sxs-lookup"><span data-stu-id="5732f-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="5732f-157">Les utilisateurs ne voient jamais le Skype pour l’interface utilisateur du client entreprise (Lync) si la stratégie n’est pas définie.</span><span class="sxs-lookup"><span data-stu-id="5732f-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="5732f-158">Ils continueront d'utiliser l'interface utilisateur du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="5732f-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="5732f-159">L'interface utilisateur restera celle du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="5732f-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="5732f-p109">Ce tableau présente toutes les stratégies personnalisées Online disponibles. Il existe de nouvelles stratégies créées afin d'offrir plus de flexibilité aux administrateurs qui souhaitent conserver l'ancienne stratégie personnalisée tout en basculant entre les différents indicateurs EnableSkypeUI. Utilisez les applets de commande ci-dessus pour accorder l'une des stratégies ci-dessous à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5732f-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="5732f-163">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="5732f-163">**Policy name**</span></span>|<span data-ttu-id="5732f-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="5732f-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
```ClientPolicyDefaultPhoto```||
```ClientPolicyDefaultPhotoDisableSkypeUI``` |<span data-ttu-id="5732f-165">False</span><span class="sxs-lookup"><span data-stu-id="5732f-165">False</span></span>|
```ClientPolicyNoIMURL```||
```ClientPolicyNoIMURLDisableSkypeUI``` |<span data-ttu-id="5732f-166">False</span><span class="sxs-lookup"><span data-stu-id="5732f-166">False</span></span>|
```ClientPolicyNoIMURLPhoto```||
```ClientPolicyNoIMURLPhotoDisableSkypeUI``` |<span data-ttu-id="5732f-167">False</span><span class="sxs-lookup"><span data-stu-id="5732f-167">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingI```||
```ClientPolicyNoSaveIMNoArchivingDisableSkypeUI``` |<span data-ttu-id="5732f-168">False</span><span class="sxs-lookup"><span data-stu-id="5732f-168">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURL```||
```ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI``` |<span data-ttu-id="5732f-169">False</span><span class="sxs-lookup"><span data-stu-id="5732f-169">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto``` ||
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI```|<span data-ttu-id="5732f-170">False</span><span class="sxs-lookup"><span data-stu-id="5732f-170">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingPhoto```||
```ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI``` |<span data-ttu-id="5732f-171">False</span><span class="sxs-lookup"><span data-stu-id="5732f-171">False</span></span>|

   
<span data-ttu-id="5732f-172">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="5732f-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- <span data-ttu-id="5732f-173">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="5732f-173">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- [<span data-ttu-id="5732f-174">Les meilleures façons de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5732f-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="5732f-175">Comportements client au premier lancement</span><span class="sxs-lookup"><span data-stu-id="5732f-175">First launch client behaviors</span></span>

<span data-ttu-id="5732f-176">Par défaut, lorsque les utilisateurs lancent Skype pour les entreprises pour la première fois, ils seront toujours voir le Skype pour l’interface utilisateur de Business--même si vous avez sélectionné l’expérience du client Lync en définissant la stratégie du client à l’expérience du client Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) tel que décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="5732f-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="5732f-177">Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.</span><span class="sxs-lookup"><span data-stu-id="5732f-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="5732f-178">Si vous souhaitez afficher l'interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez cette procédure avant le premier démarrage du client après la mise à jour :</span><span class="sxs-lookup"><span data-stu-id="5732f-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="5732f-179">Suivez la procédure décrite plus haut dans cette rubrique et confirmez que la stratégie client est définie pour désactiver l'interface utilisateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="5732f-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="5732f-p111">Mettez à jour le registre système sur l'ordinateur de l'utilisateur. Vous devez le faire avant que les utilisateurs lancent le client Skype Entreprise la première fois et vous ne devez effectuer cette opération qu'une seule fois. Pour plus d'informations sur la création d'un objet de stratégie de groupe pour mettre à jour le registre sur un ordinateur joint à un domaine, reportez-vous à la section dans la suite de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5732f-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="5732f-183">Dans la clé **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**, créez une valeur **Binaire**.</span><span class="sxs-lookup"><span data-stu-id="5732f-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="5732f-184">Le **nom de la valeur** doit être **EnableSkypeUI** et les **données de la valeur** doivent être définies sur la valeur **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="5732f-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="5732f-185">La clé doit se présenter comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="5732f-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="5732f-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span><span class="sxs-lookup"><span data-stu-id="5732f-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="5732f-187">« CanSharePptInCollab » = DWORD : 00000001</span><span class="sxs-lookup"><span data-stu-id="5732f-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="5732f-188">« CanShareOneNoteInCollab » = DWORD : 00000001</span><span class="sxs-lookup"><span data-stu-id="5732f-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="5732f-189">« CanAppShareInCollab » = DWORD : 00000001</span><span class="sxs-lookup"><span data-stu-id="5732f-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="5732f-190">« EnableSkypeUI » = hex : 00, 00, 00, 00</span><span class="sxs-lookup"><span data-stu-id="5732f-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="5732f-191">L'interface utilisateur de Lync s'affiche maintenant lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="5732f-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="5732f-192">Contrôle de l'affichage du didacticiel de l'écran d'accueil</span><span class="sxs-lookup"><span data-stu-id="5732f-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="5732f-193">Lorsque les utilisateurs ouvrent le Skype pour client d’entreprise, le comportement par défaut est d’afficher un écran de bienvenue qui inclut la *demande de la plupart des gens 7 astuces pour*.</span><span class="sxs-lookup"><span data-stu-id="5732f-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="5732f-194">Vous pouvez désactiver l'affichage de l'écran d'accueil, mais permettre quand même aux utilisateurs d'accéder au didacticiel en ajoutant la valeur de registre ci-dessous sur l'ordinateur client :</span><span class="sxs-lookup"><span data-stu-id="5732f-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="5732f-p113">Dans la clé **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**, créez une valeur **DWORD (32 bit)**. Le **nom de la valeur** doit être **IsBasicTutorialSeenByUser** et les **données de valeur** doivent être définies sur **1**.</span><span class="sxs-lookup"><span data-stu-id="5732f-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="5732f-197">La clé doit se présenter comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="5732f-197">The key should look like the following:</span></span>
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="5732f-198">Désactivation du didacticiel client</span><span class="sxs-lookup"><span data-stu-id="5732f-198">Turn off the client tutorial</span></span>

<span data-ttu-id="5732f-199">Si vous ne voulez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel du client avec la valeur de registre suivante :</span><span class="sxs-lookup"><span data-stu-id="5732f-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="5732f-p114">Dans la clé **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**, créez une valeur **DWORD (32 bit)**. Le **nom de la valeur** doit être **TutorialFeatureEnabled** et les **données de valeur** doivent être définies sur **0**.</span><span class="sxs-lookup"><span data-stu-id="5732f-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="5732f-202">Vous pouvez réactiver le didacticiel en définissant les **données de valeur** sur **1**.</span><span class="sxs-lookup"><span data-stu-id="5732f-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="5732f-203">Création d'un objet de stratégie de groupe pour modifier le registre sur un ordinateur joint au domaine</span><span class="sxs-lookup"><span data-stu-id="5732f-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="5732f-p115">La mise à jour du registre pour afficher l'expérience client Lync la première fois qu'un utilisateur lance le client Skype Entreprise ne doit être effectuée qu'une seule fois. Si vous utilisez un objet de stratégie de groupe pour mettre à jour le registre, vous devez définir l'objet pour créer une valeur et non mettre à jour les données d'une valeur. Lorsque l'objet de stratégie de groupe est appliqué, si la nouvelle valeur n'existe pas, l'objet stratégie de groupe la crée et définit les données de valeur sur 0.</span><span class="sxs-lookup"><span data-stu-id="5732f-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="5732f-p116">La procédure ci-dessous décrit comment modifier le registre afin que l'expérience client Lync s'affiche la première fois qu'un utilisateur lance le client Skype Entreprise. Vous pouvez également utiliser cette procédure pour mettre à jour le registre afin de désactiver l'écran d'accueil du didacticiel, comme indiqué précédemment.</span><span class="sxs-lookup"><span data-stu-id="5732f-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="5732f-209">**Pour créer l’objet de stratégie de groupe**</span><span class="sxs-lookup"><span data-stu-id="5732f-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="5732f-210">Démarrez la **Console de gestion des stratégies de groupe**.</span><span class="sxs-lookup"><span data-stu-id="5732f-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="5732f-211">Pour plus d'informations sur l'utilisation de la Console de gestion des stratégies de groupe, reportez-vous à l'article [Console de gestion des stratégies de groupe](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="5732f-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="5732f-212">Cliquez avec le bouton droit sur le nœud **Objets de stratégie de groupe** et sélectionnez **Nouveau** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="5732f-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="5732f-213">Dans la boîte de dialogue **Nouvel objet GPO**, entrez un nom pour l'objet GPO, par exemple, MakeLyncDefaultUI, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5732f-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="5732f-214">Cliquez avec le bouton droit sur le nouvel objet GPO que vous venez de créer, puis sélectionnez **Modifier** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="5732f-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="5732f-215">Dans **Éditeur de gestion des stratégies de groupe**, développez **Configuration utilisateur**, **Préférences**, **Paramètres Windows**, puis sélectionnez le nœud **Registre**.</span><span class="sxs-lookup"><span data-stu-id="5732f-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="5732f-216">Cliquez avec le bouton droit sur le nœud **Registre**, puis sélectionnez **Nouveau** > **Élément Registre**.</span><span class="sxs-lookup"><span data-stu-id="5732f-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="5732f-217">Dans la boîte de dialogue **Nouvelles propriétés de registre**, mettez à jour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="5732f-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="5732f-218">**Champ**</span><span class="sxs-lookup"><span data-stu-id="5732f-218">**Field**</span></span>|<span data-ttu-id="5732f-219">**Valeur à sélectionner ou entrer**</span><span class="sxs-lookup"><span data-stu-id="5732f-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5732f-220">**Action**</span><span class="sxs-lookup"><span data-stu-id="5732f-220">**Action**</span></span> <br/> |<span data-ttu-id="5732f-221">**Créer**</span><span class="sxs-lookup"><span data-stu-id="5732f-221">**Create**</span></span> <br/> |
|<span data-ttu-id="5732f-222">**Ruche**</span><span class="sxs-lookup"><span data-stu-id="5732f-222">**Hive**</span></span> <br/> | <span data-ttu-id="5732f-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="5732f-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="5732f-224">**Chemin d'accès à la clé**</span><span class="sxs-lookup"><span data-stu-id="5732f-224">**Key Path**</span></span> <br/> |<span data-ttu-id="5732f-225">Logiciel\\Microsoft\\Office\\Lync</span><span class="sxs-lookup"><span data-stu-id="5732f-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="5732f-226">**Nom de la valeur**</span><span class="sxs-lookup"><span data-stu-id="5732f-226">**Value name**</span></span> <br/> |<span data-ttu-id="5732f-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="5732f-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="5732f-228">**Type de la valeur**</span><span class="sxs-lookup"><span data-stu-id="5732f-228">**Value type**</span></span> <br/> |<span data-ttu-id="5732f-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="5732f-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="5732f-230">**Données de la valeur**</span><span class="sxs-lookup"><span data-stu-id="5732f-230">**Value data**</span></span> <br/> |<span data-ttu-id="5732f-231">00000000</span><span class="sxs-lookup"><span data-stu-id="5732f-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="5732f-232">Cliquez sur **OK** pour enregistrer les modifications, puis fermez l'objet GPO.</span><span class="sxs-lookup"><span data-stu-id="5732f-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="5732f-233">Ensuite, vous devez lier l'objet GPO créé au groupe d'utilisateurs auquel vous voulez affecter la stratégie, par exemple, une unité d'organisation.</span><span class="sxs-lookup"><span data-stu-id="5732f-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="5732f-234">**Pour utiliser l’objet de stratégie de groupe pour attribuer la stratégie**</span><span class="sxs-lookup"><span data-stu-id="5732f-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="5732f-235">Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l'unité d'organisation à laquelle vous voulez affecter la stratégie, puis sélectionnez **Lier un objet de stratégie de groupe existant**.</span><span class="sxs-lookup"><span data-stu-id="5732f-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="5732f-236">Dans la boîte de dialogue **Sélectionner un objet GPO**, sélectionnez l'objet GPO créé, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="5732f-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="5732f-237">Sur l'ordinateur de l'utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="5732f-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="5732f-238">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="5732f-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="5732f-p117">Le message « mise à jour la stratégie… » s'affiche pendant l'application de l'objet GPO. Au terme de l'opération, le message « La mise à jour de la stratégie utilisateur s'est terminée sans erreur. » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="5732f-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="5732f-241">Dans l'invite de commandes, tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="5732f-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="5732f-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="5732f-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="5732f-243">« Objets de stratégie de groupé affectés » doit s'afficher avec le nom de l'objet GPO créé en-dessous.</span><span class="sxs-lookup"><span data-stu-id="5732f-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="5732f-p118">Vous pouvez également vérifier que l'objet de stratégie de groupe a mis à jour le registre sur l'ordinateur de l'utilisateur en examinant le registre. Ouvrez l'Éditeur du registre et accédez à la clé **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Si l'objet GPO a mis à jour correctement le registre, la valeur nommée EnableSkypeUI s'affiche avec la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="5732f-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5732f-247">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="5732f-247">Related topics</span></span>
[<span data-ttu-id="5732f-248">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="5732f-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5732f-249">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="5732f-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 