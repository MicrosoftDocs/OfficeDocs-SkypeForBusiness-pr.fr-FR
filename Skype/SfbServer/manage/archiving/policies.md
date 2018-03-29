---
title: Gestion des stratégies d’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Résumé : Apprenez à gérer les stratégies de l’utilisateur pour l’archivage de Skype pour Business Server 2015.'
ms.openlocfilehash: 584849862e106098bc4bbad92ed4e0b87be410e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="3324f-103">Gestion des stratégies d’archivage dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="3324f-103">Manage archiving policies in Skype for Business Server 2015</span></span>

<span data-ttu-id="3324f-104">**Résumé :** Découvrez comment gérer les stratégies de l’utilisateur pour l’archivage de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3324f-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3324f-105">Vous définissez initialement politiques d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations d’après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="3324f-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="3324f-106">Les stratégies d’archivage déterminent s’il faut archiver :</span><span class="sxs-lookup"><span data-stu-id="3324f-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="3324f-107">Communications internes</span><span class="sxs-lookup"><span data-stu-id="3324f-107">Internal communications</span></span>
    
- <span data-ttu-id="3324f-108">Communications externes</span><span class="sxs-lookup"><span data-stu-id="3324f-108">External communications</span></span>
    
<span data-ttu-id="3324f-109">Politiques d’archivage peuvent être définies au niveau global, du site ou niveau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3324f-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3324f-110">Si vous activé l’intégration de Microsoft Exchange pour votre déploiement, le contrôle des stratégies Exchange si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et que leurs boîtes aux lettres sur Place maintenez.</span><span class="sxs-lookup"><span data-stu-id="3324f-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="3324f-111">Pour plus d’informations, consultez [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md) et [configurer une intégration avec le stockage Exchange pour Skype pour Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="3324f-111">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="3324f-112">Gérer les options d’archivage via le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="3324f-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="3324f-113">Vous pouvez gérer les stratégies d’archivage via le Panneau de configuration comme suit :</span><span class="sxs-lookup"><span data-stu-id="3324f-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="3324f-114">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3324f-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3324f-115">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="3324f-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3324f-116">Dans la barre de navigation de gauche, cliquez sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="3324f-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="3324f-117">Gérer les stratégies d’archivage via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3324f-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="3324f-118">Vous pouvez également configurer les stratégies d’archivage via les applets de commande Windows PowerShell répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="3324f-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="3324f-119">Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, consultez [Skype pour Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="3324f-119">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="3324f-120">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="3324f-120">**Cmdlet**</span></span>|<span data-ttu-id="3324f-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="3324f-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3324f-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3324f-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3324f-123">Retourne des informations sur les stratégies d’archivage des sessions de messagerie instantanée de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3324f-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="3324f-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3324f-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3324f-125">Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3324f-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="3324f-126">Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.</span><span class="sxs-lookup"><span data-stu-id="3324f-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="3324f-127">Nouvelle-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3324f-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3324f-128">Crée des stratégies d’archivage des sessions de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="3324f-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="3324f-129">Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.</span><span class="sxs-lookup"><span data-stu-id="3324f-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="3324f-130">Supprimer-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3324f-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3324f-131">Supprime le spécifié messagerie instantanée (MI) d’archivage de stratégie qui détermine si les Skype pour Business Server enregistre automatiquement toutes les sessions de messagerie instantanée qui ont lieu entre les utilisateurs internes, ou toutes les sessions de messagerie instantanée entre des utilisateurs internes et des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="3324f-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="3324f-132">Ensemble-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3324f-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3324f-133">Modifie un existant messagerie instantanée (MI stratégie d’archivage).</span><span class="sxs-lookup"><span data-stu-id="3324f-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="3324f-134">Une stratégie d’archivage vous donne la possibilité d’archiver toutes les sessions de messagerie instantanée et les conférences qui ont lieu entre des utilisateurs internes ; Vous pouvez également archiver les sessions qui ont lieu entre les utilisateurs internes et des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="3324f-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

