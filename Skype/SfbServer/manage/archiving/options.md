---
title: Gérer les options d’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Résumé : Découvrez comment configurer les options d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817534"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="4599c-103">Gérer les options d’archivage dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4599c-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="4599c-104">**Résumé :** Découvrez comment configurer les options d’archivage pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4599c-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="4599c-105">Vous configurez initialement l’archivage lors du déploiement, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="4599c-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="4599c-106">Les options d’archivage déterminent s’il faut :</span><span class="sxs-lookup"><span data-stu-id="4599c-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="4599c-107">Activation ou désactivation de l’archivage</span><span class="sxs-lookup"><span data-stu-id="4599c-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="4599c-108">Archiver les sessions de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="4599c-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="4599c-109">Archiver les sessions de conférence web</span><span class="sxs-lookup"><span data-stu-id="4599c-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="4599c-110">Bloquer l’activité lorsque l’archivage n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="4599c-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="4599c-111">Utiliser l’intégration Exchange</span><span class="sxs-lookup"><span data-stu-id="4599c-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="4599c-112">Configurer le purgement et l’exportation des données</span><span class="sxs-lookup"><span data-stu-id="4599c-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="4599c-113">Vous pouvez spécifier des options de configuration aux niveaux suivants :</span><span class="sxs-lookup"><span data-stu-id="4599c-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="4599c-114">Configuration au niveau global créée par défaut lorsque vous déployez Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4599c-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="4599c-115">Configurations facultatives au niveau du site qui spécifient la façon dont l’archivage est implémenté pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="4599c-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="4599c-116">Configurations facultatives au niveau du pool qui spécifient comment l’archivage est implémenté pour un pool spécifique</span><span class="sxs-lookup"><span data-stu-id="4599c-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="4599c-117">Vous pouvez supprimer une configuration de site ou de pool, mais vous ne pouvez pas supprimer la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="4599c-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="4599c-118">Si vous supprimez la configuration globale, elle est réinitialisée automatiquement aux valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="4599c-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="4599c-119">Pour plus d’informations sur la façon dont les configurations d’archivage sont implémentées et la hiérarchie des configurations d’archivage, voir [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="4599c-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="4599c-120">Configurer les options d’archivage à l’aide du Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="4599c-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="4599c-121">Vous pouvez configurer les options d’archivage à l’aide du Panneau de configuration comme suit :</span><span class="sxs-lookup"><span data-stu-id="4599c-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="4599c-122">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4599c-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="4599c-123">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4599c-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4599c-124">Dans la barre de navigation de gauche, cliquez sur **Configuration de l’archivage.**</span><span class="sxs-lookup"><span data-stu-id="4599c-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="4599c-125">Configurer les options d’archivage à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4599c-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="4599c-126">Vous pouvez également configurer les options d’archivage à l’aide Windows PowerShell cmdlets répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="4599c-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="4599c-127">Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, voir [Skype Entreprise Server Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="4599c-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="4599c-128">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="4599c-128">**Cmdlet**</span></span>|<span data-ttu-id="4599c-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="4599c-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4599c-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="4599c-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="4599c-131">Retourne des informations sur les paramètres de configuration de l’archivage dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4599c-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="4599c-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="4599c-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="4599c-133">Crée un nouvel ensemble de paramètres de messagerie instantanée, qui peuvent être utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer les messages instantanés qui ne peuvent pas être archivés.</span><span class="sxs-lookup"><span data-stu-id="4599c-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="4599c-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="4599c-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="4599c-135">Supprime la collection spécifiée de paramètres d’archivage utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer éventuellement les messages instantanés qui ne peuvent pas être archivés.</span><span class="sxs-lookup"><span data-stu-id="4599c-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="4599c-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="4599c-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="4599c-137">Modifie une collection existante d’options de configuration de l’archivage de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="4599c-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
