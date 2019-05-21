---
title: Supprimer les paramètres de configuration de la réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Résumé: Découvrez comment supprimer des paramètres de configuration de réunion dans Skype entreprise Server.'
ms.openlocfilehash: a728f1c1de3470cf505163c5cb25996c190e9026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306474"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="ca0a9-103">Supprimer les paramètres de configuration de la réunion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ca0a9-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="ca0a9-104">**Résumé:** Découvrez comment supprimer des paramètres de configuration de réunion dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ca0a9-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="ca0a9-105">Vous pouvez supprimer les paramètres de configuration de la réunion à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ca0a9-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="ca0a9-p101">Vous pouvez supprimer une configuration de site ou d’utilisateur, mais il est impossible de supprimer la configuration globale. Si vous tentez de supprimer la configuration globale, ses valeurs par défaut sont rétablies automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ca0a9-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ca0a9-108">Supprimer les paramètres de configuration de la réunion à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ca0a9-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ca0a9-109">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ca0a9-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ca0a9-110">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ca0a9-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ca0a9-111">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="ca0a9-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="ca0a9-112">Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool à supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ca0a9-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ca0a9-113">Supprimer les paramètres de configuration de la réunion à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ca0a9-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ca0a9-114">Pour supprimer les paramètres de réunion, utilisez l’applet de commande **Remove-Cs MeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ca0a9-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="ca0a9-115">La commande ci-dessous supprime les paramètres de configuration de réunion appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="ca0a9-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="ca0a9-116">La commande ci-dessous supprime tous les paramètres de configuration de réunion appliqués au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="ca0a9-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="ca0a9-117">Pour plus d’informations, y compris une liste complète des paramètres, consultez la rubrique [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ca0a9-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

