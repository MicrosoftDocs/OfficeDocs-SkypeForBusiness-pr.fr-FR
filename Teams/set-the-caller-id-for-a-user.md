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
description: En savoir plus sur l’ID de l’appelant par défaut d’Office 365 (le numéro de téléphone affecté à l’utilisateur), également connu sous le nom d’ID de ligne d’appel. Vous pouvez modifier ou bloquer l’ID d’appelant d’un utilisateur.
ms.openlocfilehash: c04fdfa7dc395f31eb3277fe0ab2f77aa92605c7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140907"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="49bfd-104">Définir l'ID d'appelant d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="49bfd-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="49bfd-105">Le système téléphonique dans Office 365 fournit un ID d’appelant par défaut qui est le numéro de téléphone attribué.</span><span class="sxs-lookup"><span data-stu-id="49bfd-105">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="49bfd-106">Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé ID de ligne d'appel).</span><span class="sxs-lookup"><span data-stu-id="49bfd-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="49bfd-107">Pour plus d’informations sur l’utilisation de l’identification de l’appelant au sein de votre organisation, voir utilisation [de l’ID d’appelant au sein de votre organisation](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="49bfd-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="49bfd-108">Vous ne pouvez actuellement pas bloquer les appels entrants dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="49bfd-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="49bfd-109">Vous pouvez changer les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="49bfd-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="49bfd-110">Ceci **n'est pas** destiné aux organisations sur site avec Lync ou Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="49bfd-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="49bfd-p103">**Changer l'ID d'appelant sortant** Vous pouvez remplacer l'ID d'appelant d'un utilisateur, constitué par défaut par son numéro de téléphone, par un autre numéro de téléphone. Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique. Vous pouvez remplacer le numéro d'ID d'appel par un numéro de **service** en ligne (payant ou gratuit).</span><span class="sxs-lookup"><span data-stu-id="49bfd-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="49bfd-114">Si vous souhaitez utiliser le paramètre  _Service_, vous devez spécifier un numéro de service valide.</span><span class="sxs-lookup"><span data-stu-id="49bfd-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="49bfd-115">**Bloquer l’ID d’appelant sortant** Vous pouvez empêcher l’envoi de l’ID d’appelant sortant sur les appels RTC sortants d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="49bfd-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="49bfd-116">Ce faisant, vous empêchez son numéro de téléphone d'être affiché sur le téléphone d'une personne contactée.</span><span class="sxs-lookup"><span data-stu-id="49bfd-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="49bfd-117">**Bloquer l’ID d’appelant entrant** Vous pouvez empêcher un utilisateur de recevoir l’ID d’appelant à chaque appel RTC entrant.</span><span class="sxs-lookup"><span data-stu-id="49bfd-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="49bfd-118">Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="49bfd-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="49bfd-p105">Par défaut, chacun de ces paramètres d'ID d'appelant est **désactivé**. Cela signifie que le numéro de téléphone de l'utilisateur de Skype Entreprise Online est visible lorsque l'utilisateur effectue un appel vers un téléphone RTC.</span><span class="sxs-lookup"><span data-stu-id="49bfd-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="49bfd-121">Pour en savoir plus sur ces paramètres et leur utilisation, cliquez [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="49bfd-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="49bfd-122">Définir vos paramètres de stratégie d'ID d'appelant</span><span class="sxs-lookup"><span data-stu-id="49bfd-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="49bfd-123">Pour tous les paramètres d’identification de l’appelant dans Skype entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="49bfd-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="49bfd-124">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bfd-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="49bfd-125">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="49bfd-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="49bfd-126">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="49bfd-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="49bfd-127">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="49bfd-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="49bfd-128">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49bfd-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="49bfd-129">Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="49bfd-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="49bfd-130">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="49bfd-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="49bfd-p107">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="49bfd-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="49bfd-134">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="49bfd-134">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="49bfd-135">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="49bfd-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="49bfd-136">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="49bfd-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="49bfd-137">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="49bfd-137">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="49bfd-138">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="49bfd-138">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="49bfd-139">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="49bfd-139">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="49bfd-140">Voir l'ensemble des paramètres de stratégie d'ID d'appelant de votre organisation</span><span class="sxs-lookup"><span data-stu-id="49bfd-140">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="49bfd-141">Pour afficher tous les paramètres de stratégie d’ID d’appelant au sein de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49bfd-141">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="49bfd-142">Voir d’autres exemples et des informations supplémentaires sur [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="49bfd-142">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="49bfd-143">Créer une stratégie d'ID d'appelant pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="49bfd-143">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="49bfd-144">Pour créer une nouvelle stratégie d’ID d’appelant qui définit l’ID d’appelant sur anonyme, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49bfd-144">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="49bfd-145">Dans tous les cas, le champ « Numéro » ne doit pas inclure le préfixe « + ».</span><span class="sxs-lookup"><span data-stu-id="49bfd-145">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="49bfd-146">En savoir plus sur [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="49bfd-146">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="49bfd-147">Pour appliquer la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49bfd-147">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="49bfd-148">En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="49bfd-148">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="49bfd-149">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="49bfd-149">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="49bfd-150">Définir la stratégie de manière à bloquer l'ID d'appelant</span><span class="sxs-lookup"><span data-stu-id="49bfd-150">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="49bfd-151">Pour bloquer l’ID de l’appelant, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49bfd-151">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="49bfd-152">En savoir plus sur [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="49bfd-152">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="49bfd-153">Pour appliquer le paramètre de stratégie que vous avez créé à un utilisateur de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49bfd-153">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="49bfd-154">En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="49bfd-154">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="49bfd-155">Stratégie de suppression dʼID dʼappelant</span><span class="sxs-lookup"><span data-stu-id="49bfd-155">Remove a caller ID policy</span></span>

<span data-ttu-id="49bfd-156">Pour supprimer une stratégie de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49bfd-156">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="49bfd-157">Pour supprimer une stratégie dʼun utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49bfd-157">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="49bfd-158">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="49bfd-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="49bfd-159">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="49bfd-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="49bfd-160">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="49bfd-160">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="49bfd-161">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="49bfd-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="49bfd-162">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="49bfd-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="49bfd-163">Six raisons d’utiliser Windows PowerShell pour gérer Office 365</span><span class="sxs-lookup"><span data-stu-id="49bfd-163">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="49bfd-164">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="49bfd-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="49bfd-165">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="49bfd-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="49bfd-166">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bfd-166">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="49bfd-167">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="49bfd-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="49bfd-168">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="49bfd-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="49bfd-169">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="49bfd-169">Related topics</span></span>
[<span data-ttu-id="49bfd-170">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="49bfd-170">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="49bfd-171">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="49bfd-171">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="49bfd-172">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="49bfd-172">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="49bfd-173">Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant</span><span class="sxs-lookup"><span data-stu-id="49bfd-173">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="49bfd-174">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="49bfd-174">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="49bfd-175">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="49bfd-175">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
