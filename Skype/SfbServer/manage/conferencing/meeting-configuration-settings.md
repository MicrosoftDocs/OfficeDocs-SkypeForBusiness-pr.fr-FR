---
title: Gestion des paramètres de configuration de réunion dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Résumé : Apprenez à gérer les paramètres de configuration dans Skype pour Business Server 2015 de réunion.'
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="ba5ed-103">Gestion des paramètres de configuration de réunion dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="ba5ed-103">Manage meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ba5ed-104">**Résumé :** Apprenez à gérer les paramètres de configuration dans Skype pour Business Server 2015 de réunion.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ba5ed-105">Cette rubrique décrit comment gérer les paramètres de configuration de réunion.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="ba5ed-106">Pour plus d’informations sur la façon de planifier et de déployer des conférences, voir [conférences de déployer dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md)et de [Plan pour les conférences dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) .</span><span class="sxs-lookup"><span data-stu-id="ba5ed-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="ba5ed-107">Les paramètres de configuration de réunion dictent le type de réunions que les utilisateurs peuvent créer, contrôler comment (ou même si) les utilisateurs anonymes et les utilisateurs d’accès à la conférence peuvent joindre à ces réunions.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="ba5ed-108">Notez que ces paramètres n’affectent que les réunions planifiées ; elles n’affectent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="ba5ed-109">Les paramètres de configuration de réunion définissent ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ba5ed-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="ba5ed-110">si les appels émis à partir d’un du réseau téléphonique commuté (PSTN) sont transférés vers la salle d’attente ;</span><span class="sxs-lookup"><span data-stu-id="ba5ed-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="ba5ed-111">qui peut être présentateur ;</span><span class="sxs-lookup"><span data-stu-id="ba5ed-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="ba5ed-112">si le type de conférence est affecté par défaut ;</span><span class="sxs-lookup"><span data-stu-id="ba5ed-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="ba5ed-113">si les utilisateurs anonymes (non authentifiés) sont admis par défaut.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="ba5ed-114">Vous pouvez définir les caractéristiques des réunions à l’aide de Skype pour le panneau de configuration de Business Server ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="ba5ed-115">Vous pouvez spécifier des paramètres au niveau global (créé par défaut) de la réunion, au niveau du site ou au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="ba5ed-116">Par défaut, les paramètres globaux définissent l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="ba5ed-117">Si vous créez des paramètres au niveau du pool, ceux-ci s’appliquent à toutes les réunions hébergées par ce pool.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="ba5ed-118">Si vous ne créez pas de paramètres au niveau du pool, les paramètres définis au niveau du site s’appliquent, s’ils existent.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="ba5ed-119">Si aucun paramètre n’a été défini au niveau du site, les paramètres globaux s’appliquent à l’ensemble des réunions.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ba5ed-120">Gérer les paramètres de réunion pour le panneau de configuration de Business Server à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="ba5ed-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="ba5ed-121">Pour gérer les paramètres de la réunion pour le panneau de configuration de Business Server à l’aide de Skype :</span><span class="sxs-lookup"><span data-stu-id="ba5ed-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="ba5ed-122">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ba5ed-123">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ba5ed-124">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ba5ed-125">Gérer les paramètres de réunion pour Business Server Management Shell à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="ba5ed-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ba5ed-126">Pour gérer des réunions à l’aide de Skype pour Business Server Management Shell, utilisez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba5ed-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="ba5ed-127">**Paramètres de configuration de réunion**</span><span class="sxs-lookup"><span data-stu-id="ba5ed-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="ba5ed-128">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="ba5ed-128">**Cmdlet**</span></span>|<span data-ttu-id="ba5ed-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="ba5ed-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ba5ed-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ba5ed-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="ba5ed-131">Renvoie des informations sur les paramètres de configuration de réunion actuellement utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="ba5ed-132">Nouvelle-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ba5ed-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="ba5ed-133">Crée une collection de paramètres de configuration de réunion au niveau de l’étendue du site ou du service.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="ba5ed-134">Supprimer-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ba5ed-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="ba5ed-135">Supprime une collection existante de paramètres de configuration de réunion.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="ba5ed-136">Ensemble-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ba5ed-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="ba5ed-137">Modifie les paramètres de configuration de réunion actuellement utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ba5ed-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

