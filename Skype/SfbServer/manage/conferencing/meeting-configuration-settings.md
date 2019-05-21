---
title: Gérer les paramètres de configuration de la réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Résumé: Découvrez comment gérer les paramètres de configuration de la réunion dans Skype entreprise Server.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283738"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="065be-103">Gérer les paramètres de configuration de la réunion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="065be-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="065be-104">**Résumé:** Découvrez comment gérer les paramètres de configuration de la réunion dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="065be-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="065be-105">Cette rubrique décrit comment gérer les paramètres de configuration de réunion.</span><span class="sxs-lookup"><span data-stu-id="065be-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="065be-106">Pour plus d’informations sur la planification et le déploiement de conférences, voir [planifier les conférences dans Skype entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) et [déployer des conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="065be-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="065be-107">Les paramètres de configuration de réunion déterminent le type de réunion que les utilisateurs peuvent créer, en plus de contrôler la façon dont les utilisateurs anonymes et les conférences rendez-vous peuvent participer à ces réunions.</span><span class="sxs-lookup"><span data-stu-id="065be-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="065be-108">Notez que ces paramètres affectent uniquement les réunions planifiées; Il n’y a pas d’incidence sur les réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="065be-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="065be-109">Les paramètres de configuration de réunion définissent ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="065be-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="065be-110">si les appels émis à partir d’un du réseau téléphonique commuté (PSTN) sont transférés vers la salle d’attente ;</span><span class="sxs-lookup"><span data-stu-id="065be-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="065be-111">qui peut être présentateur ;</span><span class="sxs-lookup"><span data-stu-id="065be-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="065be-112">si le type de conférence est affecté par défaut ;</span><span class="sxs-lookup"><span data-stu-id="065be-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="065be-113">si les utilisateurs anonymes (non authentifiés) sont admis par défaut.</span><span class="sxs-lookup"><span data-stu-id="065be-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="065be-114">Vous pouvez définir les caractéristiques des réunions à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="065be-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="065be-115">Vous pouvez spécifier les paramètres de la réunion au niveau global (créé par défaut), au niveau du site ou au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="065be-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="065be-116">Par défaut, les paramètres globaux définissent l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="065be-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="065be-117">Si vous créez des paramètres au niveau du pool, ceux-ci s’appliquent à toutes les réunions hébergées par ce pool.</span><span class="sxs-lookup"><span data-stu-id="065be-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="065be-118">Si vous ne créez pas de paramètres au niveau du pool, les paramètres définis au niveau du site s’appliquent, s’ils existent.</span><span class="sxs-lookup"><span data-stu-id="065be-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="065be-119">Si aucun paramètre n’a été défini au niveau du site, les paramètres globaux s’appliquent à l’ensemble des réunions.</span><span class="sxs-lookup"><span data-stu-id="065be-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="065be-120">Gérer les paramètres de la réunion à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="065be-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="065be-121">Pour gérer les paramètres de la réunion à l’aide du panneau de configuration Skype entreprise Server, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="065be-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="065be-122">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="065be-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="065be-123">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="065be-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="065be-124">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="065be-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="065be-125">Gérer les paramètres de la réunion à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="065be-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="065be-126">Pour gérer les réunions à l’aide de Skype entreprise Server Management Shell, utilisez les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="065be-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="065be-127">**Paramètres de configuration des réunions**</span><span class="sxs-lookup"><span data-stu-id="065be-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="065be-128">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="065be-128">**Cmdlet**</span></span>|<span data-ttu-id="065be-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="065be-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="065be-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="065be-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="065be-131">Renvoie des informations sur les paramètres de configuration de réunion actuellement utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="065be-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="065be-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="065be-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="065be-133">Crée une collection de paramètres de configuration de réunion au niveau de l’étendue du site ou du service.</span><span class="sxs-lookup"><span data-stu-id="065be-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="065be-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="065be-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="065be-135">Supprime une collection existante de paramètres de configuration de réunion.</span><span class="sxs-lookup"><span data-stu-id="065be-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="065be-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="065be-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="065be-137">Modifie les paramètres de configuration de réunion actuellement utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="065be-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

