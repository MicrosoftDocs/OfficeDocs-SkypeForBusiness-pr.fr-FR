---
title: Définir l'ID d'appelant d'un utilisateur
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: En savoir plus sur l’ID d’appelant par défaut Microsoft 365 et Office 365 (le numéro de téléphone affecté d’un utilisateur), également appelé ID de ligne d’appel. Vous pouvez modifier ou bloquer l’ID d’appelant d’un utilisateur.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569416"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="c1695-104">Définir l'ID d'appelant d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c1695-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="c1695-105">Le système téléphonique de Microsoft 365 et Office 365 fournit un ID d’appelant par défaut, qui est le numéro de téléphone affecté à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c1695-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="c1695-106">Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé ID de ligne d'appel).</span><span class="sxs-lookup"><span data-stu-id="c1695-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="c1695-107">Pour en savoir plus sur l’utilisation de l’ID d’appelant dans votre organisation, voir Comment utiliser [l’ID](how-can-caller-id-be-used-in-your-organization.md)d’appelant dans votre organisation .</span><span class="sxs-lookup"><span data-stu-id="c1695-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="c1695-108">Vous ne pouvez actuellement pas bloquer les appels entrants dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="c1695-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="c1695-109">Vous pouvez changer les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c1695-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1695-110">Ceci **n'est pas** destiné aux organisations sur site avec Lync ou Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c1695-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="c1695-p103">**Changer l'ID d'appelant sortant** Vous pouvez remplacer l'ID d'appelant d'un utilisateur, constitué par défaut par son numéro de téléphone, par un autre numéro de téléphone. Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique. Vous pouvez remplacer le numéro d'ID d'appel par un numéro de **service** en ligne (payant ou gratuit).</span><span class="sxs-lookup"><span data-stu-id="c1695-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1695-114">Si vous souhaitez utiliser le paramètre  _Service_, vous devez spécifier un numéro de service valide.</span><span class="sxs-lookup"><span data-stu-id="c1695-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="c1695-115">**Bloquer l’ID d’appelant sortant** Vous pouvez empêcher l’ID d’appelant sortant d’être envoyé lors des appels RSTN sortants d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c1695-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="c1695-116">Ce faisant, vous empêchez son numéro de téléphone d'être affiché sur le téléphone d'une personne contactée.</span><span class="sxs-lookup"><span data-stu-id="c1695-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="c1695-117">**Bloquer l’ID d’appelant entrant** Vous pouvez empêcher un utilisateur de recevoir l’ID d’appelant à chaque appel RSTN entrant.</span><span class="sxs-lookup"><span data-stu-id="c1695-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="c1695-118">Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c1695-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="c1695-p105">Par défaut, chacun de ces paramètres d'ID d'appelant est **désactivé**. Cela signifie que le numéro de téléphone de l'utilisateur de Skype Entreprise Online est visible lorsque l'utilisateur effectue un appel vers un téléphone RTC.</span><span class="sxs-lookup"><span data-stu-id="c1695-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="c1695-121">Pour en savoir plus sur ces paramètres et leur utilisation, cliquez [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c1695-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="c1695-122">Définir vos paramètres de stratégie d'ID d'appelant</span><span class="sxs-lookup"><span data-stu-id="c1695-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="c1695-123">Pour tous les paramètres **d’ID d’appelant** dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et le Centre d’administration **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="c1695-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="c1695-124">Démarrer PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1695-124">Start PowerShell</span></span>

- <span data-ttu-id="c1695-125">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1695-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="c1695-126">Voir l'ensemble des paramètres de stratégie d'ID d'appelant de votre organisation</span><span class="sxs-lookup"><span data-stu-id="c1695-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="c1695-127">Pour afficher tous les paramètres de stratégie d’ID d’appelant de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c1695-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="c1695-128">Consultez plus d’exemples et de [détails pour Get-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793856.aspx)</span><span class="sxs-lookup"><span data-stu-id="c1695-128">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="c1695-129">Créer une stratégie d'ID d'appelant pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="c1695-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="c1695-130">Pour créer une stratégie d’ID d’appelant qui définit l’ID d’appelant sur anonyme, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c1695-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="c1695-131">Dans tous les cas, le champ « Numéro » ne doit pas inclure le préfixe « + ».</span><span class="sxs-lookup"><span data-stu-id="c1695-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="c1695-132">Consultez plus d’exemples et de [détails pour New-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793855.aspx)</span><span class="sxs-lookup"><span data-stu-id="c1695-132">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="c1695-133">Pour appliquer la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c1695-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="c1695-134">En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1695-134">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="c1695-135">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c1695-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="c1695-136">Définir la stratégie de manière à bloquer l'ID d'appelant</span><span class="sxs-lookup"><span data-stu-id="c1695-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="c1695-137">Pour bloquer l’ID d’appelant entrant, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c1695-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="c1695-138">Consultez plus d’exemples et de [détails pour Set-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793854.aspx)</span><span class="sxs-lookup"><span data-stu-id="c1695-138">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="c1695-139">Pour appliquer le paramètre de stratégie que vous avez créé à un utilisateur de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c1695-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="c1695-140">En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1695-140">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="c1695-141">Stratégie de suppression dʼID dʼappelant</span><span class="sxs-lookup"><span data-stu-id="c1695-141">Remove a caller ID policy</span></span>

<span data-ttu-id="c1695-142">Pour supprimer une stratégie de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c1695-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="c1695-143">Pour supprimer une stratégie dʼun utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c1695-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c1695-144">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="c1695-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="c1695-145">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="c1695-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c1695-146">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="c1695-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c1695-147">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="c1695-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c1695-148">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c1695-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c1695-149">Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="c1695-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c1695-150">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="c1695-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c1695-151">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1695-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c1695-152">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1695-152">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c1695-153">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c1695-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c1695-154">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c1695-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="c1695-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c1695-155">Related topics</span></span>
[<span data-ttu-id="c1695-156">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="c1695-156">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="c1695-157">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="c1695-157">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="c1695-158">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="c1695-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c1695-159">Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant</span><span class="sxs-lookup"><span data-stu-id="c1695-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="c1695-160">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="c1695-160">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c1695-161">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c1695-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
