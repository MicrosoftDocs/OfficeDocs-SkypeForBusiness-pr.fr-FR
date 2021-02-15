---
title: Gérer les stratégies d’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Résumé : Découvrez comment gérer les stratégies utilisateur pour l’archivage de Skype Entreprise Server.'
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828545"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="3d325-103">Gérer les stratégies d’archivage dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3d325-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="3d325-104">**Résumé :** Découvrez comment gérer les stratégies utilisateur pour l’archivage de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3d325-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="3d325-105">Vous définissez initialement les stratégies d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="3d325-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="3d325-106">Les stratégies d’archivage déterminent s’il faut archiver :</span><span class="sxs-lookup"><span data-stu-id="3d325-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="3d325-107">Communications internes</span><span class="sxs-lookup"><span data-stu-id="3d325-107">Internal communications</span></span>
    
- <span data-ttu-id="3d325-108">Communications externes</span><span class="sxs-lookup"><span data-stu-id="3d325-108">External communications</span></span>
    
<span data-ttu-id="3d325-109">Les stratégies d’archivage peuvent être définies au niveau global, du site ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3d325-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d325-110">Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies Exchange contrôlent si l’archivage est activé pour les utilisateurs qui sont homed on Exchange et dont les boîtes aux lettres sont mises en In-Place archive.</span><span class="sxs-lookup"><span data-stu-id="3d325-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="3d325-111">Pour plus d’informations, voir [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="3d325-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="3d325-112">Gérer les stratégies d’archivage à l’aide du Panneau de contrôle</span><span class="sxs-lookup"><span data-stu-id="3d325-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="3d325-113">Vous pouvez gérer les stratégies d’archivage à l’aide du Panneau de contrôle comme suit :</span><span class="sxs-lookup"><span data-stu-id="3d325-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="3d325-114">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3d325-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3d325-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3d325-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3d325-116">Dans la barre de navigation de gauche, cliquez sur **Stratégie d’archivage**</span><span class="sxs-lookup"><span data-stu-id="3d325-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="3d325-117">Gérer les stratégies d’archivage à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d325-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="3d325-118">Vous pouvez également configurer des stratégies d’archivage à l’aide Windows PowerShell cmdlets répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="3d325-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="3d325-119">Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, voir [Skype Entreprise Server Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="3d325-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="3d325-120">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="3d325-120">**Cmdlet**</span></span>|<span data-ttu-id="3d325-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="3d325-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3d325-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3d325-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3d325-123">Retourne des informations sur les stratégies d’archivage des sessions de messagerie instantanée de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3d325-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="3d325-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3d325-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3d325-125">Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à des ensembles d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3d325-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="3d325-126">Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.</span><span class="sxs-lookup"><span data-stu-id="3d325-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="3d325-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3d325-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3d325-128">Crée des stratégies d’archivage des sessions de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="3d325-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="3d325-129">Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.</span><span class="sxs-lookup"><span data-stu-id="3d325-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="3d325-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3d325-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3d325-131">Supprime la stratégie d’archivage de messagerie instantanée spécifiée qui détermine si Skype Entreprise Server enregistre automatiquement toutes les sessions de messagerie instantanée qui ont lieu entre les utilisateurs internes et/ou toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="3d325-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="3d325-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3d325-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3d325-133">Modifie une stratégie d’archivage de messagerie instantanée existante.</span><span class="sxs-lookup"><span data-stu-id="3d325-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="3d325-134">Une stratégie d’archivage vous permet d’archiver toutes les sessions de messagerie instantanée et les conférences qui ont lieu entre des utilisateurs internes ; vous pouvez également archiver des sessions qui ont lieu entre des utilisateurs internes et des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="3d325-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

