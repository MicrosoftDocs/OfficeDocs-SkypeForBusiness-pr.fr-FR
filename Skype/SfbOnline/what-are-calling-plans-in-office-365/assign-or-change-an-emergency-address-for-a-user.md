---
title: Affectation ou modification d'une adresse d'urgence pour un utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 1411b594-1e88-44c9-9f60-2202f9bb8553
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
description: Découvrez comment configurer une adresse et un numéro de téléphone d’urgence pour chacun de vos utilisateurs qui fonctionne avec les publics téléphone réseau commuté (RTCP).
ms.openlocfilehash: 884dd4051ef15cb29d6ab125989edf990980f722
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299533"
---
# <a name="assign-or-change-an-emergency-address-for-a-user"></a><span data-ttu-id="a3ee2-103">Affectation ou modification d'une adresse d'urgence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a3ee2-103">Assign or change an emergency address for a user</span></span>

<span data-ttu-id="a3ee2-104">Lorsque vous configurez des Forfaits d’appels dans Office 365, vous devez affecter une adresse d’urgence à chaque numéro de téléphone ou à chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="a3ee2-105">En Europe, l’adresse d’urgence est associée au numéro de téléphone lorsque vous l’obtenez à partir d’Office 365, ou lorsque vous transférez un numéro de téléphone vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="a3ee2-106">Aux États-Unis, l’adresse d’urgence est associée au numéro de téléphone lorsqu’il est assigné à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="a3ee2-107">L’adresse d’urgence peut être modifiée si l’utilisateur à qui elle est attribuée se déplace vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="a3ee2-108">Pour en savoir plus sur les adresses de secours et les emplacements d’urgence, voir [que sont les emplacements d’urgence, les adresses de secours et le routage des appels?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="a3ee2-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span></span>
  
<span data-ttu-id="a3ee2-109">Pour savoir comment obtenir des Forfaits d’appels dans Office 365 et leur coût, consultez la rubrique [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a3ee2-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="assign-or-change-an-emergency-address"></a><span data-ttu-id="a3ee2-110">Affecter ou modifier une adresse d'urgence</span><span class="sxs-lookup"><span data-stu-id="a3ee2-110">Assign or change an emergency address</span></span>

1. <span data-ttu-id="a3ee2-111">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a3ee2-112">Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-112">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="a3ee2-113">Dans le volet de navigation de gauche, sélectionnez **voix**, puis cliquez sur **utilisateurs voix**.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-113">In the left navigation go to **Voice**, then click **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3ee2-114">Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration de Skype entreprise, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="a3ee2-114">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="a3ee2-115">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs pour lesquels vous souhaitez modifier l'adresse de secours.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-115">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="a3ee2-116">Dans le volet Action, sous **Emplacement d'urgence**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3ee2-117">Vous pouvez modifier une adresse de secours à condition qu'elle ait été validée.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-117">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="a3ee2-118">Pour modifier une adresse de secours qui n’a pas été validée, supprimez-la et créez une autre adresse de secours.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-118">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
6. <span data-ttu-id="a3ee2-119">Dans la page **Attribuer un numéro**, cliquez sur **Changer l'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-119">On the **Assign number** page, click **Change location**.</span></span>
    
7. <span data-ttu-id="a3ee2-120">Sous **changer l’adresse de secours en**, entrez le nom de la ville et cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-120">Under **Change emergency address to**, enter the name of the city and click **Search**.</span></span>
    
8. <span data-ttu-id="a3ee2-121">Dans la liste déroulante adresse, sélectionnez l’adresse de secours, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a3ee2-121">Select the emergency address from the address drop-down list, and then click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="a3ee2-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3ee2-122">Related topics</span></span>
## <a name="related-topics"></a><span data-ttu-id="a3ee2-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3ee2-123">Related topics</span></span>
[<span data-ttu-id="a3ee2-124">Ajouter, modifier ou supprimer une adresse d’urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a3ee2-124">Add, change, or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="a3ee2-125">Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a3ee2-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="a3ee2-126">Qu’est-ce que la validation d’adresse ?</span><span class="sxs-lookup"><span data-stu-id="a3ee2-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="a3ee2-127">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="a3ee2-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a3ee2-128">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="a3ee2-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a3ee2-129">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a3ee2-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 