---
title: Problèmes connus des Plans d’appel
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: c4e3834960439fb09c58ece2bf9e39e2756419e7
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="63540-103">Problèmes connus des Plans d’appel</span><span class="sxs-lookup"><span data-stu-id="63540-103">Calling Plans known issues</span></span>

<span data-ttu-id="63540-104">Plans d’appel dans Office 365 sont une nouvelle fonctionnalité trouvée dans Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="63540-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="63540-105">Les éléments suivants sont des problèmes actuels qui sont suivies et activement examinée.</span><span class="sxs-lookup"><span data-stu-id="63540-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="63540-106">Ils seront résolus potentiellement lorsque la fonction est mis à jour dans les versions futures dans Office 365 et Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="63540-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="63540-107">Problèmes connus des Plans d’appel</span><span class="sxs-lookup"><span data-stu-id="63540-107">Calling Plans known issues</span></span>

|<span data-ttu-id="63540-108">**Problème connu**</span><span class="sxs-lookup"><span data-stu-id="63540-108">**Known issue**</span></span>|<span data-ttu-id="63540-109">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="63540-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63540-110">Transition à partir de Tech Preview des licences pour les licences de production pour les Plans d’appel de ne pas mettre à jour automatiquement la licence.</span><span class="sxs-lookup"><span data-stu-id="63540-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="63540-111">Commencez par acheter vos nouvelles licences afin qu'elles soient prêtes pour être affectées à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="63540-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="63540-112">Supprimer la licence de promotion (Tech Preview) d’un utilisateur, et d’affecter **immédiatement** les nouvelles licences **Intérieures appelant Plan** et/ou **national et International appel de planifier** à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="63540-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="63540-113">Si vous supprimez et ajoutez des licences pour plusieurs utilisateurs, il est très important de supprimer les licences de tous les utilisateurs à l'aide de Windows PowerShell, puis de leur affecter **IMMÉDIATEMENT** les nouvelles licences en utilisant là encore Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63540-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="63540-114">Cela permet de garantir qu’il n’y a aucune interruption de service lors de la gestion des volumes importants d’attributions de licence d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="63540-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="63540-115">Pour des exemples de scripts PowerShell, consultez [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="63540-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="63540-116">**Remarque :** Si vous utilisez la connectivité RTPC sur site pour les utilisateurs de hybride, vous *seulement* devez attribuer une licence de **Système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="63540-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="63540-117">Il ne doit **pas** également attribuer une voix à l’appel de Plan.</span><span class="sxs-lookup"><span data-stu-id="63540-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="63540-118">Toutefois, si vous activez l’appel de Plans dans Office 365 pour les utilisateurs qui se trouvent dans Office 365, vous devez toujours assigner un **Intérieur appel de planifier** ou une licence **national et International appelant planifier** pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="63540-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="63540-119">Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="63540-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="63540-120">Si vous avez besoin obtenir des numéros de téléphone supplémentaires que cela, veuillez [contacter le support technique pour les produits d’entreprise - aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="63540-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="63540-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="63540-121">Related topics</span></span>
[<span data-ttu-id="63540-122">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="63540-122">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="63540-123">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="63540-123">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="63540-124">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="63540-124">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="63540-125">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="63540-125">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="63540-126">Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="63540-126">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 