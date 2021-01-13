---
title: Afficher les paramètres de configuration de réunion dans Skype Entreprise Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Résumé : Découvrez comment afficher les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827924"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="05fe1-103">Afficher les paramètres de configuration de réunion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="05fe1-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="05fe1-104">**Résumé :** Découvrez comment afficher les paramètres de configuration de réunion dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="05fe1-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="05fe1-105">Vous pouvez afficher les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="05fe1-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="05fe1-106">Afficher les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="05fe1-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="05fe1-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="05fe1-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="05fe1-108">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="05fe1-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="05fe1-109">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="05fe1-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="05fe1-110">Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur **Configuration de la réunion.**</span><span class="sxs-lookup"><span data-stu-id="05fe1-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="05fe1-111">Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion que vous voulez afficher.</span><span class="sxs-lookup"><span data-stu-id="05fe1-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="05fe1-112">Dans **Modifier le filtre de fichier,** cochez la case Afficher les **détails.**</span><span class="sxs-lookup"><span data-stu-id="05fe1-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="05fe1-113">**Modifier la \<policy\> configuration de la réunion -** affiche les paramètres de la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="05fe1-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="05fe1-114">Pour plus d’informations sur la configuration des paramètres, voir Créer des paramètres de configuration de [réunion dans Skype Entreprise Server.](create-settings.md)</span><span class="sxs-lookup"><span data-stu-id="05fe1-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="05fe1-115">Afficher les paramètres de configuration de réunion à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="05fe1-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="05fe1-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="05fe1-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="05fe1-117">Pour afficher des informations sur tous vos paramètres de configuration de réunion, utilisez l’cmdlet **Get-CsMeetingConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="05fe1-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="05fe1-118">Cette commande retourne des informations semblables à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="05fe1-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="05fe1-119">Pour plus d’informations, y compris une liste complète des paramètres, voir [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="05fe1-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

