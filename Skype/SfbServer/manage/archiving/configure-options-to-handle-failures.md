---
title: Configurer les options d’archivage pour gérer les échecs dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Résumé : Apprenez à bloquer les sessions par messagerie instantanée et de conférence dans le cas d’un Skype de défaillance du serveur d’entreprise qui empêche l’archivage.'
ms.openlocfilehash: 4fe63319f2b480557c73e238f2b19692df06440f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883017"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="0c606-103">Configurer les options d’archivage pour gérer les échecs dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="0c606-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="0c606-104">**Résumé :** Découvrez comment bloquer les sessions par messagerie instantanée et de conférence dans le cas d’un Skype de défaillance du serveur d’entreprise qui empêche l’archivage.</span><span class="sxs-lookup"><span data-stu-id="0c606-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="0c606-105">Si l’archivage est une condition requise pour votre organisation, vous pouvez bloquer les sessions de messagerie instantanée et la conférence en cas d’un Skype pour Échec Business Server qui empêche l’archivage.</span><span class="sxs-lookup"><span data-stu-id="0c606-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="0c606-106">Cet état est parfois appelé « mode critique ».</span><span class="sxs-lookup"><span data-stu-id="0c606-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="0c606-107">Par exemple, en cas de problème au niveau du service de stockage, la messagerie instantanée peut être bloquée pour les utilisateurs dont l’archivage des communications est activé.</span><span class="sxs-lookup"><span data-stu-id="0c606-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="0c606-108">La récupération des sessions de messagerie instantanée et de conférence est effectuée automatiquement après la correction des échecs.</span><span class="sxs-lookup"><span data-stu-id="0c606-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="0c606-109">Configurer le mode critique à l’aide du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="0c606-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="0c606-110">Pour préciser si des sessions de communication sont autorisées en cas de panne qui empêcherait l’archivage :</span><span class="sxs-lookup"><span data-stu-id="0c606-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="0c606-111">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0c606-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="0c606-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="0c606-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0c606-113">Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="0c606-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="0c606-114">Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, et enfin sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="0c606-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0c606-115">Pour définir le comportement de l’archivage en cas d’échec, cochez ou décochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="0c606-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="0c606-116">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0c606-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="0c606-117">Configurer le mode critique à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c606-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="0c606-118">Vous pouvez également spécifier si les sessions de communication doivent être autorisées en cas de défaillance qui empêche l’archivage à l’aide de l’applet de commande **Set-CsArchivingConfiguration** avec le paramètre BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="0c606-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="0c606-119">Par exemple, la commande suivante désactive communications dans le cas d’un échec d’archivage :</span><span class="sxs-lookup"><span data-stu-id="0c606-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="0c606-120">La commande suivante active les communications en cas de panne d’archivage :</span><span class="sxs-lookup"><span data-stu-id="0c606-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="0c606-121">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0c606-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

