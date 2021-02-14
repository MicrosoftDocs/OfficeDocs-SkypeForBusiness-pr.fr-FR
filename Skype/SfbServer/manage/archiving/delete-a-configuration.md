---
title: Supprimer une configuration d’archivage dans Skype Entreprise Server
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Résumé : Découvrez comment supprimer une configuration d’archivage dans Skype Entreprise Server.'
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817624"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="468f7-103">Supprimer une configuration d’archivage dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="468f7-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="468f7-104">**Résumé :** Découvrez comment supprimer une configuration d’archivage dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="468f7-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="468f7-105">Vous pouvez supprimer une configuration de site ou de pool, mais vous ne pouvez pas supprimer la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="468f7-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="468f7-106">Si vous supprimez la configuration globale, elle est réinitialisée automatiquement aux valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="468f7-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="468f7-107">Supprimer une configuration d’archivage à l’aide du Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="468f7-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="468f7-108">Pour supprimer une configuration d’archivage à l’aide du Panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="468f7-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="468f7-109">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="468f7-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="468f7-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="468f7-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="468f7-111">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="468f7-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="468f7-112">Dans la liste des configurations d’archivage, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="468f7-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="468f7-113">Vous pouvez également cliquer sur la configuration globale, mais choisissez cette option uniquement si vous souhaitez rétablir les valeurs par défaut de la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="468f7-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="468f7-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="468f7-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="468f7-115">Supprimer une configuration d’archivage à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="468f7-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="468f7-116">Vous pouvez également supprimer une configuration d’archivage à l’aide de l’cmdlet **Remove-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="468f7-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="468f7-117">Par exemple, la commande suivante supprime les paramètres de configuration d’archivage appliqués au site Redmond.</span><span class="sxs-lookup"><span data-stu-id="468f7-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="468f7-118">Lorsqu’une stratégie configurée au niveau de l’étendue Site est supprimée, les utilisateurs précédemment gérés par la stratégie de site sont automatiquement régis par la stratégie d’archivage globale à la place :</span><span class="sxs-lookup"><span data-stu-id="468f7-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="468f7-119">La commande suivante supprime tous les paramètres de configuration d’archivage appliqués à l’étendue Service :</span><span class="sxs-lookup"><span data-stu-id="468f7-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="468f7-120">La commande suivante supprime tous les paramètres de configuration d’archivage pour lequel l’archivage Exchange a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="468f7-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="468f7-121">Vous pouvez également utiliser l’cmdlet **Remove-CsArchivingConfiguration** pour rétablir les valeurs par défaut des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="468f7-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="468f7-122">Par exemple, supposons que vous avez activé l’archivage des sessions de messagerie instantanée au niveau global ; La commande suivante réinitialise la valeur par défaut de Aucun, ce qui désactive l’archivage au niveau global :</span><span class="sxs-lookup"><span data-stu-id="468f7-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="468f7-123">Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Remove-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="468f7-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
