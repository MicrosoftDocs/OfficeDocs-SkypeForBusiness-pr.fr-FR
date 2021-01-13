---
title: Modifier les paramètres de configuration de réunion dans Skype Entreprise Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Résumé : Découvrez comment modifier les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827994"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7d7cb-103">Modifier les paramètres de configuration de réunion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7d7cb-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7d7cb-104">**Résumé :** Découvrez comment modifier les paramètres de configuration de réunion dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="7d7cb-105">Vous pouvez modifier les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7d7cb-106">Modifier les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7d7cb-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7d7cb-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7d7cb-108">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7d7cb-109">Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur **Configuration de la réunion.**</span><span class="sxs-lookup"><span data-stu-id="7d7cb-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="7d7cb-110">Dans la liste des configurations de réunion, cliquez sur la configuration à modifier, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**</span><span class="sxs-lookup"><span data-stu-id="7d7cb-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7d7cb-111">Dans **Modifier la configuration de la réunion**, modifiez les paramètres de configuration, à l’exception du nom de configuration qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="7d7cb-112">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7d7cb-113">Modifier les paramètres de configuration de réunion à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="7d7cb-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7d7cb-114">Pour modifier les paramètres de configuration de réunion, utilisez l’cmdlet **Set-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="7d7cb-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="7d7cb-115">La commande présentée dans l’exemple suivant modifie les paramètres de configuration de réunion affectés au site Redmond (-Identity site:Redmond).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="7d7cb-116">Dans ce cas, la valeur de la propriété DesignateAsPresenter est définie sur Tout le monde :</span><span class="sxs-lookup"><span data-stu-id="7d7cb-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="7d7cb-117">Pour plus d’informations, y compris une liste complète des paramètres, voir [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

