---
title: Problèmes connus relatifs aux forfaits d’appel
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 9a6f97a93aa6c7b4e847ba1cb3280a21c473db0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299523"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="24a9f-103">Problèmes connus relatifs aux forfaits d’appel</span><span class="sxs-lookup"><span data-stu-id="24a9f-103">Calling Plans known issues</span></span>

<span data-ttu-id="24a9f-104">Les forfaits d’appels dans Office 365 sont une nouvelle fonctionnalité de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="24a9f-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="24a9f-105">Vous trouverez ci-après les problèmes actuellement suivis et examinés activement.</span><span class="sxs-lookup"><span data-stu-id="24a9f-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="24a9f-106">Ils seront potentiellement résolus lorsque la fonctionnalité sera mise à jour dans les versions ultérieures d’Office 365 et de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="24a9f-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="24a9f-107">Problèmes connus relatifs aux forfaits d’appel</span><span class="sxs-lookup"><span data-stu-id="24a9f-107">Calling Plans known issues</span></span>

|<span data-ttu-id="24a9f-108">**Problème connu**</span><span class="sxs-lookup"><span data-stu-id="24a9f-108">**Known issue**</span></span>|<span data-ttu-id="24a9f-109">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="24a9f-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="24a9f-110">La transition des licences Tech Preview aux licences de production pour les offres d’appels ne met pas automatiquement à jour la licence.</span><span class="sxs-lookup"><span data-stu-id="24a9f-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="24a9f-111">Commencez par acheter vos nouvelles licences afin qu'elles soient prêtes pour être affectées à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="24a9f-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="24a9f-112">Supprimez la licence promotion (Technical Preview) d’un utilisateur, puis affectez **immédiatement** le nouveau **plan d’appels nationaux** et/ou les licences de **plan d’appels nationaux et internationaux** à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24a9f-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="24a9f-113">Si vous supprimez et ajoutez des licences pour plusieurs utilisateurs, il est très important de supprimer les licences de tous les utilisateurs à l'aide de Windows PowerShell, puis de leur affecter **IMMÉDIATEMENT** les nouvelles licences en utilisant là encore Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24a9f-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="24a9f-114">Ainsi, vous garantirez qu’il n’y a aucune perturbation en service lors de la gestion d’un grand nombre d’attributions de licences utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24a9f-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="24a9f-115">Pour obtenir des exemples de scripts PowerShell, consultez la rubrique [affectation de licences Skype entreprise et Microsoft teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="24a9f-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="24a9f-116">**Remarque:** Si vous utilisez une connectivité PSTN locale pour les utilisateurs hybrides, il \*\* vous suffit d’affecter une licence de **système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="24a9f-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="24a9f-117">Vous ne devez **pas non** plus affecter de plan d’appels vocaux.</span><span class="sxs-lookup"><span data-stu-id="24a9f-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="24a9f-118">Toutefois, si vous activez les offres d’appels dans Office 365 pour les utilisateurs qui se trouvent dans Office 365, vous devez quand même affecter une licence de **plan** d’appel **national** ou international pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="24a9f-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="24a9f-119">Consultez la rubrique [affectation de licences Skype entreprise et Microsoft teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="24a9f-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="24a9f-120">Si vous avez besoin d’obtenir plus de numéros de téléphone, [Contactez le support technique pour les produits pour les entreprises-aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="24a9f-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="24a9f-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="24a9f-121">Related topics</span></span>
[<span data-ttu-id="24a9f-122">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="24a9f-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="24a9f-123">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="24a9f-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="24a9f-124">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="24a9f-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="24a9f-125">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="24a9f-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="24a9f-126">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="24a9f-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 