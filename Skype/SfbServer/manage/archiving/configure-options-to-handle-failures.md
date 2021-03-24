---
title: Configurer les options d’archivage pour gérer les défaillances dans Skype Entreprise Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Résumé : Découvrez comment bloquer les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server qui empêcherait l’archivage.'
ms.openlocfilehash: 8bfe4d3f8e02fa0d7d7d3f1f6b55f224aaa1451a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095448"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="6eadb-103">Configurer les options d’archivage pour gérer les défaillances dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6eadb-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="6eadb-104">**Résumé :** Découvrez comment bloquer les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server qui empêcherait l’archivage.</span><span class="sxs-lookup"><span data-stu-id="6eadb-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="6eadb-105">Si l’archivage est une condition requise pour votre organisation, vous pouvez bloquer les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server qui empêcherait l’archivage.</span><span class="sxs-lookup"><span data-stu-id="6eadb-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="6eadb-106">Ce mode est parfois appelé mode critique.</span><span class="sxs-lookup"><span data-stu-id="6eadb-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="6eadb-107">Par exemple, en cas de problème avec un service de stockage, la messagerie instantanée est bloquée pour les utilisateurs dont les communications sont activées pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="6eadb-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="6eadb-108">La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.</span><span class="sxs-lookup"><span data-stu-id="6eadb-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="6eadb-109">Configurer le mode critique à l’aide du Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="6eadb-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="6eadb-110">Pour spécifier si les sessions de communication doivent être autorisées en cas de défaillance qui empêcherait l’archivage :</span><span class="sxs-lookup"><span data-stu-id="6eadb-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="6eadb-111">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="6eadb-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="6eadb-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6eadb-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6eadb-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="6eadb-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="6eadb-114">Cliquez sur le nom de la configuration globale, de site ou de pool appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**</span><span class="sxs-lookup"><span data-stu-id="6eadb-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6eadb-115">Pour définir le comportement de l’archivage en cas d’échec, cochez ou décochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="6eadb-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="6eadb-116">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="6eadb-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="6eadb-117">Configurer le mode critique à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6eadb-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="6eadb-118">Vous pouvez également spécifier si les sessions de communication doivent être autorisées en cas de défaillance qui empêcherait l’archivage à l’aide de l';cmdlet **Set-CsArchivingConfiguration** avec le paramètre BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="6eadb-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="6eadb-119">Par exemple, la commande suivante désactive les communications en cas de défaillance de l’archivage :</span><span class="sxs-lookup"><span data-stu-id="6eadb-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="6eadb-120">La commande suivante active les communications en cas d’échec de l’archivage :</span><span class="sxs-lookup"><span data-stu-id="6eadb-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="6eadb-121">Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Set-CsArchivingConfiguration.](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6eadb-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
