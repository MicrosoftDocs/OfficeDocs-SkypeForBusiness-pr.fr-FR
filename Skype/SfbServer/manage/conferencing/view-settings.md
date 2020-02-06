---
title: Afficher les paramètres de configuration de la réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Résumé : Découvrez comment afficher les paramètres de configuration de la réunion dans Skype entreprise Server.'
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818455"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="33596-103">Afficher les paramètres de configuration de la réunion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="33596-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="33596-104">**Résumé :** Découvrez comment afficher les paramètres de configuration de la réunion dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33596-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="33596-105">Vous pouvez afficher les paramètres de configuration de la réunion en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="33596-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="33596-106">Afficher les paramètres de configuration de la réunion à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="33596-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="33596-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="33596-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="33596-108">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="33596-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="33596-109">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33596-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="33596-110">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="33596-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="33596-111">Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion à afficher.</span><span class="sxs-lookup"><span data-stu-id="33596-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="33596-112">Dans **Modifier le filtre de fichier**, sélectionnez la case à cocher **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="33596-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="33596-113">**Modifier la configuration de \<la\> réunion : une stratégie** s’ouvre et affiche les paramètres de la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="33596-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="33596-114">Pour plus d’informations sur la configuration des paramètres, consultez la rubrique [créer des paramètres de configuration de réunion dans Skype entreprise Server](create-settings.md).</span><span class="sxs-lookup"><span data-stu-id="33596-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="33596-115">Afficher les paramètres de configuration de la réunion à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="33596-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="33596-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="33596-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="33596-117">Pour afficher des informations sur tous vos paramètres de configuration de réunion, utilisez l’applet de commande **Get-CsMeetingConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="33596-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="33596-118">Cette commande renvoie les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="33596-118">This command will return information similar to the following:</span></span>
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

<span data-ttu-id="33596-119">Pour plus d’informations, y compris une liste complète des paramètres, consultez la rubrique [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="33596-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

