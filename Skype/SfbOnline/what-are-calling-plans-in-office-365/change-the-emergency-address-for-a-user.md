---
title: Modification de l'adresse d'urgence d'un utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 5412636c-ad0e-48a5-b199-5925156abee4
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
description: 'Découvrez comment changer l’adresse et le numéro de téléphone d’urgence d’un utilisateur pour qu’ils fonctionnent avec le réseau téléphone commuté public (RTCP) aux États-Unis et en Europe. '
ms.openlocfilehash: 62deeae8624ad0eb6b85c25a39c475b0d1d0b198
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779044"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="78c19-103">Modification de l’adresse d’urgence d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="78c19-103">Change the emergency address for a user</span></span>

<span data-ttu-id="78c19-104">Lorsque vous configurez des Forfaits d’appels dans Office 365, vous devez affecter une adresse d’urgence à chaque numéro de téléphone ou à chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="78c19-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="78c19-105">En Europe, l’adresse d’urgence est associée au numéro de téléphone lorsque vous l’obtenez à partir d’Office 365, ou lorsque vous transférez un numéro de téléphone vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="78c19-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="78c19-106">Aux États-Unis, l’adresse d’urgence est associée au numéro de téléphone lorsqu’il est assigné à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="78c19-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="78c19-107">L’adresse d’urgence peut être modifiée si l’utilisateur à qui elle est attribuée se déplace vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="78c19-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="78c19-108">Pour plus d’informations sur les adresses d’urgence et les emplacements d’urgence, reportez-vous à la rubrique [Que sont les emplacements, les adresses et le routage des appels d’urgence ?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="78c19-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for details.</span></span>
  
<span data-ttu-id="78c19-109">Pour savoir comment obtenir des Forfaits d’appels dans Office 365 et leur coût, consultez la rubrique [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="78c19-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="78c19-110">Modification de l’adresse d’urgence d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="78c19-110">Change the emergency address for a user</span></span>

<span data-ttu-id="78c19-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d’administration de Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="78c19-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="78c19-112">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="78c19-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="78c19-113">|||UNTRANSLATED_CONTENT_START|||Go to the **Office 365 admin center** > **Skype for Business**.|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="78c19-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="78c19-114">Dans le volet de navigation de gauche, sélectionnez **Voix** > **Utilisateurs Voix**.</span><span class="sxs-lookup"><span data-stu-id="78c19-114">In the Skype for Business admin center, in the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78c19-115">Pour que l’option **Voix** apparaisse dans le volet de navigation gauche du Centre d’administration Skype Entreprise, vous devez d’abord acheter au moins une **licence Entreprise E5**, une licence de complément **Système téléphonique**, ou une licence de complément **Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="78c19-115">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="78c19-116">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs pour lesquels vous souhaitez modifier l’adresse d’urgence.</span><span class="sxs-lookup"><span data-stu-id="78c19-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="78c19-117">Dans le volet Action, sous **Emplacement d'urgence**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="78c19-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="78c19-118">Dans la page **Attribuer un numéro**, cliquez sur **Changer l’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="78c19-118">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="78c19-119">Sous **Remplacer l’adresse d’urgence**, saisissez le nom de la ville dans le champ et cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="78c19-119">Under **Change emergency address to** put the name of the city in the Find City box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78c19-120">Vous pouvez modifier une adresse de secours à condition qu’elle ait été validée.</span><span class="sxs-lookup"><span data-stu-id="78c19-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="78c19-121">Pour modifier une adresse d’urgence qui n’a pas été validée, supprimez-la, puis créez une autre adresse d’urgence.</span><span class="sxs-lookup"><span data-stu-id="78c19-121">To change an emergency address that hasn't been validated, delete it and recreate another emergency address.</span></span> 
  
8. <span data-ttu-id="78c19-122">Sélectionnez une nouvelle adresse d’urgence dans la liste, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="78c19-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="78c19-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="78c19-123">Related topics</span></span>
[<span data-ttu-id="78c19-124">Ajout ou suppression d'une adresse d'urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="78c19-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="78c19-125">Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence</span><span class="sxs-lookup"><span data-stu-id="78c19-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="78c19-126">Qu’est-ce que la validation d’adresse ?</span><span class="sxs-lookup"><span data-stu-id="78c19-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="78c19-127">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="78c19-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="78c19-128">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="78c19-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="78c19-129">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="78c19-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 