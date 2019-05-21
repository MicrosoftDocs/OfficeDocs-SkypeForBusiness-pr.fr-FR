---
title: Modifier les paramètres de configuration de la réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Résumé: Découvrez comment modifier les paramètres de configuration de la réunion dans Skype entreprise Server.'
ms.openlocfilehash: 6e2566a5bc48e081c1912753586aef2213e1c727
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280396"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d0634-103">Modifier les paramètres de configuration de la réunion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d0634-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d0634-104">**Résumé:** Découvrez comment modifier les paramètres de configuration de la réunion dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0634-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d0634-105">Vous pouvez modifier les paramètres de configuration de la réunion à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d0634-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d0634-106">Modifier les paramètres de configuration de la réunion à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d0634-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d0634-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="d0634-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d0634-108">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0634-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d0634-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="d0634-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="d0634-110">Dans la liste des configurations de réunion, cliquez sur la configuration à modifier, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="d0634-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d0634-111">Dans **Modifier la configuration de la réunion**, modifiez les paramètres de configuration, à l’exception du nom de configuration qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="d0634-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="d0634-112">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="d0634-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d0634-113">Modifier les paramètres de configuration de la réunion à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d0634-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d0634-114">Pour modifier les paramètres de configuration de réunion, utilisez l’applet de commande \*\* Set-CsMeetingConfiguration\*\*.</span><span class="sxs-lookup"><span data-stu-id="d0634-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="d0634-p101">La commande de l’exemple ci-dessous modifie les paramètres de configuration de réunion affectés au site Redmond (-Identity site:Redmond). Dans ce cas, la valeur de la propriété DesignateAsPresenter est Everyone :</span><span class="sxs-lookup"><span data-stu-id="d0634-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="d0634-117">Pour plus d’informations, y compris une liste complète des paramètres, consultez la rubrique [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d0634-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

