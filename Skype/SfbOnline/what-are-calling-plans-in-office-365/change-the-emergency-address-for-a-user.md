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
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'See steps on how to change the emergency address for a user to work with the Public Switched Telephone Network (PSTN) in the US and Europe. '
ms.openlocfilehash: fc5976a2701b174ecbfcbcbb32f278debe7c68f2
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="fec3b-103">Modification de l'adresse d'urgence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="fec3b-103">Change the emergency address for a user</span></span>

<span data-ttu-id="fec3b-104">Lorsque vous configurez l’appel de Plans dans Office 365, vous devez attribuer une adresse d’urgence à chaque numéro de téléphone ou d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fec3b-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="fec3b-105">Dans les pays européens, l’adresse d’urgence est associé au numéro de téléphone lorsque vous le récupérez à partir d’Office 365, ou lorsque vous transférez un numéro de téléphone sur vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="fec3b-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="fec3b-106">Aux États-Unis, l’adresse d’urgence est associé au numéro de téléphone lorsqu’il est assigné à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fec3b-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="fec3b-107">L’adresse d’urgence peut être modifiée si l’utilisateur qu’il est affecté à se déplace vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="fec3b-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="fec3b-108">Pour plus d’informations sur les emplacements et les adresses d’urgence, consultez [Quels sont les emplacements en cas d’urgence, des adresses et le routage des appels ?](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="fec3b-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](what-are-emergency-locations-addresses-and-call-routing.md)</span></span>
  
<span data-ttu-id="fec3b-109">Pour savoir comment obtenir des Plans d’appel dans Office 365 et leur coût, consultez [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="fec3b-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="fec3b-110">Modification de l'adresse d'urgence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="fec3b-110">Change the emergency address for a user</span></span>

1. <span data-ttu-id="fec3b-111">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="fec3b-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="fec3b-112">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="fec3b-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="fec3b-113">Dans la navigation de gauche, accédez à **voix** > **utilisateurs de voix**.</span><span class="sxs-lookup"><span data-stu-id="fec3b-113">In the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fec3b-114">Pour pouvoir voir l’option **voix** dans la navigation de gauche dans le Skype pour le centre d’administration métier, vous devez d’abord acheter au moins une **licence d’entreprise E5**, une licence de module complémentaire de **Système téléphonique** ou une licence de module complémentaire **d’Audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="fec3b-114">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="fec3b-115">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs pour lesquels vous souhaitez modifier l'adresse de secours.</span><span class="sxs-lookup"><span data-stu-id="fec3b-115">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="fec3b-116">Dans le volet Action, sous **Emplacement d'urgence**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fec3b-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="fec3b-117">Dans la page **Attribuer un numéro**, cliquez sur **Changer l'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="fec3b-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="fec3b-118">Sous **Modifier l’adresse d’urgence à**, entrez le nom de la ville dans la zone et cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="fec3b-118">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fec3b-119">Vous pouvez modifier une adresse de secours à condition qu'elle ait été validée.</span><span class="sxs-lookup"><span data-stu-id="fec3b-119">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="fec3b-120">Pour modifier une adresse d’urgence qui n’a pas encore été validée, supprimer et en créer une autre adresse en cas d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fec3b-120">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
8. <span data-ttu-id="fec3b-121">Sélectionnez une nouvelle adresse d’urgence dans la liste, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fec3b-121">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fec3b-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fec3b-122">Related topics</span></span>
[<span data-ttu-id="fec3b-123">Ajout ou suppression d'une adresse d'urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="fec3b-123">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="fec3b-124">Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence</span><span class="sxs-lookup"><span data-stu-id="fec3b-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="fec3b-125">Qu’est-ce que la validation d’adresse ?</span><span class="sxs-lookup"><span data-stu-id="fec3b-125">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="fec3b-126">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="fec3b-126">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="fec3b-127">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="fec3b-127">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="fec3b-128">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fec3b-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 