---
title: Affectation, modification ou suppression du numéro de téléphone d’un utilisateur
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Découvrez comment affecter, modifier ou supprimer un numéro de téléphone professionnel pour vos équipes ou les utilisateurs Skype entreprise de sorte que les entreprises et les clients externes puissent appeler.
ms.openlocfilehash: ea2135a095a60d6da37ce4db0fb443f2e9a74154
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493897"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="7c1c1-103">Affectation, modification ou suppression du numéro de téléphone d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7c1c1-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="7c1c1-104">Lorsque vous configurez des forfaits d’appels dans Office 365, vous attribuez des numéros de téléphone à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="7c1c1-105">Dans le client Microsoft Teams, le numéro de téléphone que vous assignez apparaît lorsqu’ils cliquent sur **Appels**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Le numéro de téléphone de l’utilisateur affiché dans Microsoft Teams.](media/teams-phone-number.png)

<span data-ttu-id="7c1c1-107">Dans le client Skype entreprise, le numéro de téléphone que vous attribuez figurera dans la zone **téléphone professionnel** et ne peut pas être modifié par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![Work Phone Number is Greyed Out.](media/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="7c1c1-109">Si un utilisateur souhaite [changer son numéro de téléphone pour Skype entreprise](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) et si le numéro de téléphone dans l’application Skype entreprise ne peut pas être modifié ou s’il est grisé, cela signifie qu’un administrateur l’a configuré pour eux et qu’il ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="7c1c1-110">Lorsque vous configurez les utilisateurs pour qu’ils puissent passer et recevoir des appels téléphoniques, vous devez d’abord utiliser le centre d’administration Skype entreprise et attribuer un numéro de téléphone, mais vous pouvez modifier ou supprimer le numéro de téléphone le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="7c1c1-111">Pour savoir comment obtenir des Forfaits d’appels dans Office 365 et leur coût, consultez la rubrique [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="7c1c1-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c1c1-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="7c1c1-115">Affectation d’un numéro de téléphone à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7c1c1-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="7c1c1-116">![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="7c1c1-116">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="7c1c1-117">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7c1c1-118">Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-118">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="7c1c1-119">Dans le volet de navigation de gauche, cliquez sur**utilisateurs**vocaux **vocaux** > .</span><span class="sxs-lookup"><span data-stu-id="7c1c1-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="7c1c1-120">Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration de Skype entreprise, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="7c1c1-120">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="7c1c1-121">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs auxquels vous souhaitez affecter un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="7c1c1-122">Dans le volet Action, cliquez sur **Affecter un numéro**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="7c1c1-123">Dans la page **attribuer un numéro** , dans la liste Sélectionner le **numéro à attribuer** , sélectionnez le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7c1c1-124">Si vous ne voyez aucun numéro de téléphone dans la liste, vous devez d’abord [obtenir des numéros de téléphone pour vos utilisateurs](/microsoftteams/getting-phone-numbers-for-your-users) .</span><span class="sxs-lookup"><span data-stu-id="7c1c1-124">If you don't see any phone numbers listed, you need to [get phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users) first.</span></span> <span data-ttu-id="7c1c1-125">Ou, si vous utilisez le **centre d’administration Skype Entreprise** > **Voix** > page **Numéros de téléphone**, cliquez sur **Ajouter**, puis cliquez sur **Nouveaux numéros utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="7c1c1-126">Pour attribuer ou modifier l’adresse d’urgence associée, sous **Sélectionner l’emplacement d’urgence validée**, sélectionnez l’emplacement dans la liste ou, si vous avez de nombreux emplacements définis, entrez le nom de la ville dans la zone de recherche, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="7c1c1-127">Après avoir choisi le numéro de téléphone et l'adresse de secours, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7c1c1-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span><span class="sxs-lookup"><span data-stu-id="7c1c1-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="7c1c1-131">Changer le numéro de téléphone d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7c1c1-131">Change a phone number for a user</span></span>
 
<span data-ttu-id="7c1c1-132">![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="7c1c1-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="7c1c1-133">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7c1c1-134">Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-134">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="7c1c1-135">Dans le volet de navigation de gauche, cliquez sur**utilisateurs**vocaux **vocaux** > .</span><span class="sxs-lookup"><span data-stu-id="7c1c1-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="7c1c1-136">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs pour lesquels vous souhaitez changer le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="7c1c1-137">Dans le volet action, sous **numéro attribué**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="7c1c1-138">Sur la page **Attribuer un numéro**, cliquez sur **Changer le numéro**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="7c1c1-139">Sur la page **Attribuer un numéro**, dans le menu **Sélectionner le numéro à attribuer**, sélectionnez le nouveau numéro de téléphone dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="7c1c1-140">Pour modifier l’adresse de secours associée, cliquez sur **changer l’emplacement**, puis sous **changer l’adresse de secours en**, sélectionnez l’emplacement dans la liste ou, si vous avez de nombreux emplacements définis, entrez le nom de la ville dans la zone de recherche, puis cliquez sur **Recherchez**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="7c1c1-141">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="7c1c1-142">Supprimer le numéro de téléphone d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7c1c1-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="7c1c1-143">![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="7c1c1-143">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="7c1c1-144">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7c1c1-145">Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-145">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="7c1c1-146">Dans le volet de navigation de gauche, cliquez sur**utilisateurs**vocaux **vocaux** > .</span><span class="sxs-lookup"><span data-stu-id="7c1c1-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="7c1c1-147">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs dont vous souhaitez supprimer le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="7c1c1-148">Dans le volet action, sous **numéro attribué**, cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="7c1c1-149">Dans la page **Supprimer le numéro sélectionné attribué ?**, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7c1c1-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="7c1c1-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c1c1-150">Related topics</span></span>
[<span data-ttu-id="7c1c1-151">Qu’est-ce que la validation d’adresse ?</span><span class="sxs-lookup"><span data-stu-id="7c1c1-151">What is address validation?</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[<span data-ttu-id="7c1c1-152">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="7c1c1-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="7c1c1-153">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="7c1c1-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="7c1c1-154">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="7c1c1-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 