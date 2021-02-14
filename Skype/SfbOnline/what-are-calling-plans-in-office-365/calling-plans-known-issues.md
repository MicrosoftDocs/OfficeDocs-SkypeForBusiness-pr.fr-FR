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
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Découvrez les problèmes connus concernant le plan d’appel pour les appels PSTN et ce que vous pouvez faire à leur sujet.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220734"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="0ed01-103">Problèmes connus relatifs aux forfaits d’appel</span><span class="sxs-lookup"><span data-stu-id="0ed01-103">Calling Plans known issues</span></span>

<span data-ttu-id="0ed01-p101">Les forfaits d’appels sont une nouvelle fonctionnalité de Skype Entreprise Online. Voici les problèmes actuels qui font l’objet d’un suivi et font l’objet de recherches actives. Ils seront potentiellement résolus lorsque la fonctionnalité sera mise à jour dans les prochaines builds.</span><span class="sxs-lookup"><span data-stu-id="0ed01-p101">Calling Plans are a new feature found in Skype for Business Online. The following are current issues that are being tracked and actively investigated. They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="0ed01-107">Problèmes connus relatifs aux forfaits d’appel</span><span class="sxs-lookup"><span data-stu-id="0ed01-107">Calling Plans known issues</span></span>

|<span data-ttu-id="0ed01-108">**Problème connu**</span><span class="sxs-lookup"><span data-stu-id="0ed01-108">**Known issue**</span></span>|<span data-ttu-id="0ed01-109">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="0ed01-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0ed01-110">La transition des licences Tech Preview aux licences de production pour les plans d’appels ne met pas automatiquement à jour la licence.</span><span class="sxs-lookup"><span data-stu-id="0ed01-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="0ed01-111">Commencez par acheter vos nouvelles licences afin qu'elles soient prêtes pour être affectées à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0ed01-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="0ed01-112">Supprimez la licence de promotion (Tech  Preview) d’un utilisateur,  puis affectez IMMÉDIATEment les nouvelles licences Plan d’appels nationaux et/ou Plan d’appels nationaux et internationaux à l’utilisateur. </span><span class="sxs-lookup"><span data-stu-id="0ed01-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="0ed01-113">Si vous supprimez et ajoutez des licences pour plusieurs utilisateurs, il est très important de supprimer les licences de tous les utilisateurs à l'aide de Windows PowerShell, puis de leur affecter **IMMÉDIATEMENT** les nouvelles licences en utilisant là encore Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ed01-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="0ed01-114">Ainsi, vous vous assurerez qu’il n’y a aucune interruption de service lorsque vous traitez un grand nombre d’attributions de licences utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ed01-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="0ed01-115">Pour obtenir des exemples de scripts PowerShell, [consultez Affecter des licences Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)Entreprise et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ed01-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="0ed01-116">**Remarque :** Si vous utilisez la connectivité RSTN sur site  pour des utilisateurs hybrides, il vous suffit d’affecter une licence **Phone System.**</span><span class="sxs-lookup"><span data-stu-id="0ed01-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="0ed01-117">Vous ne devez **PAS** non plus affecter de plan d’appel vocal.</span><span class="sxs-lookup"><span data-stu-id="0ed01-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="0ed01-118">Toutefois, si vous activez les forfaits d’appels dans Microsoft 365 ou Office 365 pour les  utilisateurs qui  utilisent Microsoft 365 ou Office 365, vous devez encore affecter une licence Plan d’appels nationaux et internationaux à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0ed01-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="0ed01-119">Consultez [Attribuer des licences Skype Entreprise et Microsoft Teams.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="0ed01-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0ed01-120">Si vous devez obtenir plus de numéros de téléphone, contactez le support technique pour les [produits pour les entreprises - Aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="0ed01-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="0ed01-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0ed01-121">Related topics</span></span>
[<span data-ttu-id="0ed01-122">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="0ed01-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="0ed01-123">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="0ed01-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="0ed01-124">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="0ed01-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="0ed01-125">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="0ed01-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="0ed01-126">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0ed01-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
