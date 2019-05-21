---
title: Définir votre code confidentiel pour transférer des numéros vers un nouveau fournisseur de service
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
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
description: To transfer or port out phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN. After you set the PIN, you need to include it when you request to port a phone number out.
ms.openlocfilehash: 64eaa010939c10a25e7c1fb4c53672a27296ebe1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290851"
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="fcfd1-104">Définir votre code confidentiel pour transférer des numéros vers un nouveau fournisseur de service</span><span class="sxs-lookup"><span data-stu-id="fcfd1-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="fcfd1-p102">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN. After you set the PIN, you need to include it when you request to port a phone number out.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-p102">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN. After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fcfd1-107">Un code confidentiel de transfert est utilisé uniquement pour les organisations aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="fcfd1-108">Pour plus d’informations sur le transfert et portage des numéros de téléphone d’entrée/sortie, voir [Transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-108">See [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="fcfd1-109">Voici quelques informations spécifiques sur ce code confidentiel que vous devez connaître :</span><span class="sxs-lookup"><span data-stu-id="fcfd1-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="fcfd1-110">Si un code confidentiel n’est pas défini, vous ne pourrez pas transférer ou extraire des numéros de téléphone depuis Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="fcfd1-111">Il peut contenir 6 à 10 chiffres (numéros).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="fcfd1-112">Il ne peut pas contenir de lettres ou de caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="fcfd1-113">Le code confidentiel par défaut est vide, mais si vous en insérez un, vous ne pouvez pas le supprimer ou le rétablir.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="fcfd1-114">Vous pouvez mettre à jour ou modifier le code confidentiel après en avoir inséré un.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="fcfd1-115">Configurez votre code confidentiel</span><span class="sxs-lookup"><span data-stu-id="fcfd1-115">Set up your PIN</span></span>

<span data-ttu-id="fcfd1-116">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="fcfd1-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="fcfd1-117">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="fcfd1-118">Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-118">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="fcfd1-119">Dans le volet de navigation de gauche, sélectionnez**commandes de port** **vocal** > .</span><span class="sxs-lookup"><span data-stu-id="fcfd1-119">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="fcfd1-120">Cliquez sur **Installer et gérer le code confidentiel** qui est utilisé pour le transfert ou le portage des numéros vers un autre fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-120">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="fcfd1-121">Dans le panneau**Définir ou modifier votre code confidentiel de transfert**, entrez votre code confidentiel et cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-121">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="fcfd1-122">Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="fcfd1-122">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fcfd1-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fcfd1-123">Related topics</span></span>
[<span data-ttu-id="fcfd1-124">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="fcfd1-124">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="fcfd1-125">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="fcfd1-125">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="fcfd1-126">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="fcfd1-126">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="fcfd1-127">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="fcfd1-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="fcfd1-128">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fcfd1-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
  

