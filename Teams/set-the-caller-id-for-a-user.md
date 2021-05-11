---
title: Définir l'ID d'appelant d'un utilisateur
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: En savoir plus sur Microsoft 365 et Office 365'ID d’appelant par défaut (le numéro de téléphone affecté d’un utilisateur), également appelé ID de ligne d’appel. Vous pouvez modifier ou bloquer l’ID d’appelant d’un utilisateur.
ms.openlocfilehash: dbbb48952264d82ca24bdd82dbb45538b0428368
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308333"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="f8296-104">Définir l'ID d'appelant d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f8296-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="f8296-105">Système téléphonique dans Microsoft 365 fournit un ID d’appelant par défaut, c’est-à-dire le numéro de téléphone affecté à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f8296-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="f8296-106">Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé ID de ligne d'appel).</span><span class="sxs-lookup"><span data-stu-id="f8296-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="f8296-107">Pour en savoir plus sur l’utilisation de l’ID d’appelant dans votre organisation, voir Comment utiliser [l’ID](how-can-caller-id-be-used-in-your-organization.md)d’appelant dans votre organisation .</span><span class="sxs-lookup"><span data-stu-id="f8296-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="f8296-108">Par défaut, les paramètres d’ID d’appelant suivants **sont désactivés.**</span><span class="sxs-lookup"><span data-stu-id="f8296-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="f8296-109">Cela signifie que le Teams de téléphone de l’utilisateur peut être vu quand cet utilisateur appelle un téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8296-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="f8296-110">Vous pouvez modifier ces paramètres comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8296-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="f8296-111">**ID de l’appelant sortant** Vous pouvez remplacer l’ID d’appelant d’un utilisateur, qui est son numéro de téléphone par défaut, par un autre numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f8296-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="f8296-112">Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique.</span><span class="sxs-lookup"><span data-stu-id="f8296-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="f8296-113">Vous pouvez modifier le numéro d’ID d’appel en n’importe quel numéro de service en ligne (gratuit ou gratuit).</span><span class="sxs-lookup"><span data-stu-id="f8296-113">You can change the Calling ID number to any online service number (toll or toll-free).</span></span> <span data-ttu-id="f8296-114">Vous pouvez également changer le numéro d’ID d’appel en numéro de téléphone local via un routage direct affecté à un compte de ressource utilisé par une Standard automatique ou une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f8296-114">You can also change the Calling ID number to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="f8296-115">Si vous souhaitez utiliser le paramètre *Service,* vous devez spécifier un numéro de service valide.</span><span class="sxs-lookup"><span data-stu-id="f8296-115">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="f8296-116">**Bloquer l’ID d’appelant sortant**</span><span class="sxs-lookup"><span data-stu-id="f8296-116">**Block outbound caller ID.**</span></span> <span data-ttu-id="f8296-117">Vous pouvez empêcher l’ID d’appelant sortant d’être envoyé lors des appels RSTN sortants d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f8296-117">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="f8296-118">Ce faisant, vous empêchez son numéro de téléphone d'être affiché sur le téléphone d'une personne contactée.</span><span class="sxs-lookup"><span data-stu-id="f8296-118">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="f8296-119">**Bloquer l’ID d’appelant entrant.**</span><span class="sxs-lookup"><span data-stu-id="f8296-119">**Block incoming caller ID.**</span></span> <span data-ttu-id="f8296-120">Vous pouvez empêcher un utilisateur de recevoir l’ID d’appelant à chaque appel RSTN entrant.</span><span class="sxs-lookup"><span data-stu-id="f8296-120">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="f8296-121">**Définissez le nom de l’appelant (CNAM).**</span><span class="sxs-lookup"><span data-stu-id="f8296-121">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="f8296-122">Pour vos Microsoft Teams utilisateurs, vous pouvez envoyer un CNAM dans les appels RSTN sortants.</span><span class="sxs-lookup"><span data-stu-id="f8296-122">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="f8296-123">Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f8296-123">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="f8296-124">Pour en savoir plus sur ces paramètres et sur leur utilisation, consultez comment utiliser l’ID d’appelant [dans votre organisation.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="f8296-124">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="f8296-125">Définir vos paramètres de stratégie d'ID d'appelant</span><span class="sxs-lookup"><span data-stu-id="f8296-125">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="f8296-126">Pour définir l’ID d’appelant sur un numéro de téléphone de compte de ressource et définir le nom de l’appelant, utilisez les cmdlets PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity dans le module Teams PowerShell 2.3.1 ou une ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f8296-126">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="f8296-127">(Ces options ne sont actuellement pas disponibles dans le Centre Microsoft Teams’administration.)</span><span class="sxs-lookup"><span data-stu-id="f8296-127">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="f8296-128">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8296-128">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="f8296-129">Afficher, créer et appliquer des paramètres de stratégie</span><span class="sxs-lookup"><span data-stu-id="f8296-129">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="f8296-130">Pour afficher tous les paramètres de stratégie d’ID d’appelant de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f8296-130">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="f8296-131">Pour plus d’informations, [voir Get-CsCallingLineIdentity.](/powershell/module/skype/Get-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="f8296-131">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="f8296-132">Pour créer une stratégie d’ID d’appelant pour votre organisation, utilisez l'New-CsCallingIdentity de la société :</span><span class="sxs-lookup"><span data-stu-id="f8296-132">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="f8296-133">Dans tous les cas, le champ « Numéro » ne doit pas inclure le préfixe « + ».</span><span class="sxs-lookup"><span data-stu-id="f8296-133">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="f8296-134">Pour plus d’informations, [voir New-CsCallingLineIdentity.](/powershell/module/skype/New-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="f8296-134">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="f8296-135">Appliquez la nouvelle stratégie que vous avez créée à l’aide Grant-CsCallingIdentity cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8296-135">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="f8296-136">Par exemple, l’exemple suivant applique la nouvelle stratégie à l’utilisateur Amos Marble.</span><span class="sxs-lookup"><span data-stu-id="f8296-136">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="f8296-137">Pour plus d’informations, [voir la cmdlet Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="f8296-137">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="f8296-138">Si vous souhaitez bloquer l’ID d’appelant entrant, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f8296-138">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="f8296-139">Pour plus d’informations, [voir Set-CsCallingLineIdentity.](/powershell/module/skype/Set-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="f8296-139">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="f8296-140">Pour appliquer le paramètre de stratégie que vous avez créé à un utilisateur de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f8296-140">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="f8296-141">Pour plus d’informations, [voir Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="f8296-141">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="f8296-142">Pour créer une stratégie d’ID d’appelant qui définit l’ID d’appelant sur le numéro de téléphone du compte de ressource spécifié et définit le nom de l’appelant sur Contoso :</span><span class="sxs-lookup"><span data-stu-id="f8296-142">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="f8296-143">Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) pour appliquer les paramètres à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f8296-143">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="f8296-144">Supprimer un paramètre de stratégie</span><span class="sxs-lookup"><span data-stu-id="f8296-144">Remove a policy setting</span></span>

<span data-ttu-id="f8296-145">Pour supprimer une stratégie de votre organisation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f8296-145">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="f8296-146">Pour supprimer une stratégie dʼun utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f8296-146">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f8296-147">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="f8296-147">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f8296-148">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="f8296-148">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f8296-149">En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365'aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien.</span><span class="sxs-lookup"><span data-stu-id="f8296-149">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="f8296-150">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="f8296-150">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="f8296-151">Présentation des Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8296-151">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="f8296-152">Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8296-152">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="f8296-153">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="f8296-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f8296-154">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8296-154">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="f8296-155">[Les meilleures façons de gérer Microsoft 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f8296-155">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="f8296-156">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f8296-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="f8296-157">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f8296-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="f8296-158">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f8296-158">Related topics</span></span>
[<span data-ttu-id="f8296-159">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="f8296-159">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="f8296-160">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="f8296-160">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="f8296-161">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="f8296-161">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="f8296-162">Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant</span><span class="sxs-lookup"><span data-stu-id="f8296-162">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="f8296-163">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="f8296-163">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="f8296-164">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f8296-164">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
