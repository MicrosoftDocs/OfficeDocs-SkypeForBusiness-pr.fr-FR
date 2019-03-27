---
title: Supprimer une configuration d’archivage dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Résumé : Découvrez comment supprimer une configuration d’archivage dans Skype pour Business Server.'
ms.openlocfilehash: 5e567a08606bb9d0475033515b4b9148deb2f446
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895582"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="72d68-103">Supprimer une configuration d’archivage dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="72d68-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="72d68-104">**Résumé :** Découvrez comment supprimer une configuration d’archivage dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="72d68-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="72d68-p101">Vous pouvez supprimer une configuration de site ou une configuration de pool, mais vous ne pouvez pas supprimer la configuration globale. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies.</span><span class="sxs-lookup"><span data-stu-id="72d68-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="72d68-107">Supprimer une configuration d’archivage via le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="72d68-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="72d68-108">Pour supprimer une configuration d’archivage en utilisant le Panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="72d68-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="72d68-109">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="72d68-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="72d68-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="72d68-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="72d68-111">Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="72d68-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="72d68-112">Dans la liste des configurations d’archivage, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="72d68-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="72d68-113">Vous pouvez cliquer sur Configuration globale, mais choisir cette option uniquement si vous voulez rétablir les valeurs par défaut de la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="72d68-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="72d68-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="72d68-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="72d68-115">Supprimer une configuration d’archivage via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72d68-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="72d68-116">Vous pouvez également supprimer une configuration d’archivage à l’aide de l’applet de commande **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="72d68-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="72d68-p102">Par exemple, la commande suivante supprime les paramètres de la configuration d’archivage appliquées au site Redmond. Lorsqu’une stratégie configurée au niveau de l’étendue Site est supprimée, les utilisateurs précédemment gérés par cette stratégie utilisent automatiquement à la place la stratégie d’archivage globale :</span><span class="sxs-lookup"><span data-stu-id="72d68-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="72d68-119">La commande suivante supprime tous les paramètres de configuration d’archivage appliqués à l’étendue du service :</span><span class="sxs-lookup"><span data-stu-id="72d68-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="72d68-120">La commande suivante supprime tous les paramètres de configuration d’archivage là où l’archivage Exchange a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="72d68-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="72d68-121">Vous pouvez également utiliser l’applet de commande **Remove-CsArchivingConfiguration** pour rétablir les valeurs par défaut des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="72d68-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="72d68-122">Par exemple, supposons que vous avez activé l’archivage d’une session de messagerie instantanée au niveau global ; la commande suivante rétablit la valeur par défaut None, ce qui désactive l’archivage au niveau global :</span><span class="sxs-lookup"><span data-stu-id="72d68-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="72d68-123">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="72d68-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
