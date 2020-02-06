---
title: Gestion des stratégies de conférence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Résumé : Découvrez comment gérer les stratégies de conférence dans Skype entreprise Server.'
ms.openlocfilehash: fc069093b9cc7cf5ce0e1e1f1efc0ee9e18e335d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818645"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="64c70-103">Gestion des stratégies de conférence dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="64c70-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="64c70-104">**Résumé :** Apprenez à gérer les stratégies de conférence dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="64c70-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="64c70-105">Cette rubrique décrit comment gérer les stratégies de conférence.</span><span class="sxs-lookup"><span data-stu-id="64c70-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="64c70-106">Pour plus d’informations sur la planification et le déploiement de conférences, voir [planifier les conférences dans Skype entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) et [déployer des conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="64c70-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="64c70-p102">Les stratégies de conférence vous permettent de définir une grande variété d’options de planification et de participation, allant de la possibilité d’inclure la fonction IP audio et vidéo dans une réunion à la détermination du nombre maximal de participants. Vous pouvez utiliser les stratégies de conférence pour gérer la sécurité, la bande passante et les aspects juridiques des réunions.</span><span class="sxs-lookup"><span data-stu-id="64c70-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="64c70-109">Vous pouvez définir une stratégie de conférence sur trois niveaux : étendue globale, étendue de site et étendue d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64c70-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="64c70-110">Les paramètres s’appliquent à un utilisateur spécifique de l’étendue la plus étroite à la plus large.</span><span class="sxs-lookup"><span data-stu-id="64c70-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="64c70-111">Si vous affectez une stratégie à un utilisateur, les paramètres de cette stratégie prévalent.</span><span class="sxs-lookup"><span data-stu-id="64c70-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="64c70-112">Si vous n’affectez pas une stratégie utilisateur à un utilisateur, les paramètres de la stratégie par site s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="64c70-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="64c70-113">Si vous n’appliquez aucune stratégie par utilisateur ou par site, la stratégie globale fournit les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="64c70-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="64c70-114">Une stratégie globale existe par défaut, par conséquent vous ne pouvez pas en créer une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="64c70-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="64c70-115">Vous ne pouvez pas non plus supprimer la stratégie globale existante, mais vous pouvez modifier la stratégie globale existante pour personnaliser les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="64c70-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="64c70-116">Gestion des stratégies de conférence à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="64c70-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="64c70-117">Pour gérer les stratégies de conférence à l’aide du panneau de configuration Skype entreprise Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="64c70-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="64c70-118">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="64c70-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="64c70-119">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="64c70-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="64c70-120">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="64c70-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="64c70-121">Gestion des stratégies de conférence à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64c70-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="64c70-122">Pour gérer les réunions à l’aide de Skype entreprise Server Management Shell, utilisez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="64c70-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="64c70-123">**Paramètres de stratégie de conférence**</span><span class="sxs-lookup"><span data-stu-id="64c70-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="64c70-124">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="64c70-124">**Cmdlet**</span></span>|<span data-ttu-id="64c70-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="64c70-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="64c70-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="64c70-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="64c70-127">Renvoie des informations sur les stratégies de conférence qui ont été configurées pour être utilisées dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="64c70-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="64c70-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="64c70-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="64c70-129">Affecte une stratégie de conférence au niveau de l’étendue Utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64c70-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="64c70-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="64c70-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="64c70-131">Crée une stratégie de conférence pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="64c70-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="64c70-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="64c70-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="64c70-133">Supprime la stratégie de conférence spécifiée.</span><span class="sxs-lookup"><span data-stu-id="64c70-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="64c70-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="64c70-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="64c70-135">Modifie une stratégie de conférence existante.</span><span class="sxs-lookup"><span data-stu-id="64c70-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

