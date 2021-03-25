---
title: Supprimer les paramètres de configuration de réunion dans Skype Entreprise Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119493"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="82227-103">Supprimer les paramètres de configuration de réunion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="82227-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="82227-104">**Résumé :** Découvrez comment supprimer les paramètres de configuration de réunion dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="82227-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="82227-105">Vous pouvez supprimer les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="82227-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="82227-106">Vous pouvez supprimer une configuration de site ou d’utilisateur, mais vous ne pouvez pas supprimer la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="82227-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="82227-107">Si vous essayez de supprimer la configuration globale, elle est automatiquement réinitialisée aux valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="82227-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="82227-108">Supprimer les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="82227-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="82227-109">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="82227-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="82227-110">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="82227-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="82227-111">Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Configuration de **la réunion.**</span><span class="sxs-lookup"><span data-stu-id="82227-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="82227-112">Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool à supprimer, cliquez sur **Modifier,** puis sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="82227-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="82227-113">Supprimer les paramètres de configuration de réunion à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="82227-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="82227-114">Pour supprimer les paramètres de réunion, utilisez l’cmdlet **Remove-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="82227-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="82227-115">La commande suivante supprime les paramètres de configuration de réunion appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="82227-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="82227-116">La commande suivante supprime tous les paramètres de configuration de réunion appliqués à l’étendue Site :</span><span class="sxs-lookup"><span data-stu-id="82227-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="82227-117">Pour plus d’informations, y compris une liste complète des paramètres, voir [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="82227-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
