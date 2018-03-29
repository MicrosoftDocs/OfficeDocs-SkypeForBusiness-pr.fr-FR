---
title: Configuration des options d’archivage de gestion des pannes dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Résumé : Apprenez à bloquer les sessions de conférence et de messagerie instantanée dans le cas d’un Skype pour Échec Business Server 2015 qui pourraient empêcher l’archivage.'
ms.openlocfilehash: 4ad6b8eb496555751aab31949aa3e710749e0262
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server-2015"></a><span data-ttu-id="288e1-103">Configuration des options d’archivage de gestion des pannes dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="288e1-103">Configure archiving options to handle failures in Skype for Business Server 2015</span></span>

<span data-ttu-id="288e1-104">**Résumé :** Découvrez comment faire pour bloquer des sessions de conférence et de messagerie instantanée dans le cas d’un Skype pour Échec Business Server 2015 qui pourraient empêcher l’archivage.</span><span class="sxs-lookup"><span data-stu-id="288e1-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server 2015 failure that would prevent archiving.</span></span>
  
<span data-ttu-id="288e1-105">Si l’archivage est un besoin de votre organisation, vous pouvez bloquer les sessions de messagerie instantanée et de conférence dans le cas d’un Skype pour Échec de Business Server qui peut empêcher l’archivage.</span><span class="sxs-lookup"><span data-stu-id="288e1-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="288e1-106">Cet état est parfois appelé « mode critique ».</span><span class="sxs-lookup"><span data-stu-id="288e1-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="288e1-107">Par exemple, en cas de problème au niveau du service de stockage, la messagerie instantanée peut être bloquée pour les utilisateurs dont l’archivage des communications est activé.</span><span class="sxs-lookup"><span data-stu-id="288e1-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="288e1-108">La récupération des sessions de messagerie instantanée et de conférence est effectuée automatiquement après la correction des échecs.</span><span class="sxs-lookup"><span data-stu-id="288e1-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="288e1-109">Configurer le mode critique à l’aide du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="288e1-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="288e1-110">Pour préciser si des sessions de communication sont autorisées en cas de panne qui empêcherait l’archivage :</span><span class="sxs-lookup"><span data-stu-id="288e1-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="288e1-111">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="288e1-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="288e1-112">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="288e1-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="288e1-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="288e1-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="288e1-114">Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, et enfin sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="288e1-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="288e1-115">Pour définir le comportement de l’archivage en cas d’échec, cochez ou décochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="288e1-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="288e1-116">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="288e1-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="288e1-117">Configurer le mode critique à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="288e1-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="288e1-118">Vous pouvez également spécifier si des sessions de communication peut être autorisées en cas de défaillance qui peut empêcher l’archivage à l’aide de l’applet de commande **Set-CsArchivingConfiguration** avec le paramètre BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="288e1-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="288e1-119">Par exemple, la commande suivante désactive les communications en cas d’un échec de l’archivage :</span><span class="sxs-lookup"><span data-stu-id="288e1-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="288e1-120">La commande suivante active les communications en cas de panne d’archivage :</span><span class="sxs-lookup"><span data-stu-id="288e1-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="288e1-121">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="288e1-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

