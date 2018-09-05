---
title: Attribuer, modifier ou supprimer le numéro de téléphone d’un utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: Découvrez comment attribuer, modifier ou supprimer le numéro de téléphone professionnel de vos utilisateurs Skype Entreprise pour que les entreprises et les clients extérieurs puissent appeler.
ms.openlocfilehash: 8c80bf9da5471f1a7293a01ed9e2d56f6e1aa15b
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780938"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="1a414-103">Attribuer, modifier ou supprimer le numéro de téléphone d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a414-103">Assign, change or remove a phone number for a user</span></span>

<span data-ttu-id="1a414-104">Lorsque vous configurez des Forfaits d’appel dans Office 365, vous assignez les numéros de téléphone à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1a414-104">When you set up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> 

<span data-ttu-id="1a414-105">Dans le client Microsoft Teams, le numéro de téléphone que vous assignez apparaît lorsqu’ils cliquent sur **Appels**.</span><span class="sxs-lookup"><span data-stu-id="1a414-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Le numéro de téléphone de l’utilisateur affiché dans Microsoft Teams.](../images/teams-phone-number.png)

<span data-ttu-id="1a414-107">Dans le client Skype Entreprise, le numéro de téléphone que vous assignez est répertorié dans le champ **Téléphone professionnel** et ne peut pas être modifié par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a414-107">The phone number you assign will be listed in the **This Work Phone** box in their Skype for Business client and can't be changed by a user.</span></span>
  
