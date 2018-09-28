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
search.appverid: MET150
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
description: 'Découvrez comment changer l’adresse et le numéro de téléphone d’urgence d’un utilisateur pour qu’ils fonctionnent avec le réseau téléphone commuté public (RTCP) aux États-Unis et en Europe. '
ms.openlocfilehash: e27ea228972ceead0838cff481a0db983c503b02
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347100"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="a4491-103">Modification de l'adresse d'urgence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a4491-103">Change the emergency address for a user</span></span>

<span data-ttu-id="a4491-104">Lorsque vous configurez des Forfaits d’appels dans Office 365, vous devez affecter une adresse d’urgence à chaque numéro de téléphone ou à chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a4491-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="a4491-105">En Europe, l’adresse d’urgence est associée au numéro de téléphone lorsque vous l’obtenez à partir d’Office 365, ou lorsque vous transférez un numéro de téléphone vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4491-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="a4491-106">Aux États-Unis, l’adresse d’urgence est associée au numéro de téléphone lorsqu’il est assigné à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a4491-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="a4491-107">L’adresse d’urgence peut être modifiée si l’utilisateur à qui elle est attribuée se déplace vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="a4491-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="a4491-108">Pour plus d’informations sur les adresses d’urgence et les emplacements, voir [Quels sont les emplacements d’urgence, les adresses et le routage des appels ?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="a4491-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span></span>
  
<span data-ttu-id="a4491-109">Pour savoir comment obtenir des Forfaits d’appels dans Office 365 et leur coût, consultez la rubrique [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a4491-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="a4491-110">Modification de l'adresse d'urgence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a4491-110">Change the emergency address for a user</span></span>

<span data-ttu-id="a4491-111">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="a4491-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a4491-112">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="a4491-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a4491-113">Accédez aux **équipes de Microsoft et Skype pour le centre d’administration Business** > **portail hérité**.</span><span class="sxs-lookup"><span data-stu-id="a4491-113">Go to the **Microsoft Teams and Skype for Business Admin Center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="a4491-114">Dans la navigation de gauche, accédez à la **voix** > **utilisateurs Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="a4491-114">In the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a4491-115">Vous permet de voir l’option de **voix** dans le volet de navigation gauche dans le Skype entreprise centre d’administration, vous devez d’abord acheter une licence de module complémentaire de **Conférence Audio** , une licence de module complémentaire **Système téléphonique** ou au moins une **licence Enterprise E5**.</span><span class="sxs-lookup"><span data-stu-id="a4491-115">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="a4491-116">Dans la page **Utilisateurs Voix**, cherchez et sélectionnez le ou les utilisateurs pour lesquels vous souhaitez modifier l'adresse de secours.</span><span class="sxs-lookup"><span data-stu-id="a4491-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="a4491-117">Dans le volet Action, sous **Emplacement d'urgence**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a4491-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="a4491-118">Dans la page **Attribuer un numéro**, cliquez sur **Changer l'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="a4491-118">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="a4491-119">Sous **Modifier l’adresse d’urgence à**, entrez le nom de la ville dans la zone, cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="a4491-119">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a4491-120">Vous pouvez modifier une adresse de secours à condition qu'elle ait été validée.</span><span class="sxs-lookup"><span data-stu-id="a4491-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="a4491-121">Pour modifier une adresse d’urgence qui n’a pas été validée, supprimer et en créer une autre adresse en cas d’urgence.</span><span class="sxs-lookup"><span data-stu-id="a4491-121">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
8. <span data-ttu-id="a4491-122">Sélectionnez une nouvelle adresse d’urgence dans la liste, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a4491-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a4491-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a4491-123">Related topics</span></span>
[<span data-ttu-id="a4491-124">Ajout ou suppression d'une adresse d'urgence pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a4491-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="a4491-125">Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence</span><span class="sxs-lookup"><span data-stu-id="a4491-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="a4491-126">Qu’est-ce que la validation d’adresse ?</span><span class="sxs-lookup"><span data-stu-id="a4491-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="a4491-127">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="a4491-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a4491-128">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="a4491-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a4491-129">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a4491-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 