---
title: Gérer les stratégies d’archivage de Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Résumé : Découvrez comment gérer les stratégies d’utilisateur pour l’archivage pour Skype pour Business Server.'
ms.openlocfilehash: 289902ded6f1530c74f9c945517a3c853c99d364
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873239"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="a9c98-103">Gérer les stratégies d’archivage de Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a9c98-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="a9c98-104">**Résumé :** Découvrez comment gérer les stratégies d’utilisateur pour l’archivage pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="a9c98-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="a9c98-105">Vous définissez initialement des stratégies d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a9c98-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="a9c98-106">Si vous souhaitez archiver déterminent les stratégies d’archivage :</span><span class="sxs-lookup"><span data-stu-id="a9c98-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="a9c98-107">Communications internes</span><span class="sxs-lookup"><span data-stu-id="a9c98-107">Internal communications</span></span>
    
- <span data-ttu-id="a9c98-108">Communications externes</span><span class="sxs-lookup"><span data-stu-id="a9c98-108">External communications</span></span>
    
<span data-ttu-id="a9c98-109">Les stratégies d’archivage peuvent être définies au niveau global, site ou au niveau utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9c98-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9c98-110">Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, le contrôle des stratégies Exchange si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et mettre les boîtes aux lettres en blocage sur Place.</span><span class="sxs-lookup"><span data-stu-id="a9c98-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a9c98-111">Pour plus d’informations, voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md) et [configurer l’intégration avec le stockage Exchange pour Skype pour Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="a9c98-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="a9c98-112">Gérer les options d’archivage via le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="a9c98-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="a9c98-113">Vous pouvez gérer les stratégies d’archivage via le Panneau de configuration comme suit :</span><span class="sxs-lookup"><span data-stu-id="a9c98-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="a9c98-114">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a9c98-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="a9c98-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a9c98-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a9c98-116">Dans la barre de navigation de gauche, cliquez sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="a9c98-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="a9c98-117">Gérer les stratégies d’archivage via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9c98-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="a9c98-118">Vous pouvez également configurer les stratégies d’archivage via les applets de commande Windows PowerShell répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a9c98-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="a9c98-119">Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, voir [Skype pour Business Server Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="a9c98-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="a9c98-120">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="a9c98-120">**Cmdlet**</span></span>|<span data-ttu-id="a9c98-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="a9c98-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9c98-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9c98-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="a9c98-123">Retourne des informations sur les stratégies d’archivage des sessions de messagerie instantanée de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a9c98-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="a9c98-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9c98-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="a9c98-125">Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9c98-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="a9c98-126">Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.</span><span class="sxs-lookup"><span data-stu-id="a9c98-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="a9c98-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9c98-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="a9c98-128">Crée des stratégies d’archivage des sessions de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="a9c98-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="a9c98-129">Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.</span><span class="sxs-lookup"><span data-stu-id="a9c98-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="a9c98-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9c98-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="a9c98-131">Supprime le spécifié messagerie instantanée (MI) qui détermine si Skype pour Business Server doit enregistrer automatiquement toutes les sessions de messagerie instantanée qui ont lieu entre les utilisateurs internes et/ou toutes les sessions de messagerie instantanée entre utilisateurs internes et des partenaires fédérés stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="a9c98-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="a9c98-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9c98-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="a9c98-133">Modifie une existante la messagerie instantanée (MI) stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="a9c98-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="a9c98-134">Une stratégie d’archivage vous donne la possibilité d’archiver tous les sessions de messagerie instantanée et les conférences qui ont lieu entre les utilisateurs internes ; Vous pouvez également archiver les sessions qui ont lieu entre les utilisateurs internes et des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="a9c98-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

