---
title: "Problèmes connus des Plans d’appel"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: "Découvrez les problèmes connus avec le programme appelant pour Office 365 (appel RTC) et que vous pouvez faire à leur sujet. "
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="0ab76-103">Problèmes connus des Plans d’appel</span><span class="sxs-lookup"><span data-stu-id="0ab76-103">Calling Plans known issues</span></span>

<span data-ttu-id="0ab76-104">Plans d’appel dans Office 365 sont une nouvelle fonctionnalité trouvée dans Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="0ab76-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="0ab76-105">Les éléments suivants sont des problèmes actuels qui sont suivies et activement examinée.</span><span class="sxs-lookup"><span data-stu-id="0ab76-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="0ab76-106">Ils seront résolus potentiellement lorsque la fonction est mis à jour dans les versions futures dans Office 365 et Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="0ab76-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="0ab76-107">Problèmes connus des Plans d’appel</span><span class="sxs-lookup"><span data-stu-id="0ab76-107">Calling Plans known issues</span></span>

|<span data-ttu-id="0ab76-108">**Problème connu**</span><span class="sxs-lookup"><span data-stu-id="0ab76-108">**Known issue**</span></span>|<span data-ttu-id="0ab76-109">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="0ab76-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0ab76-110">Transition à partir de Tech Preview des licences pour les licences de production pour les Plans d’appel de ne pas mettre à jour automatiquement la licence.</span><span class="sxs-lookup"><span data-stu-id="0ab76-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="0ab76-111">Achetez vos nouvelles licences tout d’abord afin qu’elles soient prêtes à affecter à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0ab76-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="0ab76-112">Supprimer la licence de promotion (Tech Preview) d’un utilisateur, et d’affecter **immédiatement** les nouvelles licences **Intérieures appelant Plan** et/ou **national et International appel de planifier** à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ab76-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="0ab76-113">Si vous êtes la suppression et l’ajout de licences pour plusieurs utilisateurs, il est extrêmement important que vous supprimez les licences de tous les utilisateurs à l’aide de Windows PowerShell et ensuite affecter **immédiatement** les licences pour tous les utilisateurs de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ab76-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="0ab76-114">Cela permet de garantir qu’il n’y a aucune interruption de service lors de la gestion des volumes importants d’attributions de licence d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ab76-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="0ab76-115">Pour des exemples de scripts PowerShell, consultez [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="0ab76-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="0ab76-116">**Remarque :** Si vous utilisez la connectivité RTPC sur site pour les utilisateurs de hybride, vous *seulement* devez attribuer une licence de **Système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="0ab76-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="0ab76-117">Il ne doit **pas** également attribuer une voix à l’appel de Plan.</span><span class="sxs-lookup"><span data-stu-id="0ab76-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="0ab76-118">Toutefois, si vous activez l’appel de Plans dans Office 365 pour les utilisateurs qui se trouvent dans Office 365, vous devez toujours assigner un **Intérieur appel de planifier** ou une licence **national et International appelant planifier** pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0ab76-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="0ab76-119">Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="0ab76-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0ab76-120">Si vous avez besoin obtenir des numéros de téléphone supplémentaires que cela, veuillez [contacter le support technique pour les produits d’entreprise - aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="0ab76-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="0ab76-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0ab76-121">Related topics</span></span>
[<span data-ttu-id="0ab76-122">Transfert de questions courantes des numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="0ab76-122">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="0ab76-123">Différents types de numéros de téléphone utilisés pour les Plans d’appel</span><span class="sxs-lookup"><span data-stu-id="0ab76-123">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="0ab76-124">Gérer les numéros de téléphone pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="0ab76-124">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="0ab76-125">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="0ab76-125">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="0ab76-126">Skype pour Business Online : étiquette de décharge de responsabilité d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="0ab76-126">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
