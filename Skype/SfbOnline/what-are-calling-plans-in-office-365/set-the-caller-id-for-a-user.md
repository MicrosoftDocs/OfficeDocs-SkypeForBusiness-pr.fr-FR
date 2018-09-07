---
title: Définir l'ID d'appelant d'un utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Le système téléphonique dans Office 365 fournit un ID d’appelant par défaut qui est le numéro de téléphone attribué. Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé ID de ligne d'appel). Pour en savoir plus sur l’utilisation de l’ID d’appelant dans votre organisation, cliquez sur Comment utiliser un ID d’appelant dans votre organisation.
ms.openlocfilehash: cb32a7dcc38dcdd7fbaa5bf414d711953d237deb
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858654"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="61519-105">Définir l'ID d'appelant d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="61519-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="61519-106">Le système téléphonique dans Office 365 fournit un ID d’appelant par défaut qui est le numéro de téléphone attribué.</span><span class="sxs-lookup"><span data-stu-id="61519-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="61519-107">Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé ID de ligne d'appel).</span><span class="sxs-lookup"><span data-stu-id="61519-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="61519-108">Pour en savoir plus sur l’utilisation de l’ID d’appelant dans votre organisation, cliquez sur [Comment utiliser un ID d’appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="61519-108">You learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="61519-109">Vous ne pouvez actuellement pas bloquer les appels entrants dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="61519-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="61519-110">Vous pouvez changer les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="61519-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="61519-111">Ceci **n'est pas** destiné aux organisations sur site avec Lync ou Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="61519-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="61519-p103">**Changer l'ID d'appelant sortant** Vous pouvez remplacer l'ID d'appelant d'un utilisateur, constitué par défaut par son numéro de téléphone, par un autre numéro de téléphone. Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique. Vous pouvez remplacer le numéro d'ID d'appel par un numéro de **service** en ligne (payant ou gratuit).</span><span class="sxs-lookup"><span data-stu-id="61519-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="61519-115">Si vous souhaitez utiliser le paramètre  _Service_, vous devez spécifier un numéro de service valide.</span><span class="sxs-lookup"><span data-stu-id="61519-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="61519-116">**Bloquer l’identification de l’appelant sortant** Vous pouvez empêcher l’identifiant de l’appelant sortant d’être envoyé lors des appels RTC sortants d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61519-116">**Block their outbound caller ID** You can block their outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="61519-117">Ce faisant, vous empêchez son numéro de téléphone d'être affiché sur le téléphone d'une personne contactée.</span><span class="sxs-lookup"><span data-stu-id="61519-117">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="61519-118">**Bloquer l’identification de l’appelant entrant** Vous pouvez empêcher l’utilisateur de recevoir l’identifiant de l’appelant de tous les appels RTC entrants.</span><span class="sxs-lookup"><span data-stu-id="61519-118">**Block their incoming caller ID** You can block the user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="61519-119">Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61519-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="61519-p105">Par défaut, chacun de ces paramètres d'ID d'appelant est **désactivé**. Cela signifie que le numéro de téléphone de l'utilisateur de Skype Entreprise Online est visible lorsque l'utilisateur effectue un appel vers un téléphone RTC.</span><span class="sxs-lookup"><span data-stu-id="61519-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="61519-122">Pour en savoir plus sur ces paramètres et leur utilisation, cliquez [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="61519-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="61519-123">Définir vos paramètres de stratégie d'ID d'appelant</span><span class="sxs-lookup"><span data-stu-id="61519-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="61519-124">Pour tous les paramètres d’identification de l’appelant dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration de Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="61519-124">For all of the callerID settings in Skype for Business Online you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="61519-125">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61519-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="61519-126">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="61519-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="61519-127">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="61519-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="61519-128">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="61519-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="61519-p106">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="61519-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="61519-p107">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="61519-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="61519-135">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="61519-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="61519-136">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="61519-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="61519-137">Depuis le **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="61519-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="61519-138">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="61519-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="61519-139">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="61519-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
> 
  ```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```
> 
  ```
  $credential = Get-Credential
  ```
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```
> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="61519-140">Pour plus d’informations sur le démarrage de Windows PowerShell, consultez la rubrique [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connexion à Skype Entreprise Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="61519-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="61519-141">Voir l'ensemble des paramètres de stratégie d'ID d'appelant de votre organisation</span><span class="sxs-lookup"><span data-stu-id="61519-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="61519-142">Pour afficher l’ensemble des paramètres de politique d’identification de l’appelant de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="61519-142">View all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
<span data-ttu-id="61519-143">Consulter plus d’exemples et de détails sur [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="61519-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="61519-144">Créer une stratégie d'ID d'appelant pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="61519-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="61519-145">Pour créer une politique d’identification de l’appelant qui définit l’identification de l’appelant sur anonyme, exécutez :</span><span class="sxs-lookup"><span data-stu-id="61519-145">Create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="61519-146">Dans tous les cas, le champ « Numéro » ne doit pas inclure le préfixe « + ».</span><span class="sxs-lookup"><span data-stu-id="61519-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="61519-147">Consultez plus d’exemples et de détails sur [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="61519-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)</span></span>
    
- <span data-ttu-id="61519-148">Pour appliquer la nouvelle politique créée pour Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="61519-148">Apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="61519-149">En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="61519-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="61519-150">Si vous avez déjà créé une politique, vous pouvez utiliser le cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) pour apporter des modifications à la politique existante, puis utiliser le cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="61519-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, then use the[Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="61519-151">Définir la stratégie de manière à bloquer l'ID d'appelant</span><span class="sxs-lookup"><span data-stu-id="61519-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="61519-152">Pour bloquer l’identification de l’appelant entrant, exécutez :</span><span class="sxs-lookup"><span data-stu-id="61519-152">Block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="61519-153">Consulter plus d’exemples et de détails sur [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="61519-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)</span></span>
    
- <span data-ttu-id="61519-154">Pour appliquer le paramètre de politique créé à un utilisateur de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="61519-154">Apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="61519-155">En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="61519-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="61519-156">Stratégie de suppression dʼID dʼappelant</span><span class="sxs-lookup"><span data-stu-id="61519-156">Remove a caller ID policy</span></span>

<span data-ttu-id="61519-157">Pour supprimer une stratégie de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="61519-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="61519-158">Pour supprimer une stratégie dʼun utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="61519-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="61519-159">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="61519-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="61519-160">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="61519-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="61519-161">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="61519-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="61519-162">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="61519-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="61519-163">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="61519-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="61519-164">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="61519-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="61519-p109">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="61519-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="61519-167">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61519-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="61519-168">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="61519-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="61519-169">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="61519-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="61519-170">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="61519-170">Related topics</span></span>
[<span data-ttu-id="61519-171">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="61519-171">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="61519-172">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="61519-172">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="61519-173">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="61519-173">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="61519-174">Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant</span><span class="sxs-lookup"><span data-stu-id="61519-174">More about Calling Line ID and Calling Party Name</span></span>](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[<span data-ttu-id="61519-175">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="61519-175">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="61519-176">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="61519-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