![Le numéro de téléphone professionnel est grisé.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="1a414-109">Si un utilisateur souhaite [Modifier son numéro de téléphone Skype Entreprise](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) et que le numéro de téléphone dans l’application Skype Entreprise ne peut pas être modifié ou est grisé, cela signifie que l’administrateur l’a configuré pour lui et qu’il ne peut pas le modifier.</span><span class="sxs-lookup"><span data-stu-id="1a414-109">If they want to [Change my phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) ** and the phone number in the Skype for Business app can't be changed or is grayed out**, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="1a414-110">Lorsque vous configurez des utilisateurs afin qu’ils puissent émettre et recevoir des appels téléphoniques, vous devez d’abord utiliser le Centre d'administration Skype Entreprise et affecter un numéro de téléphone, mais vous pouvez modifier ou supprimer le numéro de téléphone si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1a414-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="1a414-111">Pour savoir comment obtenir des Forfaits d’appels dans Office 365 et leur coût, consultez la rubrique [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="1a414-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a414-112">Vous pouvez savoir si un utilisateur possède une licence en accédant au **centre d’administration Skype Entreprise** > **Voix** > **Utilisateurs Voix** et en sélectionnant l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a414-112">One way to see if a user has a license assigned is in the **Skype for Business admin center** > **Voice** > **Voice users** and select the user.</span></span> <span data-ttu-id="1a414-113">Si une licence est affectée, elle apparaîtra sous **Licence affectée**.</span><span class="sxs-lookup"><span data-stu-id="1a414-113">If a license is assigned, it will be listed under the **Assigned license**.</span></span> <span data-ttu-id="1a414-114">Vous pouvez également utiliser le centre d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a414-114">You can use the Office 365 admin center though too.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="1a414-115">Attribution d'un numéro de téléphone à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a414-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="1a414-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d’administration de Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="1a414-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="1a414-117">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1a414-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a414-118">Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1a414-118">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="1a414-119">Dans le volet de navigation de gauche, sélectionnez **Voix** > **Utilisateurs Voix**.</span><span class="sxs-lookup"><span data-stu-id="1a414-119">In the left navigation, **Voice** > **Voice users**.</span></span>
   > [!NOTE]
 <span data-ttu-id="1a414-120">Pour que l’option **Voix** apparaisse dans le volet de navigation gauche du Centre d’administration Skype Entreprise, vous devez d’abord acheter au moins une **licence Entreprise E5**, une licence de complément **Système téléphonique**, ou une licence de complément **Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="1a414-120">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="1a414-121">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs auxquels vous souhaitez affecter un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="1a414-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="1a414-122">Dans le volet Action, cliquez sur **Affecter un numéro**.</span><span class="sxs-lookup"><span data-stu-id="1a414-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="1a414-123">Sur la page **Affecter un numéro**, dans la liste **Sélectionner le numéro à affecter**, sélectionnez le numéro de téléphone pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a414-123">On the **Assign number** page in the **Select number to assign** list, then select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="1a414-124">Si vous ne voyez pas de numéros de téléphone répertoriés, vous devez tout d’abord [Obtenir des numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="1a414-124">If you don't see any phone numbers listed, you need to go Getting Skype for Business phone numbers for your users first or If you use the Skype for Business admin center  Voice  Phone numbers page > click Add then New user numbers.</span></span> <span data-ttu-id="1a414-125">Ou, si vous utilisez le **centre d’administration Skype Entreprise** > **Voix** > page **Numéros de téléphone**, cliquez sur **Ajouter**, puis cliquez sur **Nouveaux numéros utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="1a414-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="1a414-126">Pour affecter ou modifier l’adresse d’urgence associée, sous **Sélectionner un emplacement d’urgence validé**, sélectionnez l'emplacement dans la liste ou, si de nombreux emplacements sont définis, entrez le nom de la ville dans la zone de recherche et cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="1a414-126">To assign or change the associated emergency address under Select validated emergency location, either select the location from the list or if you have many locations defined put the name of the city in the Search by city box and click Search.</span></span>
    
8. <span data-ttu-id="1a414-127">Après avoir choisi le numéro de téléphone et l'adresse de secours, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1a414-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1a414-128">En raison de la latence entre Office 365 et Skype Entreprise Online, l’activation des utilisateurs peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="1a414-128">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for user to be enabled.</span></span> <span data-ttu-id="1a414-129">Si le numéro de téléphone n’est toujours pas activé dans un délai de 24 heures, [Contactez le support pour les entreprises - Aide d’administration](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="1a414-129">If after 24 hours, the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="1a414-130">Nous sommes là pour vous aider !</span><span class="sxs-lookup"><span data-stu-id="1a414-130">We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="1a414-131">Changer le numéro de téléphone d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a414-131">To change a phone number for a user</span></span>
 
<span data-ttu-id="1a414-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d’administration de Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="1a414-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="1a414-133">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1a414-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a414-134">Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1a414-134">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="1a414-135">Dans le volet de navigation de gauche, sélectionnez **Voix** > **Utilisateurs Voix**.</span><span class="sxs-lookup"><span data-stu-id="1a414-135">In the left navigation, **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="1a414-136">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs pour lesquels vous souhaitez changer le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="1a414-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="1a414-137">Dans le volet Action, sous **Numéro attribué**, cliquez sur **Changer**.</span><span class="sxs-lookup"><span data-stu-id="1a414-137">In the Action pane, under **Assigned number** click **Change number**.</span></span> 
    
6. <span data-ttu-id="1a414-138">Sur la page **Attribuer un numéro**, cliquez sur **Changer le numéro**.</span><span class="sxs-lookup"><span data-stu-id="1a414-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="1a414-139">Sur la page **Attribuer un numéro**, dans le menu **Sélectionner le numéro à attribuer**, sélectionnez le nouveau numéro de téléphone dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="1a414-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="1a414-140">Pour changer l’adresse d’urgence associée, cliquez sur **Changer d’emplacement**, puis, sous **Remplacer l’adresse d'urgence par**, sélectionnez l’emplacement dans la liste ou, si de nombreux emplacements sont définis, entrez le nom de la ville dans la zone de recherche et cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="1a414-140">To change the associated emergency address click Change location and under Change emergency address to, either select the location from the list or if you have many locations defined put the name of the city in the Search by city box and click Search.</span></span>
    
9. <span data-ttu-id="1a414-141">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1a414-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="1a414-142">Supprimer le numéro de téléphone d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a414-142">To remove a phone number from a user</span></span>
 
<span data-ttu-id="1a414-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d’administration de Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="1a414-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="1a414-144">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1a414-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a414-145">Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1a414-145">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="1a414-146">Dans le volet de navigation de gauche, sélectionnez **Voix** > **Utilisateurs Voix**.</span><span class="sxs-lookup"><span data-stu-id="1a414-146">In the left navigation, **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="1a414-147">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs dont vous souhaitez supprimer le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="1a414-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="1a414-148">Dans le volet Action, sous **Attribuer un numéro**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1a414-148">In the Action pane, under **Assigned number** click **Remove**.</span></span> 
    
6. <span data-ttu-id="1a414-149">Dans la page **Supprimer le numéro sélectionné attribué ?**, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1a414-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="1a414-150">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="1a414-150">Related topics</span></span>
[<span data-ttu-id="1a414-151">Qu’est-ce que la validation d’adresse ?</span><span class="sxs-lookup"><span data-stu-id="1a414-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="1a414-152">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="1a414-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="1a414-153">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="1a414-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="1a414-154">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="1a414-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 