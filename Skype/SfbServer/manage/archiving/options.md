---
title: Gérer les options d’archivage dans Skype entreprise Server
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Résumé : Découvrez comment configurer les options d’archivage de Skype entreprise Server.'
ms.openlocfilehash: af5c8f90cd49f556e1e787e5f550b54da1976c45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818896"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="90a3b-103">Gérer les options d’archivage dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="90a3b-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="90a3b-104">**Résumé :** Apprenez à configurer les options d’archivage de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="90a3b-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="90a3b-105">Si l’archivage est initialement configuré au déploiement, vous pouvez modifier, ajouter et supprimer des configurations par la suite.</span><span class="sxs-lookup"><span data-stu-id="90a3b-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="90a3b-106">Les options d’archivage déterminent :</span><span class="sxs-lookup"><span data-stu-id="90a3b-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="90a3b-107">l’activation ou la désactivation de l’archivage</span><span class="sxs-lookup"><span data-stu-id="90a3b-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="90a3b-108">Archiver les sessions de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="90a3b-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="90a3b-109">Archiver les sessions de conférence Web</span><span class="sxs-lookup"><span data-stu-id="90a3b-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="90a3b-110">Bloquer l’activité lorsque l’archivage n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="90a3b-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="90a3b-111">Utiliser l’intégration à Exchange</span><span class="sxs-lookup"><span data-stu-id="90a3b-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="90a3b-112">Configurer la purge et l’exportation des données</span><span class="sxs-lookup"><span data-stu-id="90a3b-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="90a3b-113">Vous pouvez préciser les options de configuration aux niveaux suivants :</span><span class="sxs-lookup"><span data-stu-id="90a3b-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="90a3b-114">Configuration de niveau global créée par défaut lors du déploiement de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="90a3b-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="90a3b-115">Configurations facultatives au niveau du site qui déterminent la mise en œuvre de l’archivage d’un site spécifique</span><span class="sxs-lookup"><span data-stu-id="90a3b-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="90a3b-116">Configurations facultatives de niveau de pool qui spécifient la façon dont l’archivage est implémenté pour un pool spécifique</span><span class="sxs-lookup"><span data-stu-id="90a3b-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="90a3b-117">Vous pouvez supprimer une configuration de site ou une configuration de pool, mais vous ne pouvez pas supprimer la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="90a3b-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="90a3b-118">Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies.</span><span class="sxs-lookup"><span data-stu-id="90a3b-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="90a3b-119">Pour plus d’informations sur l’implémentation des configurations d’archivage et la hiérarchie des configurations d’archivage, voir [planifier l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="90a3b-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="90a3b-120">Configurer les options d’archivage à l’aide du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="90a3b-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="90a3b-121">Vous pouvez configurer les options d’archivage à l’aide du panneau de configuration comme suit :</span><span class="sxs-lookup"><span data-stu-id="90a3b-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="90a3b-122">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="90a3b-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="90a3b-123">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="90a3b-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="90a3b-124">Dans la barre de navigation de gauche, cliquez sur **Configuration d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="90a3b-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="90a3b-125">Configurer les options d’archivage à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a3b-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="90a3b-126">Vous pouvez également configurer les options d’archivage à l’aide des applets de commande de Windows PowerShell figurant dans le tableau ci-après.</span><span class="sxs-lookup"><span data-stu-id="90a3b-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="90a3b-127">Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, reportez-vous à la rubrique [Skype entreprise Server Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="90a3b-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="90a3b-128">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="90a3b-128">**Cmdlet**</span></span>|<span data-ttu-id="90a3b-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="90a3b-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90a3b-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="90a3b-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="90a3b-131">Retourne des informations sur les paramètres de configuration d’archivage de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="90a3b-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="90a3b-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="90a3b-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="90a3b-133">Crée un nouveau jeu de paramètres pour la messagerie instantanée qui peuvent être utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer les messages instantanés qu’il n’est pas possible d’archiver.</span><span class="sxs-lookup"><span data-stu-id="90a3b-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="90a3b-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="90a3b-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="90a3b-135">Supprime la collection spécifiée de paramètres d’archivage utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer éventuellement tout message instantané ne pouvant pas être archivé.</span><span class="sxs-lookup"><span data-stu-id="90a3b-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="90a3b-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="90a3b-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="90a3b-137">Modifie une collection existante d’options de configuration d’archivage de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="90a3b-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
