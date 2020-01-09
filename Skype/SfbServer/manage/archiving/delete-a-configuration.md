---
title: Suppression d’une configuration de l’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Résumé : Découvrez comment supprimer une configuration d’archivage dans Skype entreprise Server.'
ms.openlocfilehash: 22da9464a4bb6b17c6d4b9aa63ad8990a9152c38
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992371"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="8b213-103">Suppression d’une configuration de l’archivage dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8b213-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="8b213-104">**Résumé :** Découvrez comment supprimer une configuration d’archivage dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8b213-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="8b213-p101">Vous pouvez supprimer une configuration de site ou une configuration de pool, mais vous ne pouvez pas supprimer la configuration globale. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies.</span><span class="sxs-lookup"><span data-stu-id="8b213-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="8b213-107">Supprimer une configuration d’archivage via le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="8b213-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="8b213-108">Pour supprimer une configuration d’archivage en utilisant le Panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="8b213-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="8b213-109">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8b213-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8b213-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8b213-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8b213-111">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="8b213-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="8b213-112">Dans la liste des configurations d’archivage, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8b213-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8b213-113">Vous pouvez cliquer sur Configuration globale, mais choisir cette option uniquement si vous voulez rétablir les valeurs par défaut de la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="8b213-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="8b213-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8b213-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="8b213-115">Supprimer une configuration d’archivage via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b213-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="8b213-116">Vous pouvez également supprimer une configuration de l’archivage à l’aide de l’applet de passe **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8b213-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="8b213-p102">Par exemple, la commande suivante supprime les paramètres de la configuration d’archivage appliquées au site Redmond. Lorsqu’une stratégie configurée au niveau de l’étendue Site est supprimée, les utilisateurs précédemment gérés par cette stratégie utilisent automatiquement à la place la stratégie d’archivage globale :</span><span class="sxs-lookup"><span data-stu-id="8b213-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="8b213-119">La commande suivante supprime tous les paramètres de configuration d’archivage appliqués à l’étendue du service :</span><span class="sxs-lookup"><span data-stu-id="8b213-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="8b213-120">La commande suivante supprime tous les paramètres de configuration d’archivage là où l’archivage Exchange a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="8b213-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="8b213-121">Vous pouvez également utiliser l’applet de commande **Remove-CsArchivingConfiguration** pour rétablir les valeurs par défaut des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="8b213-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="8b213-122">Par exemple, supposons que vous avez activé l’archivage d’une session de messagerie instantanée au niveau global ; la commande suivante rétablit la valeur par défaut None, ce qui désactive l’archivage au niveau global :</span><span class="sxs-lookup"><span data-stu-id="8b213-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="8b213-123">Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8b213-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
