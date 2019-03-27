---
title: Gérer les stratégies de conférence de Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Résumé : Découvrez comment gérer les stratégies de conférence de Skype pour Business Server.'
ms.openlocfilehash: 96b2f5e27aa65931f5cd76499e1a3f66b817baa5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898143"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="2a3ac-103">Gérer les stratégies de conférence de Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="2a3ac-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="2a3ac-104">**Résumé :** Découvrez comment gérer les stratégies de conférence de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="2a3ac-105">Cette rubrique décrit comment gérer les stratégies de conférence.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="2a3ac-106">Pour plus d’informations sur la façon de planifier et déployer la conférence, voir [Plan pour la conférence dans Skype pour Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conférence dans Skype pour Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="2a3ac-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="2a3ac-p102">Les stratégies de conférence vous permettent de définir une grande variété d’options de planification et de participation, allant de la possibilité d’inclure la fonction IP audio et vidéo dans une réunion à la détermination du nombre maximal de participants. Vous pouvez utiliser les stratégies de conférence pour gérer la sécurité, la bande passante et les aspects juridiques des réunions.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="2a3ac-109">Vous pouvez définir une stratégie de conférence sur trois niveaux : étendue globale, étendue de site et étendue d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="2a3ac-110">Les paramètres s’appliquent à un utilisateur spécifique de l’étendue la plus étroite à la plus large.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="2a3ac-111">Si vous affectez une stratégie à un utilisateur, les paramètres de cette stratégie prévalent.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="2a3ac-112">Si vous n’affectez pas une stratégie utilisateur à un utilisateur, les paramètres de la stratégie par site s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="2a3ac-113">Si vous n’appliquez aucune stratégie par utilisateur ou par site, la stratégie globale fournit les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="2a3ac-114">Une stratégie globale existe par défaut, par conséquent vous ne pouvez pas en créer une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="2a3ac-115">Vous ne pouvez pas non plus supprimer la stratégie globale existante, mais vous pouvez modifier la stratégie globale existante pour personnaliser les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2a3ac-116">Gérer les stratégies de conférence à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="2a3ac-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="2a3ac-117">Pour gérer les stratégies de conférence à l’aide de Skype pour le panneau de configuration serveur Business :</span><span class="sxs-lookup"><span data-stu-id="2a3ac-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="2a3ac-118">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2a3ac-119">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2a3ac-120">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2a3ac-121">Gérer les stratégies de conférence à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="2a3ac-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2a3ac-122">Pour gérer des réunions à l’aide de Skype pour Business Server Management Shell, utilisez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="2a3ac-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="2a3ac-123">**Paramètres de stratégie de conférence**</span><span class="sxs-lookup"><span data-stu-id="2a3ac-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="2a3ac-124">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="2a3ac-124">**Cmdlet**</span></span>|<span data-ttu-id="2a3ac-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="2a3ac-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2a3ac-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="2a3ac-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="2a3ac-127">Renvoie des informations sur les stratégies de conférence qui ont été configurées pour être utilisées dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="2a3ac-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="2a3ac-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="2a3ac-129">Affecte une stratégie de conférence au niveau de l’étendue Utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="2a3ac-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="2a3ac-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="2a3ac-131">Crée une stratégie de conférence pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="2a3ac-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="2a3ac-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="2a3ac-133">Supprime la stratégie de conférence spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="2a3ac-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="2a3ac-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="2a3ac-135">Modifie une stratégie de conférence existante.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

